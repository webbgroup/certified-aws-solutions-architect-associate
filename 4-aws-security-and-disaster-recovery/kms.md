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
	- Used for Encrypt/Decrypt, or Sign/Verify operations
	- The public key is downloadable, but you cant access the Private Key unencrypted


## AWS Key Management Service (KMS)

- Able to fully manage the keys and policies
	* Create
	* Rotation polices
	* Disable
	* Enable
- Able to audit key usage (using CloudTrail)
- Three types of Customer Master Keys (CMK)
	- AWS Managed Service Default:free
	- User keys created in KMS $1/month
	- User keys imported (must be 256-bit symmetric key) $1/month
- + Pay for API calls to KMS ($0.03/1000 calls)

## AWS KMS 101

- Anytime you need to share information.... use KMS
	- Database passwords
	- Credentials to external services
	- Private Key of SSL certificates

- The value in KMS is that the CMK used to encrypt data can never be retrieved by the user, and the CMK can be rotated for extra security

* Never store your secrets in plaintext, especially in your own code!
* Encrypted secrets can be stored in the code/environmental variables
* KMS can only help in encrypting up to 4KB of data per call
* If data > 4KB, use envelope encryption

* To give access to KMS to someone:
	- Make sure the Key Policy allows the user
	- Make sure the IAM Policy allows the API calls

# KMS Key Policies
- Control access to KMS keys, "similar" to S3 bucket policies
- Difference: you cannot control access without them

* Default KMS Key Policy:
	- Created if you don't provide a specific KMS Key Policy
	- Complete access to the key to the root user = entire AWS account
	- Gives access to the IAM policies to the KMS key
* Custom KMS Key Policy:
	- Define users, roles that can access the KMS key
	- Define who can administer the key
	- Useful for cross-account access of your KMS key







