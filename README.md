# Voice controlled photo album
 Designed a scalable photo album web application that can be searched using natural language through both text and voice and also created a CI/CD DevOps pipeline to automate the build, test and deploy phases.

![alt text](https://github.com/KshitijaSAPatel/Voice-controlled-photo-album/blob/main/Architecture/diagram.png)

#### Output:

![alt text](https://github.com/KshitijaSAPatel/Voice-controlled-photo-album/blob/main/FrontEnd/FrontEndUI.png)

#### AWS Services Used:
<ul>
 <li> S3 : To host buckets for the frontend, uploaded images, lambda code for Cloudformation stack to deploy lambda, etc. </li>
 <li> Lambda : To implement the indexing function which is triggered when image is uploaded to S3. It used Rekognition to label the image and stores in ES. Also to implement the search lambda function which has an API Gateway trigger. It parses the searched text using LEX, searched labels in ES and returns url for images in S3 </li>
 <li> ElasticSearch : Stores images along with their labels </li>
 <li> Rekognition : Used for object detection on uploaded images. Returns labels for images. </li>
 <li> Lex : Used to parse the search text </li>
 <li> CloudFront : To redirect http requests to https to be able to use microphone service </li>
 <li> CodePipeline : To build the CI/CD DevOps pipeline to automate code updation when changes are made in the corresponding GIT Repository </li>
 <li> CloudFormation : To build the resource deployment stack </li>
 <li> CodeBuild : To build the lambda functions from the buildspec yaml files in Git </li>
 <li> API Gateway : To connect the frontend with the backend </li>
 <li> IAM : To defines roles and corresponding policies for the resources </li>
</ul>
