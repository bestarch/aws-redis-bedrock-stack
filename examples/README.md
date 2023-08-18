# Running example notebooks

To run these example notebooks, please follow these instructions.
1. Fireup Amazon SageMaker Studio.
2. Launch a Jupyter Notebook with the following runtime configurations:
   
   <img width="603" alt="image" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/49b9ae69-ac60-4451-b323-6510c5c91149">
3. Downoad Bedrock Python SDK from [here](https://d2eo22ngex1n9g.cloudfront.net/Documentation/SDK/bedrock-python-sdk.zip)
4. Unzip the SDK archive to access .whl files.
5. Move the .whl files in to a new directory.
6. Now start executing each cell in the Jupyter Notebooks and you should be in the game.

# IAM Policy setup for invoking Bedrock APIs.
Create an IAM policy like this in the policy editor:
```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "BedrockPolicySid",
            "Effect": "Allow",
            "Action": "bedrock:ListFoundationModels",
            "Resource": "*"
        }
    ]
}
```

And give this policy a name called `Bedrock Policy`
![image](https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/a646983f-84d9-41a9-970f-c694722ed1a6)

Then go ahead and add this to the your SageMaker Execution Role, like this:
![image](https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/b235ea64-30d7-4574-bc6e-62e382130805)

![image](https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/c955ece4-f236-4bd8-a054-e85f9259a4fc)

![image](https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/8fea975b-345b-4992-86cd-1bed23be7b5c)

Now when you execute the `bedrock.list_foundation_models()` it runs without any errors.

![image](https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/42957a05-33c5-4f7c-bd59-5bba6d73767d)
