Video Transcription Service
This Python script automates the process of downloading a YouTube video, uploading it to Amazon S3, transcribing the video using Amazon Transcribe, and saving the transcriptions back to the S3 bucket.

Dependencies
To run this script, you need to install the following Python packages:

pytube for downloading YouTube videos
boto3 for interacting with AWS services
Install the required packages using pip:

pip install pytube boto3

Usage
To use this script, follow these steps:

Set up your AWS credentials in the ~/.aws/credentials file or as environment variables.
Run the script using Python:
bash
Copy code
python video_transcription_service.py
When prompted, enter the name of your S3 bucket.
Enter the YouTube video URL you want to transcribe.
Wait for the script to complete the processing.
How it works
The script performs the following tasks:

Download the YouTube video using the pytube package.
Upload the video to the specified S3 bucket.
Start a transcription job using Amazon Transcribe.
Poll the transcription job status until it's completed or failed.
If the job is successful, download the transcription result and format it.
Save the formatted transcript to the S3 bucket.
Notes
This script assumes that your AWS credentials are properly configured.
Make sure that your S3 bucket and Amazon Transcribe service are in the same AWS region.
The script uses the highest resolution video stream available for the given YouTube video URL.
Transcripts are formatted with timestamps for every 10th word.
Temporary files are used for uploading and downloading from S3, and they are deleted after processing.
Transcription jobs can take some time to complete, depending on the length of the video. The script will poll the job status every 30 seconds until completion.
Troubleshooting
If you encounter issues with the pytube package, make sure that you have the latest version installed.
Ensure that your AWS credentials are properly set up and have the necessary permissions for the S3 and Transcribe services.