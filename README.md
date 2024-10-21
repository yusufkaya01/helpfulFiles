# Website Hosting with S3 and CloudFront - Jenkins Pipeline

This Jenkins pipeline is specifically designed for website hosting using Amazon S3 and CloudFront. It automates the process of uploading files to an S3 bucket, configuring a CloudFront distribution, and invalidating the cache when changes are made.

## Prerequisites

Before using this pipeline, ensure you have the following set up:

1. **AWS CLI**: Make sure AWS CLI is installed and configured on the machine where Jenkins is running. You can configure AWS CLI by running `aws configure` and providing your AWS credentials.

2. **Jenkins**: You should have a Jenkins instance set up with the necessary plugins installed for pipeline execution.

## User Inputs

When you run this Jenkins pipeline, it will prompt you for the following inputs:

- **S3_BUCKET**: Enter the name of the S3 bucket where you want to host your website.
- **S3_ARN**: Enter the ARN of the S3 bucket.
- **CLOUDFRONT_DISTRIBUTION_ID**: Enter the CloudFront distribution ID you want to use.
- **GITHUB_REPO**: Enter the URL of the GitHub repository that contains the website files.

## Pipeline Stages

The pipeline consists of the following stages:

1. **Get User Input**: Prompts the user for the required inputs.
2. **Clone GitHub Repository**: Clones the specified GitHub repository into a local directory.
3. **Check S3 Bucket for Files**: Checks if the S3 bucket is empty.
4. **Empty S3 Bucket if Not Empty**: If the bucket is not empty, it empties the bucket.
5. **Upload Files to S3 Bucket**: Uploads the cloned files from the repository to the S3 bucket.
6. **Output S3 Bucket Website Endpoint**: Displays the S3 bucket website endpoint.
7. **Invalidate CloudFront Distribution**: Invalidates the CloudFront distribution cache to reflect the latest changes.
8. **Output CloudFront Distribution Link**: Displays the CloudFront distribution link.

## Usage

To use this Jenkins pipeline:

1. Create a new pipeline job in Jenkins.
2. Copy and paste the pipeline script into the job configuration.
3. Run the pipeline and follow the prompts for user input.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

Yusuf Kaya
