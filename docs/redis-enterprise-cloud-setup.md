-------

# Redis Enterprise Cloud Setup

## Objective
The goal is to deploy Redis Enterprise Cloud as your vector database for AWS Bedrock on the AWS Marketplace. You will create a flexible, pay-as-you-go subscription. If you are new to Redis, **we even give you a 14-day free trial of $500 USD to get started!**

[ TODO - BEDROCK UI REDIS DEPLOYMENT LINK SCREENSHOT]

Link directly from the Bedrock configuration screen seen above, or manually [follow this link] to the AWS Marketplace offering to get started.

## Setup Procedure

### Getting started from AWS Marketplace
Once on the landing page, continue to click on `View purchase options`.

<img width="1296" alt="bedrock-redis-rc-2" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/8de36e98-71bf-49c1-b0b8-640388f6fdde">

On the product page,
1. Click on the `Subscribe` button. This button gets greyed out after you click on it for the first time.
2. Then the banner highlighted at the top, will appear.
3. On this banner, go ahead and click on `Setup your account`.

<img width="1296" alt="bedrock-redis-rc-3" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/947c3a6b-3947-43a2-b88b-ee3ab1585138">

This navigates you to the sign-in page of `Redis Enterprise Cloud` web console.

<img width="1288" alt="bedrock-redis-rc-4" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/3d23a948-44f2-4287-b0e4-47350ce5a42f">

As soon as you sign in , you will see that your `AWS Account` ( example: `Srini 1320974`) is displayed and you will be able to connect this AWS account with Redis Enterprise Cloud web console.
Go ahead and check the selection box highlighted.
<img width="1288" alt="bedrock-redis-rc-5" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/8b7281f1-12d9-4f94-8e35-274137dae51b">

Click `Connect account`. This will connect your AWS account with "Redis Enterprise Cloud" web console.

<img width="1288" alt="bedrock-redis-rc-6" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/bae55fb8-13d4-4900-9a0e-6ae42883a359">

Once connected successfully, you will see a message at the top ( see annotation 1) and now you can get started. In this case, since a "Free Trial" option is chosen, you will see a `Start free trial` option.
Go ahead and click on `Start free trial`.

<img width="1288" alt="bedrock-redis-rc-7" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/d05c6e4a-68ac-4fc8-a9df-c6b387be8c8d">

As soon as you login, you will see this UI. Notice that there is a Free Trial banner at the top. Ignore this banner, if you are not on a promotional free tier.
1. Appearance of `AWS Marketplace` icon, indicates that your Redis account is now connected to your AWS account.
2. On the `Setup` tab, you will see cloud vendors.
3. Select `AWS` if it is not highlighted and selected already.

<img width="1293" alt="bedrock-redis-rc-8" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/bf288185-0864-4780-a168-877828dc0aa0">

### Setting up Redis Subscription

Go ahead and select your `Region` and give `Subscription name` a name.

<img width="1288" alt="bedrock-redis-rc-10" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/9d204251-2399-43a1-a406-869af7769986">

`Redis 7.2` is now available for you to choose. This is the latest and greatest offering from Redis. Select it.

<img width="1288" alt="bedrock-redis-rc-11" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/9337ab30-208e-4e4f-a2d2-c485a0c6fe39">

Choose a `Region` and a `CIDR`, like what is shown below.

<img width="1288" alt="bedrock-redis-rc-12" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/68ac390f-559a-489b-a62f-a3d5216c27f9">

Simply choose default values here.

<img width="1290" alt="bedrock-redis-rc-13" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/544c0942-4515-460f-9706-a56d44f7f0eb">

### Sizing a Redis Database

On the `Sizing` tab, click on `+` button to add a new database.

<img width="1290" alt="bedrock-redis-rc-14" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/5214845a-d3c6-49c1-b3d1-7eec57059876">

Give your `database` a name and select `RediSearch` and `RedisJSON` modules.

<img width="1288" alt="bedrock-redis-rc-15" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/6d449812-b920-4f5e-9f59-cb0e7878df3d">

Depending upon the total number of documents you intend to use in your vector database, you will need to start with a specific data size for your applications. For this exercise, use the approximate sizing table below to help pick a starting point (which you can always adjust up or down later on). Alternatively, you can select a simple minimalistic configuration for now (example: Memory = 1 GB and Throughput Shards = 1).

| Number of Documents | Db size w/out replication (no HA) | Db size w/ replication (HA) |
| ------- | ------- | ------- |
| TODO  | TODO  | TODO  |
| TODO  | TODO  | TODO  |


<img width="1288" alt="bedrock-redis-rc-21" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/3dafeb05-c1d1-411f-bace-7bd5ed921334">

Once you review the total cost price, and other details, simply click on the `Create subscription` button to create `Redis Enterprise Cloud Flexible` subscription.

<img width="1288" alt="bedrock-redis-rc-22" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/f0581b95-a855-46ca-a11f-2eeed535f3d4">

The actual subscription creation may take approximately 5 mins to 15mins.

<img width="1288" alt="bedrock-redis-rc-23" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/e8c82094-81cd-4c06-b519-50dd0bad44fe">

Once the subscription is created, you will see that it is ready with a Green amber light on in the `Status` column.

<img width="1288" alt="bedrock-redis-rc-24" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/36af6ccf-a789-46eb-913e-24f354eee3df">

### TLS Setup for your Redis Database
If you click on the database, the database configuration screen shows that the TLS is turned off by default. Click on Edit button to edit the details.

<img width="1288" alt="bedrock-redis-rc-25" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/3dfae120-a999-450b-a6ed-74260f84e37b">

