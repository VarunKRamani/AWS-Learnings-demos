# Learnings Around S3

Simple Storage Service: A Cloud based storage which stores data in form of objects with in Buckets, these buckets are globally unique. 

Each object cannot be more then 5TB, Files stored in buckets can be accessed using Http protocol.
Server side encryption is automatically added to the objects stored in the buckets.
Can Add Tags 
Event notification, when a specific event is performed a notififation is sent.
Bucket Versioning: once enabled, we can used S3 as versioning system.
Can Host static websites on S3. 

Advantages: Security, Cost effecrtive, availablity & durability, performance and scalability.
_________________
Hands On :
- **Bucket versioning with IAM user**:
We start from unabling the versioning feature of the bucket. The previous version of the file/objects can be deleted with set time i.e. to auto delete with set a set timer (eg: 5 days, 10 days). The older versions can be stored in a different storage calss like S3 glacier etc fro minimal charges and retrive needed. Once the versioning is enabled we move on the create IAM user to test bucket policy, bacing on the bucket policy writen to specific buckets and appropraite permissions assined the IAM user will be able to access the objects, IAM user Creation with S3 full access, changing the bucket policy from the Root user, and test the availablity of the objects in buckets with pre defined policy.

- **Static website hosting**:
Under this demo, we demonstratite static website hosting in bucket, go to properties of bucket and enable static website hosting. Once the hosting feature is unabled make sure the public Access is also enabled to see the website hosted, check under permissions to make it publically available. Now edit the bucket policy too, for all the public to access the website. once the website is hosted get the URL under 'static website hosting' and browse it to access the website. 
<img width="1911" height="431" alt="image" src="https://github.com/user-attachments/assets/e8d7739e-6c57-45f0-8646-06b4593ee3ec" />

