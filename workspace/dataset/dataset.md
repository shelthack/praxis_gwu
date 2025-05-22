# Dataset Retrieval Guide

This document explains how to fetch the five CSV files used in the praxis experiments without bloating Git history.

| Bucket | Prefix |
|--------|--------|
| `s3://the-praxis` | `Dataset/output-path/new-processed-data/` |

**Files**

- `training_subset1.csv`
- `training_subset2.csv`
- `validation.csv`
- `testing.csv`
- `testing_no_label.csv`

> **Note** The repository is private while the praxis is under review.  
> After the 2025 defense it will become public, but the data will still live in S3 to keep the repo lightweight.

---

## 1. Quick pull with AWS CLI

### Prerequisites

* AWS CLI v2 installed  
* IAM credentials with `s3:GetObject` permission  
* `aws configure` (or environment variables) set up

```bash
# clone the repo first (omit --recurse if you are not using submodules)
git clone https://github.com/<user>/praxis_gwu.git
cd praxis_gwu

# create local data folder
mkdir -p data

# copy entire prefix
aws s3 cp \
  s3://the-praxis/Dataset/output-path/new-processed-data/ \
  data/ \
  --recursive

```

## 2. Programmatic pull (Python ≥ 3.10)

```python
import pathlib, boto3

bucket  = "the-praxis"
prefix  = "Dataset/output-path/new-processed-data/"
files   = [
    "training_subset1.csv",
    "training_subset2.csv",
    "validation.csv",
    "testing.csv",
    "testing_no_label.csv",
]

s3 = boto3.client("s3")          # picks up credentials from env or ~/.aws
pathlib.Path("data").mkdir(exist_ok=True)

for f in files:
    s3.download_file(bucket, f"{prefix}{f}", f"data/{f}")
    print(f"✓ {f} downloaded")

```



## 3. Automated pull in CI (GitHub Actions)

If you need the dataset during continuous integration (e.g., to retrain or test), add repository secrets
AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, and optionally AWS_REGION, then save this as .github/workflows/data.yml:

```yaml

name: Download dataset
on: [workflow_dispatch]

jobs:
  fetch:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: unfor19/install-aws-cli-action@v1
      - name: Pull CSVs from S3
        run: |
          mkdir -p data
          aws s3 cp s3://the-praxis/Dataset/output-path/new-processed-data/ data/ --recursive
      - name: (optional) Upload as artefact
        uses: actions/upload-artifact@v4
        with:
          name: dataset
          path: data

```

## 4. Verify file integrity (recommended)

Checksums are stored in workspace/dataset/appendix/dataset_checksums.txt. After downloading:


```bash
sha256sum -c docs/appendix/dataset_checksums.txt

```


## 5. License & Citation

The dataset retrieval code is released under the MIT License.

**Citation of the original praxis is required—see README.md for full citation instructions.**

