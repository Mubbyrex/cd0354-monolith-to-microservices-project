#Project Walkthrough

### 1. Database

I create a PostgreSQL database on AWS RDS. The database is used to store the application's metadata.

- We will need to use password authentication for this project. This means that a username and password is needed to authenticate and access the database.
- The port number will need to be set as `5432`. This is the typical port that is used by PostgreSQL so it is usually set to this port by default.

| Field                                                | Value                                                                              |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------- |
| Database creation method                             | Standard create. Easy create option creates a private database by default          |
| Engine option                                        | PostgreSQL 12 or higher                                                            |
| Templates                                            | Free tier                                                                          |
| DB instance identifier, master username and password | Your choice                                                                        |
| DB instance class                                    | Burstable classes with minimal size                                                |
| Database name                                        | postgres                                                                           |
| VPC and subnet                                       | Default                                                                            |
| Public access                                        | YES. Allows application running outside of your AWS account discover the database. |
| VPC security group                                   | Either choose default or create a new one                                          |
| Availability Zone                                    | No preference                                                                      |
| Database port                                        | 5432 (default)                                                                     |

### 2. S3 Bucket creation

I created an AWS S3 bucket. The S3 bucket is used to store images that are displayed in Udagram.
I added a policy in json format to my bucket

```
{
 "Version":"2012-10-17",
 "Statement":[
     {
         "Sid":"Stmt1625306057759",
         "Principal":"*",
         "Action":"s3:*",
         "Effect":"Allow",
         "Resource":"arn:aws:s3:::my-467286114294-bucket"
     }
 ]
}
```

I also added configured CORS

````
[
	{
		"AllowedHeaders":[
			"*"
		],
		"AllowedMethods":[
			"POST",
			"GET",
			"PUT",
			"DELETE",
			"HEAD"
		],
		"AllowedOrigins":[
			"*"
		],
		"ExposeHeaders":[

		]
	}
]```
````