Go ahead and turn on the TLS (`Annotation 1`). You will download the Cloud certificate authority (Annotation 2).
You will also check `TLS client authentication` (Annotation 3).
You will `Generate certificate` (Annotation 4).
And finally you will click on the `Save database` (Annotation 5).

<img width="1920" alt="bedrock-redis-rc-tls-1" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/4c84d330-5e83-4b8f-8a58-17466f8c3d78">

When you click on `Generate certificate`, you will see the certificate text appearing between `-----BEGIN CERTIFICATE-----` and `-------END CERTIFICATE---------`. (Annotation 1)
Make sure you download the certificates (Annotation 2) before saving the the database configurations.(Annotation 3)

<img width="1920" alt="bedrock-redis-rc-tls-2-generate-client-cert" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/7988ec18-fd4e-4bfd-b883-8d1b5802e8e6">

## Connect with RedisInsight

To test client connections with `TLS` turned on, go ahead and download RedisInsight. This can be done directly by clicking on the `Connect` button on your database. 
Under `RedisInsight Desktop` section, you can see a `Download` drop down for your OS platform. Go ahead and download (Annotation 3)
You will need the `Public endpoint` connection details (Annotation 1 and 2), to connect from RedisInsight.

<img width="1920" alt="bedrock-redis-rc-tls-3-pub-endpoint" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/731a0de8-7a3b-4086-bfb3-cf00085b38a5">

Go ahead and download and install RedisInsight. Here is an example screenshot for Mac OSX. Windows installation may be slightly different but it should be self explanatory.

<img width="602" alt="bedrock-redis-rc-tls-4-redisinsight-install" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/2e0bf35f-e10b-4fc2-b235-59b63807cace">

Once RedisInsight is installed, you are welcomed to the main screen as shown below.

<img width="1278" alt="bedrock-redis-rc-tls-5-ri-welcome" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/81ea5180-f0ea-44e7-89eb-8a8fd621da9e">

Click on the `Add Database Manually`

<img width="1278" alt="bedrock-redis-rc-tls-6-ri-add-db" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/116236bb-4250-41e5-8cde-9a8b0ceec085">

Copy the details of the `Public endpoint`

<img width="1404" alt="bedrock-redis-rc-tls-7-ri-cp-ep" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/12408700-6656-426d-a7e0-887c70a30e51">

And paste the details by placing your cursor in the `Database Alias` (Annotation 1). Rest of the fields like `Username`, `Password` etc, gets automatically filled in. (Annotation 2)

Since we enabled `TLS` (both serverside and client side), we need to let RedisInsight know to present the certificates to connect to the Redis endpoints. To do this, you will select TLS checkbox ON (Annotation 3) and select `Add new CA certificate` (Annotation 4)

<img width="1265" alt="bedrock-redis-rc-tls-8-ri-pst-ep" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/6acc932d-00ec-4221-9e9c-992b5ab64528">

Copy the contents of `redis_ca.pem` file. Make sure to include the entire contents of the file, including `----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----` etc.

<img width="802" alt="bedrock-redis-rc-tls-9-ri-ca-cp" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/cca7ad50-f8a9-4ae2-b967-172538a9c238">

And past the contents in the `Certificate` textbox as shown.

<img width="1269" alt="bedrock-redis-rc-tls-10-ri-ca-pst" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/33334971-6760-44b3-8565-ab47b466225e">

Similarly, go ahead and copy the contents of the client certificates and paste it in the RedisInsight : `Requires TLS Client Authentication` section.

<img width="1269" alt="bedrock-redis-rc-tls-11-ri-client-cert-cp" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/bf4efcf9-3b1b-4e60-97be-9e7d1afc40e7">

<img width="1269" alt="bedrock-redis-rc-tls-12-ri-client-cert-priv-cp" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/dbbce9c8-7a3b-443d-93f2-3ee3ae2762bc">

<img width="1269" alt="bedrock-redis-rc-tls-13-ri-client-cert-pst" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/bd89fdac-57a9-422a-ad5e-19d3db1edda5">


Once you click on `Add Redis Database` button, you will see that your database has been added successfully.

<img width="1269" alt="bedrock-redis-rc-tls-14-ri-done" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/927e6043-e57c-4288-ba1d-72d6e6e900bb">

Click on the database to connect. Since the database is all empty, when you search for keys, you will not find any data.

<img width="1269" alt="bedrock-redis-rc-tls-15-ri-query" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/0bd5f6c1-c640-4fa9-925f-9f709cada53b">


That is it, you are all set with Redis setup and connecting to the Redis datbase using a Redis Client like RedisInsight.


### Additional Redis database endpoint configurations

Redis Enterprise Cloud on AWS is now ready for your use. Typically, the developers need an endpoint, a user password and the server certificate to connect to the database from their applications.

<img width="1288" alt="bedrock-redis-rc-30" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/0a8a13b6-4a7b-421f-a900-0186d2391d75">

Redis web console also gives you code snippets on how to connect from different clients. Choose the one that is appropriate to your client applications.

<img width="1288" alt="bedrock-redis-rc-31" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/8946edae-e0d4-4e86-8ac9-e9d38bebe618">

Like mentioned above, here is how you can get the password to your Redis database.
<img width="1290" alt="bedrock-redis-rc-32" src="https://github.com/RedisVentures/aws-redis-bedrock-stack/assets/6223831/15671058-1040-4f9b-8858-9669970c6112">


## Next Steps
By now, you have spun up a Redis Enterprise Cloud subscription in AWS and validated the connection. **Next, you will need to [create a vector index](vector-index-creation.md).**

Make sure to hold on to the following details for your database as you will need these for the final integration step.

```
Redis Enterprise Cloud Database Hostname
Redis Enterprise Cloud Database Port Number
Redis Enterprise Cloud Database Password
Redis Enterprise Cloud Database Server & Client certs for TLS
```
