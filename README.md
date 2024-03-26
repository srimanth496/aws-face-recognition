# aws-face-recognition


Face recognition in AWS by using S3 and lambada and dynamo db,Amazon Rekognition :

in this project we can detect the persons image ,first upload the images in the s3 bucket named as Facerecognition,uploaded five images of famous persons in facerecognition bucket, created lambada function,
inside lambda function i created event triggers when ever upload any image or file upload into the Facerecognition bucket lambada function triggers and test the python code uploaded in lambda function,
in dynamo db index is populated means images stored in database.IAM role is created for the services and inline policy created for the lambda functions . Then test the execution python  code by using CLI commands in powershell ,
enter the image name then display the name of the person means exected successfully. 

first go to the power shell windows to write commands aws confiure by creating security credentials in iam acces keys

![Screenshot 2024-03-26 123813](https://github.com/srimanth496/aws-face-recognition/assets/84217751/f2a97a53-9247-4c82-a2c0-4b45cc2987b8)

by using amazon rekognition collect  the images of the famous persons by creating rekognition in aws console
Create a collection on aws rekognition
aws rekognition create-collection --collection-id facerecognition_collection --region us-east-1

. create dynamobd can stores the images of the famous persons

aws dynamodb create-table --table-name facerecognition --attribute-definitions AttributeName=RekognitionId,AttributeType=S
--key-schema AttributeName=RekognitionId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1 --region us-east-1
these commands helps to create data base for store th images
![Screenshot 2024-03-26 125149](https://github.com/srimanth496/aws-face-recognition/assets/84217751/85c0cfb6-5fe2-48d8-bb99-d451c4dc40e2)

. Create S3 bucket
PS C:\Users\srima> aws s3 mb s3://personsfamous-images
![Screenshot 2024-03-26 125553](https://github.com/srimanth496/aws-face-recognition/assets/84217751/24239ff8-f5bd-404d-8a13-588a27dde345)

. creating lambda function this function can access s3 and  dynamo db cloud watch logs  we need to create the i am role and inline policies for lambda function for the lambda function.
![Screenshot 2024-03-26 131120](https://github.com/srimanth496/aws-face-recognition/assets/84217751/651e9905-2a23-4745-a96f-f3f54c114944)
trigger added to lambda function
![Screenshot 2024-03-26 131442](https://github.com/srimanth496/aws-face-recognition/assets/84217751/8d087ced-2f80-4168-b208-7edf07fc8b7b)
write code in python when ever lambada triggers this python code executes 
![Screenshot 2024-03-26 132449](https://github.com/srimanth496/aws-face-recognition/assets/84217751/cd67fefa-e557-4dba-8d4c-10eb2db6870a)
. s3 uploading the files and images in s3 bucket
![Screenshot 2024-03-26 132937](https://github.com/srimanth496/aws-face-recognition/assets/84217751/8eaa8dbe-08e7-4240-b0e0-555feb7013cb)

extracting the names of famous persons
![Screenshot 2024-03-26 133024](https://github.com/srimanth496/aws-face-recognition/assets/84217751/f73a618b-df18-45ab-a3ed-d250be083d8f)







