-------

# Redis Enterprise Cloud Setup

## Objective
The goal is to deploy Redis Enterprise Cloud as your vector database for AWS Bedrock on the AWS Marketplace. You will create a flexible, pay-as-you-go subscription. If you are new to Redis, **we even give you a 14-day free trial of $500 USD to get started!**

Link directly from the Bedrock configuration screen, or manually [follow this link](https://aws.amazon.com/marketplace/pp/prodview-mwscixe4ujhkq?sr=0-11&ref_=beagle&applicationId=AWSMPContessa) to the AWS Marketplace offering to get started.

## Setup Procedure

### Getting started from AWS Marketplace
Once on the landing page, continue to click on `View purchase options`.

<img width="1296" alt="bedrock-redis-rc-2" src="./assets/bedrock-redis-rc-2.png">

On the product page,
1. Click on the `Subscribe` button. This button gets greyed out after you click on it for the first time.
2. Then the banner highlighted at the top, will appear.
3. On this banner, go ahead and click on `Setup your account`.

<img width="1296" alt="bedrock-redis-rc-3" src="./assets/bedrock-redis-rc-3.png">

This navigates you to the sign-in page of `Redis Enterprise Cloud` web console.

<img width="1288" alt="bedrock-redis-rc-4" src="./assets/bedrock-redis-rc-4.png">

As soon as you sign in , you will see that your `AWS Account` ( example: `Srini 1320974`) is displayed and you will be able to connect this AWS account with Redis Enterprise Cloud web console.
Go ahead and check the selection box highlighted.
<img width="1288" alt="bedrock-redis-rc-5" src="./assets/bedrock-redis-rc-5.png">

Click `Connect account`. This will connect your AWS account with "Redis Enterprise Cloud" web console.

<img width="1288" alt="bedrock-redis-rc-6" src="./assets/bedrock-redis-rc-6.png">

Once connected successfully, you will see a message at the top ( see annotation 1) and now you can get started. In this case, since a "Free Trial" option is chosen, you will see a `Start free trial` option.
Go ahead and click on `Start free trial`.

<img width="1288" alt="bedrock-redis-rc-7" src="./assets/bedrock-redis-rc-7.png">

As soon as you login, you will see this UI. Notice that there is a Free Trial banner at the top. Ignore this banner, if you are not on a promotional free tier.
1. Appearance of `AWS Marketplace` icon, indicates that your Redis account is now connected to your AWS account.
2. On the `Setup` tab, you will see cloud vendors.
3. Select `AWS` if it is not highlighted and selected already.

<img width="1293" alt="bedrock-redis-rc-8" src="./assets/bedrock-redis-rc-8.png">

### Setting up Redis Subscription

Go ahead and select your `Region` and give `Subscription name` a name.

<img width="1288" alt="bedrock-redis-rc-10" src="./assets/bedrock-redis-rc-10.png">

`Redis 7.2` is now available for you to choose. This is the latest and greatest offering from Redis. Select it.

<img width="1288" alt="bedrock-redis-rc-11" src="./assets/bedrock-redis-rc-11.png">

Choose a `Region` and a `CIDR`, like what is shown below.

<img width="1288" alt="bedrock-redis-rc-12" src="./assets/bedrock-redis-rc-12.png">

Simply choose default values here.

<img width="1290" alt="bedrock-redis-rc-13" src="./assets/bedrock-redis-rc-13.png">

### Sizing a Redis Database

On the `Sizing` tab, click on `+` button to add a new database.

<img width="1290" alt="bedrock-redis-rc-14" src="./assets/bedrock-redis-rc-14.png">

Give your `database` a name and select `RediSearch` and `RedisJSON` modules.

<img width="1288" alt="bedrock-redis-rc-15" src="./assets/bedrock-redis-rc-15.png">

Depending upon the total number of documents you intend to use in your vector database, you will need to start with a specific data size for your applications. For this exercise, use the approximate sizing table below to help pick a starting point (which you can always adjust up or down later on).

| Total Size of Documents in S3 | Db size w/out replication (no HA) | Db size w/ replication (HA) |
| ------- | ------- | ------- |
| 10,000 KB  | 135 MB  | 270 MB  |
| 100,000 KB  | 1.35 GB  | 2.7 GB  |
| 1,000,000 KB | 13.5 GB | 27 GB |
| 10,000,000 KB | 135 GB | 270 GB |

If you would like to understand the rationale behind the above calculations, please check out [the announcement blog](https://redis.com/blog/amazon-bedrock-integration-with-redis-enterprise/) that has more details.

> Alternatively, you can select a simple minimalistic configuration for now (example: Memory = 1 GB and Throughput Shards = 1) and adjust later.

<img width="1288" alt="bedrock-redis-rc-21" src="./assets/bedrock-redis-rc-21.png">

Once you review the total cost price, and other details, simply click on the `Create subscription` button to create `Redis Enterprise Cloud Flexible` subscription.

<img width="1288" alt="bedrock-redis-rc-22" src="./assets/bedrock-redis-rc-22.png">

The actual subscription creation may take approximately 5 mins to 15mins.

<img width="1288" alt="bedrock-redis-rc-23" src="./assets/bedrock-redis-rc-23.png">

Once the subscription is created, you will see that it is ready with a Green amber light on in the `Status` column.

<img width="1288" alt="bedrock-redis-rc-24" src="./assets/bedrock-redis-rc-24.png">

### TLS Setup for your Redis Database
If you click on the database, the database configuration screen shows that the TLS is turned off by default. Click on Edit button to edit the details.

<img width="1288" alt="bedrock-redis-rc-25" src="./assets/bedrock-redis-rc-25.png">

Go ahead and turn on the TLS (`Annotation 1`). You will download the Cloud certificate authority (Annotation 2).
You will also check `TLS client authentication` (Annotation 3).
You will `Generate certificate` (Annotation 4).
And finally you will click on the `Save database` (Annotation 5).

<img width="1920" alt="bedrock-redis-rc-tls-1" src="./assets/bedrock-redis-rc-tls-1.png">

When you click on `Generate certificate`, you will see the certificate text appearing between `-----BEGIN CERTIFICATE-----` and `-------END CERTIFICATE---------`. (Annotation 1)
Make sure you download the certificates (Annotation 2) before saving the the database configurations.(Annotation 3)

<img width="1920" alt="bedrock-redis-rc-tls-2-generate-client-cert" src="./assets/bedrock-redis-rc-tls-2-generate-client-cert.png">


### Additional Redis database endpoint configurations

Redis Enterprise Cloud on AWS is now ready for your use. Typically, the developers need an endpoint, a user password and the server certificate to connect to the database from their applications.

<img width="1288" alt="bedrock-redis-rc-30" src="./assets/bedrock-redis-rc-30.png">

Redis web console also gives you code snippets on how to connect from different clients. Choose the one that is appropriate to your client applications.

<img width="1288" alt="bedrock-redis-rc-31" src="./assets/bedrock-redis-rc-31.png">

Like mentioned above, here is how you can get the password to your Redis database.
<img width="1290" alt="bedrock-redis-rc-32" src="./assets/bedrock-redis-rc-32.png">


## Next Steps
By now, you have spun up a Redis Enterprise Cloud subscription in AWS and validated the connection. **Next, you will need to [create a vector index](vector-index-creation.md).**

Make sure to hold on to the following details for your database as you will need these for the final integration step.

```
Redis Enterprise Cloud Database Hostname
Redis Enterprise Cloud Database Port Number
Redis Enterprise Cloud Database Password
Redis Enterprise Cloud Database Server & Client certs for TLS
```
