<h1>Hosting a Static Website on S3</h1>
<!--
 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)
--!>
<h2>Description</h2>
A new startup business in North America has recruited you to help with the launch of a quick-access, low-cost static website. You've decided to complete this contract by hosting and deploying their website utilizing AWS S3
<br />


<h2>Solution Overview</h2>

- <b>Create an S3 Bucket and enable static website hosting
- Grant permission to bucket to allow public access and read access to everyone
- Upload HTML code for web site
- View the website using the bucket endpoint created</b> 


<h2>Detailed Steps:</h2>

<p align="center">

Navigate to the “S3" resource on AWS

Select "Create Bucket" and give the bucket a name: <br/>
<img src="https://i.imgur.com/vGXPAML.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the region to host the website:  <br/>
<img src="https://i.imgur.com/TRR47JW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Uncheck "Block all public access". This allows public (anyone on the internet) access to your bucket: <br/>
 - This comes with risk but is out of the scope of this project 

Select "Create Bucket" to create the bucket


In your bucket, navigate to the "properties" tab, scroll all the way down and select "edit" under "static website hosting"

Enable static website hosting

Give a name to your "index document" (this is usually index.html), then save changes
- Note that the main source code has to have the same name as your "index document"

Upload your website source code
- Note that the main source code has to have the same name as your "index document"

Click the bucket website endpoint under "static website hosting" and note that you get an error. This is because the bucket policy has not be updated to grant public access:  <br/>
<img src="https://i.imgur.com/ezN9iyq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
To grant public access, click on the "Permissions" tab within the bucket and edit the bucket policy to the policy below
- Note that you must update the "Resource" to your buckets' ARN which can be found at the top left when you click on edit bucket policy
- Also note the "/*" at the end of the ARN, this gives access to every file within the bucket  <br/>
<img src="https://i.imgur.com/VztcVKr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now click the bucket website endpoint under "static website hosting" and access your website.  <br/>
<img src="https://i.imgur.com/6L5B0TN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
