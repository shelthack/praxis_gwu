# Dataset Retrieval Instructions

This file provides instructions for retrieving the following CSV files from an Amazon S3 bucket:
- training_subset1.csv
- training_subset2.csv
- validation.csv
- testing.csv
- testing_no_label.csv

Two methods are provided: GitHub Actions and direct S3 access.

## Method 1: Using GitHub Actions

To retrieve the files using GitHub Actions:

1. Create a new GitHub repository or use an existing one.
2. In your repository, create a new file named .github/workflows/fetch_data.yml
3. Copy the following GitHub Actions workflow into the file:

```
name: Fetch Data from S3

on:
  workflow_dispatch:

jobs:
  fetch-data:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: us-east-1  # Replace with your S3 bucket's region

      - name: Fetch CSV files from S3
        run: |
          aws s3 cp s3://your-bucket-name/path/to/training_subset1.csv ./
          aws s3 cp s3://your-bucket-name/path/to/training_subset2.csv ./
          aws s3 cp s3://your-bucket-name/path/to/validation.csv ./
          aws s3 cp s3://your-bucket-name/path/to/testing.csv ./
          aws s3 cp s3://your-bucket-name/path/to/testing_no_label.csv ./
```

4. Replace 'your-bucket-name' and 'path/to/' with the actual S3 bucket name and path.
5. Set up AWS credentials as GitHub secrets:
   - Go to your repository settings
   - Click on "Secrets and variables" > "Actions"
   - Add two new repository secrets:
     - AWS_ACCESS_KEY_ID: Your AWS access key ID
     - AWS_SECRET_ACCESS_KEY: Your AWS secret access key
6. Run the workflow manually from the "Actions" tab in your GitHub repository.

Note: Ensure that the IAM user associated with these credentials has the necessary permissions to read from the S3 bucket.

## Method 2: Direct S3 Access

To retrieve the files directly from S3:

1. Install the AWS CLI: https://aws.amazon.com/cli/
2. Configure the AWS CLI with your credentials:
   aws configure
3. Use the following commands to download the CSV files:

```
aws s3 cp s3://your-bucket-name/path/to/training_subset1.csv ./
aws s3 cp s3://your-bucket-name/path/to/training_subset2.csv ./
aws s3 cp s3://your-bucket-name/path/to/validation.csv ./
aws s3 cp s3://your-bucket-name/path/to/testing.csv ./
aws s3 cp s3://your-bucket-name/path/to/testing_no_label.csv ./
```
Replace 'your-bucket-name' and 'path/to/' with the actual S3 bucket name and path.

Note: Ensure that your IAM user has the necessary permissions to read from the S3 bucket.



