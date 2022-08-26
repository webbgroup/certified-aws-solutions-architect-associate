# Advanced IAM

## AWS STS - Security Token Service

- Allows to grant limited and temporary access to AWS resources
- Token valid for up to one hour (must be refreshed)
- STS most important APIs:
    - **AssumeRole**:
        - Usage within our account: for temporary enhanced security
        - Cross account: assume role on target account to perform actions there
    - **AssumeRoleWithSAML**:
        - Return credentials for user logging in with SAML
    - **AssumeRoleWithWebIdentity**:
        - Return credentials for users logged in with IdP (Facebook login, Google login, OIDC)
        - AWS recommends against using this, use Cognito instead
    - **GetSessionToken**:
        - Fro MFA, from an user or AWS account root user

## Using Security Token Service to Assume a Role

1. Define an IAM Role within an account or cross-account
2. Define which principals can access this IAM Role
3. Use AWS STS to retrieve credentials and impersonate the IAM Role you have access to (AssumeRole API)
4. Temporary credentials will be valid for 15 minutes up to 1 hour

## Basically for BreakGlass Elevated Privileges


## IAM Conditions

- Allows you to restrict where the AIM calls are coming from
- Can Deny from a CIDR/Region or Allow from CIDR/Region
- Can also have Deny/Allow based on string conditions MultiFactorAuthPresent


## IAM for S3
 - Bucket Resource Permissions can be directory itself  "test"
 - But GetObject,PutObject,DeleteObject applies to "test/*"


## IAM Permission Boundaries

- You can remove writes easily, by simply providing global access, THEN using a permission boundary to revoke access elsewhere.

## IAM Permissions Evaluation Logic

- https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html#policy-eval-denyallow


## AWS Resource Access Manager (RAM)

Allows multiple accounts to share the same resources within the same VPC.

## AWS Single Sign-On

- Centrally manage Single Sign-On to access multiple accounts and 3rd party business applications
- Integrated into AWS Organizations
- Supports SAML 2.0 Markup
- Integration with on-premise Active Directory
- Centralized permission management
- Centralized auditing with CloudTrail