# cdk-CloudFormationTemplate-bucket
This repository describes the steps i took in creating a S3bucket inside a cf template using AWS CDK

**Step1**
- After setting up my development enivorment accoriding to https://docs.aws.amazon.com/cdk/latest/guide/getting_started.html , I created a new directory in my home directory and I also cd-ed into it.

```
mkdir endava-cdk
cd endava-cdk
```

**Step2**
- After the previous step, I initialized AWS CDK using a default app template and Python.

```
cdk init app --language python
```

The cdk init command will create a bunch of files and directories in our main directory, which we created at step1. These files actually represent the structure of the app which we are creating.
Once the initialization is done I installed the required dependencies.

```
python3 -m pip install -r requirements.txt
```
Lastly, i checked if the stack was created by listing all de cdk stacks

```
cdk ls
```
The output should be something containing the name of the created stack, in my case "EndavaCdkStack"


**Step3**
-I began with adding a S3-bucket to the app which I created.
-I used the following command in order to install the S3 aws package:

```
pip install aws-cdk.aws-s3
```

After that i cd-ed into the endava_cdk directory, which was created by the init process. Once inside i opened the whole directory in vscode and i edited the code as follows:
-I added "_from aws_cdk import aws_s3 as s3_" under the already existing imports
-I replaced the last comment with the following:

```
bucket = s3.Bucket(self, 
    "MyFirstBucket", 
    versioned=True,)
```
**
Step4**
