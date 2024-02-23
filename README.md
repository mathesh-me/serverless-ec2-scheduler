# Serverless EC2 Instance Scheduler for Company Working Hours 
## Scenario :
In some companies, there is no need to run their EC2 instances 24/7; they require instances to operate during specific time periods, such as company working hours, from 8:00 AM in the morning to 5:00 PM in the evening. To address this scenario, I will implement two Lambda functions responsible for starting and stopping instances. These Lambda functions will be triggered by two CloudWatch Events in the morning and evening. This solution is fully serverless.

![Blank diagram](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/287063a4-964a-4f8b-b88e-25535b7f4691)


## Steps :

### Step 1 :
### Creating the Instance :
1. Navigate to the EC2 Console.
2. Follow the Outlined steps below.

![a1](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/b29f0f1a-680c-44f8-ab00-786fcf0436a5)


![a2](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0515f5b7-f504-4669-98fe-9605cc3ccd39)


![a3](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/259cc31e-e73a-4b85-8229-f9f29d84be1e)


![a4](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/a34454c0-9ad8-42a0-9127-2a80cdcfa9cb)


![a5](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/c07c8f7c-de69-406a-bb35-adf7d080027e)


![a6](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/46960135-2a4b-4d6c-9dd1-04b75e113294)


### Step 2 :
### Creating the Policy :


1. Navigate to the IAM Console.
2. Click on "Policies" and then Click on "Create policy"


![a7](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/92ea0ecd-8106-4e7f-80fc-c815093cf319)


3. Select services as EC2.
4. And Actions are DescribeInstances , StartInstances.


![a8](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/adae28aa-c4e9-4ea2-b796-4c01c1d0f99d)


![a9](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/ca8dc00e-4931-4646-a984-f251d83ebf6a)



![a10](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/68aa30f9-1a1a-4631-ac01-a98ba3ac05e9)


![a11](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/8543cf1c-26d3-41dd-9121-99015183f760)


![a12](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/78b57e8c-b8b5-470e-9af1-e7789b09f522)


![a13](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/1a1da31e-d564-4264-9b4e-fdb5438ed705)
5. Now we have created a policy for starting instances. We also need to create a policy for stopping the instances. This is because we are going to create two Lambda functions: one for starting and one for stopping the instances. Each function will have its own role, and we will attach these two policies to their respective roles.<br>
6. Now  we are going to repeat the same steps for Creating Stopping Policy also.<br>
7. Everything is same , Except Actions because we are going to stop the instance.<br>
8. The Actions are DescribeInstances , StopInstances .<br>
9. Keep your Plolicy name as "stop-ec2-instance".

## Step 3 :
## Creating the Lambda functions :

1. Navigate to the lambda Console.
2. Follow the Outlined steps below.


![a14](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0c16bb73-c4e2-4d0d-94a3-d7eb6a7b2468)


![a15](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0e1249d5-b472-46bb-8f8f-9cfffaed63e9)


![a16](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/bfbaff0e-417f-49fa-b742-622b91aa7aba)


![a17](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/e779b8fa-261f-45f5-8fad-f0f2aa60fb76)

![Screenshot 2024-02-23 065451](https://github.com/mathesh-me/serverless-ec2-scheduler/assets/144098846/3b0baa46-d8a4-4b09-8068-fce93dd37e5e)

![Screenshot 2024-02-23 065512](https://github.com/mathesh-me/serverless-ec2-scheduler/assets/144098846/1945a052-6730-4a9b-a4e5-b7ca6a6b1ce3)

![a18](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/e05532fd-b0ba-4c81-b837-be449251f2fe)


![a19](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/00a475ec-d570-47ef-9487-9a7ad6f99c67)


![a20](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/348cbc2f-650f-4e53-b375-36da1d515c21)


![a21](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/2256bd57-6ac7-4581-b1a2-2d23e5c80da8)


![a22](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/f25ec148-b4ba-4c38-bf27-6ec948b78100)


![a23](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/f628f5da-4c68-4725-a387-3931a71cfc61)


![a24](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/a0ba4746-c2dc-4e7e-8395-031adc4a2cae)

Now again , go to the Lambda console and then test the code.
![a25](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0b40564d-dea9-4101-936f-436d72dae232)
![a26](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/b6e1a8f8-9a2b-4d8d-aef2-d9059aba2928)


3. Now we Created  alambda function for Starting Instance.
4. We have to Reapeat the same steps again to Create a Lambda function for Stopping Instance , Keep your lambda function name as "Stop-EC2-demo".
5. The only changes we have to make are to replace the default code with the 'stop-ec2-instance.py' code and attach the policy we created for stopping instances to the role of this Lambda function.


![a27](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0752d20d-bfe3-45a9-9c63-b9c0111ab132)

6. As demonstrated above, when I test my Python code, it runs successfully and stops the instance.
7. Now, we are ready to proceed and create schedules for this functions.

### Step 5 :
### Creating the Schedules Using Cloud Watch :

1. Navigate to the Cloud Watch Console.
2. Follow the Outlined Steps below.


![a28](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/a932c63f-8a3b-46aa-ade2-ed0d9dd8cdac)



![a29](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/cfd0914c-7c0c-4064-ae3e-72874467fe7c)


![a30](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/8eec38a6-ec9b-4421-8911-8d3adf1247ca)
#### Note : Keep your rule name as "start-ec2-rule" , I mistakenly named it 'role' Please do not name it as 'role.'





![b1](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/caad4063-65f7-4c29-8c06-e9988cb6818c)


![b1 1](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/ed864740-4d80-4c4f-80d7-2fa74737d3c4)


![b2](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/70f29eaa-73fc-49ec-9c39-a6d1214d14f3)


![b3](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/8935ecd6-ce42-4347-b48c-3b5564679c03)


![b4](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/7cd915a1-573c-4822-b7c0-ff588521527a)


![b5](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/0ef48fa1-bcf8-41c4-a729-7a5d5555fd05)


![b6](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/1d11c5b3-a734-470c-bdf5-ab29d6f3f14c)


![b7](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/ea584d14-d997-46d7-b1ec-f07cb88a9ede)


![b8](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/b76d4878-b391-4d9c-9b12-07b1b1ebfb5d)


3. We have now created a schedule for starting the instance every day at 8:00 AM.<br>
4. Next, we need to create a schedule for stopping instances.<br>
5. To create the schedule for stopping instances, follow the same steps as for starting instance scheduling with a few changes, Keep your rule name as "stop-ec2-rule".<br>
6. The changes include modifying the scheduled time and selecting the appropriate scheduling function.<br>
7. We need to change the schedule time to 17:00 because it will stop the Lambda function at 17:00 IST (5:00 PM).

![b9](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/103c0f33-6036-4f3d-ac3f-875811cae174)

8. We have to Change the Function as Stop-EC2-demo

![b10](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/149a3faa-dea1-437c-bc3d-4515fb70dd5f)

9. Now, we have successfully created two schedules: one to start the instance every day at 8:00 AM and the other to stop the instance every day at 5:00 PM.


![b11](https://github.com/itz-mathesh/serverless-ec2-scheduler/assets/144098846/d6b5a3df-75d1-47ac-9b9c-4a6ce73854b1)


