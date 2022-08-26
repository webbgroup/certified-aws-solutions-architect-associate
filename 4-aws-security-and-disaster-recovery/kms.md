# KMS
- Anytime you hear "encryption" for an AWS service, its most likely KMS
- Easy way to control your data, AWS manages keys for us
- Fully integrated into IAM for authorization
- Seamlessly integrated into:
	- Amazon EBS: encrypt volumes
	- Amazon S3: Server side encryption of objects
	- Amazon Redshift: encryption of data
	- Amazon RDS: encryption of data
	- Amazon SSM: Parameter store

- But you can also use it with the Command Line Interface and Software Development Kits


## KMS - Customer Master Key(CMK) Types

* Symmetric (AES-256 keys)
	- First offering of KMS, single encryption key that is used to Encrypt/Decrypt
	- AWS services that are integrated with KMS use Symmetric CMK's
	- Necessary for envelope encryption
	- You never get access to the Key unencrypted (must call KMS API to use it)
* Asymmetric (RSA & ECC key pairs)
	- Public (Encrypt) and Private Key (Decrypt) pair