## All about AWS S3

## Before AWS S3
Organizations had a difficult time finding, storing, and managing all of your data. Not only that, running applications, delivering content to customers, hosting high traffic websites, or backing up emails and other files required a lot of storage. Maintaining the organization’s repository was also expensive and time-consuming for several reasons. Challenges included the following:

- Having to purchase hardware and software components
- Requiring a team of experts for maintenance
- A lack of scalability based on your requirements
- Data security requirements

These are the issues AWS S3 would eventually solve. So, what exactly is AWS S3? 


## What is Amazon Simple Storage Services (Amazon S3)?

Amazon Web Services (AWS) is defined as a service that provides object storage via a web interface to make web-scale computing more accessible to developers. This service enables companies of all sizes and industries to store vast amounts of data for a variety of uses, including websites, mobile apps, disaster recovery, and big data analytics. It provides 99.999999999 percent durability and 99.99 percent availability of objects. It can also store computer files up to 5 terabytes in size.

## AWS S3 Benefits

Some of the benefits of AWS S3 are: 

- **Durability**:  S3 provides 99.999999999 percent durability.
- **Low cost**: S3 lets you store data in a range of “storage classes.” These classes are based on the frequency and immediacy you require in accessing files. 
- **Scalability**: S3 charges you only for what resources you actually use, and there are no hidden fees or overage charges. You can scale your storage resources to easily meet your organization’s ever-changing demands.
- **Availability**: S3 offers 99.99 percent availability of objects
- **Security**: S3 offers an impressive range of access management tools and encryption features that provide top-notch security.
- **Flexibility**: S3 is ideal for a wide range of uses like data storage, data backup, software delivery, data archiving, disaster recovery, website hosting, mobile applications, IoT devices, and much more.
- **Simple data transfer**: You don’t have to be an IT genius to execute data transfers on S3. The service revolves around simplicity and ease of use.

These are compelling reasons to sign up for S3. Now, let’s move on and have a look at some of the major components of the AWS S3 storage service.

## How Does Amazon S3 work?
First off, a user creates a bucket. When this bucket is created, the user will specify the region in which the bucket is deployed. Later, when files are uploaded to the bucket, the user will determine the type of S3 storage class to be used for those specific objects. After this, users can define features to the bucket, such as bucket policy, lifecycle policies, versioning control, etc.

Now, let’s talk about the different storage classes offered by Amazon S3.

Amazon S3 Storage Classes:
This storage maintains the originality of data by inspecting it. Types of storage classes are as follows:

- Amazon S3 Standard
- Amazon S3 Intelligent-Tiering
- Amazon S3 Standard-Infrequent Access
- Amazon S3 One Zone-Infrequent Access
- Amazon S3 Glacier Instant Retrieval
- Amazon S3 Glacier Flexible Retrieval
- Amazon S3 Glacier Deep Archive


#### 1. Amazon S3 Standard:
It is used for general purposes and offers high durability, availability, and performance object storage for frequently accessed data. S3 Standard is appropriate for a wide variety of use cases, including cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics.

Mainly it is used for general purposes in order to maintain durability, availability, and performance to a higher extent. Its applications are cloud applications, dynamic websites, content distribution, mobile & gaming apps as well as big data analysis or data mining.

Characteristics of  S3 Standard:

- Availability criteria are quite good like 99.9%.
- Improves the recovery of an object file.
- It is against the events which are a little bit tough that can affect an entire Availability Zone.
- Durability of S3 standard is 99.999999999%.


#### 2. Amazon S3 Intelligent-Tiering:

The first cloud storage automatically decreases the user’s storage cost. It provides very cost-effective access based on frequency, without affecting other performances. It also manages tough operations. Amazon S3 Intelligent – Tiering reduces the cost of granular objects automatically. No retrieval charges are there in Amazon S3 Intelligent – Tiering.

Characteristics of  S3 Intelligent-Tiering:

- Required less monitoring and automatically tier charge.
- No minimum storage duration and no recovery charges are required to access the service.
- Availability criteria are quite good like 99.9%.
- Durability of S3 Intelligent- Tiering is 99.999999999%.



#### 3. Amazon S3 Standard-Infrequent Access:

To access the less frequently used data, users use S3 Standard-IA. It requires rapid access when needed. We can achieve high strength, high output, and low bandwidth by using S3 Standard-IA. It is best in storing the backup, and recovery of data for a long time. It act as a data store for disaster recovery files.

Characteristics of  S3 Standard-Infrequent Access:

- High performance and same action rate.
- Very Durable in all AZs.
- Availability is 99.9% in S3 Standard-IA.
- Durability is of 99.999999999%.



#### 4. Amazon S3 Glacier Instant Retrieval:

