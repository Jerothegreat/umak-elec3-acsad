# Lab 1 Submission (EXAMPLE)




## Part B
<img width="680" height="186" alt="717b476c-4a50-4ddd-9b25-6548406c3371" src="https://github.com/user-attachments/assets/5e5cf1bf-8c48-4c69-99ce-af5934518009" />
<img width="777" height="438" alt="39698953-c7f1-4aee-ae68-eff65d614dbf" src="https://github.com/user-attachments/assets/1f3f79fa-97f1-4354-a3b6-e6144b3e016c" />

**Screenshot:**
![Part B Error](example-part-b-error.png)

## Part C
<img width="786" height="437" alt="5a196622-c70d-4e1c-a8d9-68daf1df6687" src="https://github.com/user-attachments/assets/b18f8775-902c-4e8a-8198-53dc258c384d" /><img width="781" height="437" alt="02f8dce3-fbaf-4337-ac78-49593f10b81a" src="https://github.com/user-attachments/assets/1994c294-1242-42d4-b504-2c16b1eb55f8" />
<img width="778" height="348" alt="cee16cea-5aa2-4d9b-ad21-1581151a899d" src="https://github.com/user-attachments/assets/6721870f-2a0c-47e1-945e-c00233526b1e" />
<img width="782" height="337" alt="a5691d77-e091-493b-8fa9-fa8f06b9afea" src="https://github.com/user-attachments/assets/86944e2f-85ce-46fd-816d-31c54fc1412f" />
<img width="783" height="437" alt="e9276dfc-436d-4a73-99c1-416126a01b83" src="https://github.com/user-attachments/assets/35d5b38f-8f3f-4803-a782-7b6913032ed3" />


## Part D
<img width="777" height="268" alt="454e58f0-8940-44bd-9419-57ed7909e1b4" src="https://github.com/user-attachments/assets/34b8e578-065a-4290-86ec-c6ad8ced796d" /><img width="780" height="332" alt="7bb6b252-4b5d-4cec-b6d0-3ae27f97bc13" src="https://github.com/user-attachments/assets/bdde17a4-3264-4657-af37-71d7e0cfbeab" />
<img width="783" height="355" alt="19e652e2-f70a-4bec-977d-f7ff4c9e0a55" src="https://github.com/user-attachments/assets/bbea0cc2-f313-4950-ac07-26bb0d7ecfa5" />
<img width="785" height="177" alt="f65b3d78-edcf-45ca-a5ed-30bcc49fe902" src="https://github.com/user-attachments/assets/7eb1da73-dd75-49f3-8ada-f0de41708424" />
<img width="777" height="263" alt="2273f603-1ebc-417c-8089-3595b9a96c5f" src="https://github.com/user-attachments/assets/2a77eb6d-435a-414d-bf52-5d3fb82eede1" />


**Running Instance Time:** 14:05 UTC

**Screenshot 1 (Permissions Tab):**
![Permissions Tab](example-part-d-policy.png)

**Screenshot 2 (Running Instance):**
![Running Instance](example-part-d-instance.png)

## Part E
<img width="781" height="301" alt="055cdf91-ad98-4e5b-a567-603bacebfd5c" src="https://github.com/user-attachments/assets/23c48835-7a0f-464f-8033-ea0d0f660859" />
<img width="780" height="328" alt="9046ced1-1732-48cc-b755-96c4cd5a0298" src="https://github.com/user-attachments/assets/b0228e32-828b-4e69-b03f-a71dcb4f2f35" />
<img width="781" height="336" alt="63b4b21f-8415-44e5-8cc3-e78ca81d5008" src="https://github.com/user-attachments/assets/fa928607-0372-4098-a04f-3f66a7bce118" />
<img width="783" height="352" alt="c24c85ce-196b-4db1-888e-dd3974bff1d8" src="https://github.com/user-attachments/assets/cab73ebc-766b-4955-ba86-764f0e4b10dc" />
<img width="782" height="343" alt="fc52f7e3-04d1-4f6b-85ad-9ad07f4ec498" src="https://github.com/user-attachments/assets/ab6624e7-3dd4-422c-825d-ffa7040b1007" />

**t3.small / Tokyo Denial Error:** 
Instance launch failed... with an explicit deny in a permissions boundary.

**Screenshot 1 (Boundary Denial):**
![Boundary Denial](example-part-e-denial.png)

**Screenshot 2 (CloudTrail Event):**
![CloudTrail Event](example-part-e-cloudtrail.png)

Part F: Questions and Evidence
1. Which action did the Part B error name?	
ec2:RunInstances
2. In your policy, which condition limits ec2:RunInstances?
The condition "ec2:InstanceType": "t3.micro" limits ec2:RunInstances to only allow t3.micro instances.
3. After you attached ec2:* on * , why was t3.small still denied? Name the boundary statement.
The t3.small launch was still denied because the permissions boundary explicitly denies instance types other than t3.micro. The boundary statement is "DenyAnyInstanceTypeButT3Micro."
4. Why is ec2:* on * a poor policy even with a boundary?
The policy gives permission to perform all EC2 actions on all resources, which violates the principle of least privilege. A permissions boundary limits some actions, but the policy is still unnecessarily broad.
5. In two sentences: what does the boundary control that your policy cannot?
The permissions boundary sets the maximum permissions that the IAM user can have, including restrictions on instance types, regions, and resource ownership. Even if an attached policy allows an action, the boundary can still prevent that action from being performed.
