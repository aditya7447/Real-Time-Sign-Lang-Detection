# Project Setup

## 1. Host Model on Cloud Object Storage

To host your model on Amazon S3 presented in the converted folder, follow these steps:

1. **Create an Amazon S3 Bucket:**
   - Log in to your AWS Management Console.
   - Navigate to the Amazon S3 service.
   - Create a new S3 bucket or use an existing one.

   [Watch this tutorial for creating an S3 bucket on YouTube](https://youtu.be/MwFH65uTMXw?si=mTvfMSELhTzCkrPe).

2. **Upload Model Files:**
   - Navigate to the directory containing your model files:
     ```
     Real-Time-Sign-Lang-Detection\Tensorflow\workspace\models\my_ssd_mobnet\converted
     ```
   - Upload all files from this directory to the root of your S3 bucket.
   - Ensure that the necessary CORS configurations allow access to your model.

3. **Make Model Public:**
   - In the S3 bucket, select the uploaded model files.
   - In the "Actions" menu, choose "Make public" or configure appropriate permissions.

   [Watch this tutorial for making your S3 bucket public by adding a policy on YouTube](https://youtu.be/sWOkwp4Kd_I?si=JHeDoRvt7c5uB4UA).

4. **Get Model URL:**
   - Obtain the URL of your model (e.g., `https://your-s3-bucket-name.s3.amazonaws.com/model.json`).

5. **CORS Configuration:**
   - Add the following CORS configuration to your S3 bucket:

   ```json
   [
       {
           "AllowedHeaders": [
               "*"
           ],
           "AllowedMethods": [
               "GET"
           ],
           "AllowedOrigins": [
               "*"
           ],
           "ExposeHeaders": [
               "ETag",
               "x-amz-meta-custom-header"
           ]
       }
   ]
## 2. Install and Update Dependencies

To install and update project dependencies, run the following commands:

```bash
# Install dependencies
npm install

# Update dependencies to their latest versions
npm update

# Rebuild native Node.js modules (if needed)
npm rebuild