It is an archive storage class that delivers the lowest-cost storage for data archiving and is organized to provide you with the highest performance and with more flexibility. S3 Glacier Instant Retrieval delivers the fastest access to archive storage. Same as in S3 standard, Data retrieval in milliseconds.

Characteristics of S3 Glacier Instant Retrieval:

- It just takes milliseconds to recover the data.
- The minimum object size should be 128KB.
- Availability is 99.9% in S3 glacier Instant Retrieval.
- Durability is of  99.999999999%.



#### 5. Amazon S3 One Zone-Infrequent Access:

Different from other S3 Storage Classes which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data in a single Availability Zone and costs 20% less than S3 Standard-IA. It’s a very good choice for storing secondary backup copies of on-premises data or easily re-creatable data. S3 One Zone-IA provides you the same high durability, high throughput, and low latency as in S3 Standard.

Characteristics of S3 One Zone-Infrequent Access:-

- Supports SSL(Secure Sockets Layer) for data in transferring and encryption of data.
- Availability Zone destruction can damage the data.
- Availability is 99.5% in S3 one Zone- Infrequent Access.
- Durability is of  99.999999999%.



#### 6. Amazon S3 Glacier Flexible Retrieval:

It provides low-cost storage compared to S3 Glacier Instant Retrieval. It is a suitable solution for backing up the data so that it can be recovered easily a few times in a year. It just takes minutes to access the data. 

Characteristics of S3 Glacier Flexible Retrieval:

- Free recoveries in high quantity.
- AZs destruction can lead to difficulty in accessing data.
- when you have to retrieve large data sets , then S3 glacier flexible retrieval is best for backup and disaster recovery use cases.
- Availability is 99.99% in S3 glacier flexible retrieval.
- Durability is of  99.999999999%.



#### 7. Amazon S3 Glacier Deep Archive:

The Glacier Deep Archive storage class is designed to provide long-lasting and secure long-term storage for large amounts of data at a price that is competitive with off-premises tape archival services that is very cheap. You no longer need to deal with expensive services. Accessibility is very much efficient, that it can restore data within 12 hours. This storage class is designed in such a way that users can easily get long-lasting and more secured storage for a huge amount of data at very less cost. Efficient accessibility and can restore data within very less time, therefore its time complexity is also efficient. S3 Glacier Deep Archive also have the feature of objects replication.

Characteristics of S3 Glacier Deep Archive:-

- More secured storage.
- Recovery time is less requires less time.
- Availability is 99.99% in S3 glacier deep archive.
- Durability is of  99.999999999%.


![comparison_of_all_storgae_classes.jpg](https://cdn.hashnode.com/res/hashnode/image/upload/v1659931149827/aIo2dWDbR.jpg align="left")


![Technical_comparison_between_classes.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659931191992/NKQ0gUZUw.png align="left")

## Data Protection
Amazon S3 provides IT teams with a highly durable, protected, and scalable infrastructure designed for object storage.

#### Amazon S3 protects your data using two methods: 

- Data encryption
- Versioning
- Cross-region Replication
- Transfer Acceleration



1. Data Encryption
This refers to the protection of data while it’s being transmitted and at rest. It can happen in two ways, client-side encryption (data encryption at rest) and server-side encryption (data encryption in motion).

2. Versioning
It is utilized to preserve, recover, and restore an early version of every object you store in your AWS S3 bucket. Unintentional erases or overwriting of objects can easily be managed with versioning. For example, in a bucket, it is possible to have objects with the same key name but different version IDs. 

3. Cross-region Replication
Cross-region replication provides automatic copying of every object uploaded to your buckets (source and destination bucket) in different AWS regions. Versioning needs to be turned on to enable CRR.

4. Transfer Acceleration
This enables fast, easy, and secure transfers of files over long distances between your client and S3 bucket. The edge locations around the world provided by Amazon CloudFront are taken advantage of by transfer acceleration. It works by carrying data over an optimized network bridge that keeps running between the AWS Edge Location (closest region to your clients) and your Amazon S3 bucket.


## Why Should we Consider Using Amazon S3?

Now that we’ve answered the question “What is AWS S3?” let’s dig into why you should consider using it. There are two big reasons why you should use Amazon S3, and they’re points we’ve covered before but bear calling further attention to:

- S3 offers 99.999999999% (11 9s) data durability. That means, if you stored 10,000,000 objects in Amazon S3, you would only lose a single object every 10,000 years. That is durable!

- S3 will automatically create and store copies of every uploaded object across many systems. This protects your data against errors, failures, and threats while guaranteeing you complete data availability when you need it. 
 
Also, it doesn’t hurt that Amazon Web Services is the most popular cloud provider available today.
