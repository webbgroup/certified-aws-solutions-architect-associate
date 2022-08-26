# AWS Organizations

- Global Service
- Allows to manage multiple AWS accounts
- The main account is the master account - you can't change it
- Other accounts are member accounts
- Member accounts can only be part of one organization
- Consolidated Billing across all accounts - single payment method
- Pricing benefits from aggregated usage (Volume discount for EC2,S3)
- API is available to automate AWS account creation

## Multi Account Strategies
- Create accounts per department, per cost center, per dev/test/prod, based on regulatory restrictions (SCP), for better resource isolation VPC, to have a separate per-account service limits, isolated account for logging.

- Multi-Account vs One Account Multi VPC
- Use tagging standards for billing purposes
- Enable CloudTrail on all accounts, send logs to central S3 account
- Send CloudWatch Logs to central logging account
- Establish Cross Account Roles for Admin purposes


# Strategies

- Business Unit
 * Sales OU
 * Retail OU
 * Finance OU

- Environmental Lifecycle
	* Production OU
	* Development OU
	* Test OU

- Project Based
	* Project 1 OU
	* Project 2 OU
	* Project 3 OU


# Organization

Master Account
|- Dev OU
	*	Account 1
	* Account 2
|- Prod OU
	* Account 1
	* Account 2
	|- Finance OU
		* Account 1

# Service Control Policies

- Whitelist or Blacklist IAM actions
- Applied at the OU or Account Level
- Does not apply to the Master Account
- SCP is applied to Users and Roles of the Account, Including Root
- SCP must have a explicit Allow (does not allow anything by default)

# Migrations

1. Remove the user from old Org
2. Send a new invite to the New
3. User needs to accept the invite to the new
