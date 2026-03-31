**ASSIGNMENT : Install and set-up a .py app (CloudDrop) on an EC2
instance, create an S3 bucket and connect the app to it.**

**STEP 1 - ssh into my EC2 instance**

![](./media/media/image1.png)

**STEP 2 - updated the dependencies using dnf, package manager but they
were all up-to-date. I used the -y flag, it automatically answers yes to
all confirmations.**

![](./media/media/image2.png)

**STEP 3 - Installed the Python and Git application on my EC2
instance.**

![](./media/media/image3.png)

![](./media/media/image4.png)

**STEP 4 - Cloned the forked CloudDrop repo on my account.**
![](./media/media/image5.png)

**Changed directory into the created folder in the user home directory**

![](./media/media/image6.png)

**STEP 5 - Created my virtual environment folder named -venv. This
creates an isolated py environment, so that packages I install are local
and not global, thereby not affecting the rest of the global packages in
the server.**

![](./media/media/image7.png)

**STEP 6 - Activated the virtual environment created in step 5, so that
packages and dependencies are only installed within the project. This is
necessary to avoid package conflicts.**

![](./media/media/image8.png)

**STEP 7 - Installed all required packages the app needs from the
requirements.txt file - which is a file that lists all the dependencies
needed by CloudDrop application.**
![](./media/media/image9.png)

**STEP 8 - I allowed inbound traffic in my vpc security group on port
5000.**

![](./media/media/image10.png)

**STEP 9 - Executed the app using Flask's in-built development server.**

![](./media/media/image11.png)

**CloudDrop accessible in the browser using the http protocol, my EC2
instance public IP and the app's port no - http://100.27.32.225:5000**

![](./media/media/image12.png)

**STEP 10 - Created an AWS S3 Bucket**

![](./media/media/image13.png)

**STEP 11 - Created an IAM role with the AmazonS3FullAccess Policy, then
attached it to my EC2 instance. This allows my EC2 instance the
permission to communicate with my S3 bucket. Using this role, CloudDrop
is able communicate with my S3 bucket via Boto3 (AWS SDK) which fetches
the temporary credentials from my EC2 metadata in the background.**

![](./media/media/image14.png)

![](./media/media/image15.png)

![](./media/media/image16.png)

![](./media/media/image17.png)

**STEP 12 - Attached the created IAM role above, to the EC2 instance
CloudDrop app is deployed on.**

![](./media/media/image18.png)

![](./media/media/image19.png)

**STEP 13 - Set up my S3 Bucket Name as an environment variable on my
EC2 instance, in a hidden .bashrc file using a nano text editor.**

![](./media/media/image20.png)

![](./media/media/image21.png)

**STEP 14 - Reloaded the .bashrc file, so my changes can take effect
immediately without closing the current terminal session.**

![](./media/media/image22.png)

![](./media/media/image23.png)

**STEP 15 - My S3 Bucket with no object currently in it before running
app.py**

![](./media/media/image24.png)

**STEP 16 - Executed app.py from my isolated virtual environment.**

![](./media/media/image25.png)

**STEP 17 - Text upload success**

![](./media/media/image26.png)
![](./media/media/image27.png)

**STEP 18 - File upload success**

![](./media/media/image28.png)
![](./media/media/image29.png)

**STEP 19 - Objects successfully uploaded to S3 Bucket**

![](./media/media/image30.png)

![](./media/media/image31.png)

![](./media/media/image32.png)
