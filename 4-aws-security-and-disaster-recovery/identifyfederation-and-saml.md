# Identity Federation in AWS

- Federation allows users outside of AWS to assume temporary role for accessing AWS resources.
- These users assume identity provided access role.

- Federations can have many flavors:
    * SAML 2.0
    * Custom Identity Broker
    * Web Identity Federation with Amazon Cognito
    * Web Identity Federation without Amazon Cognito
    * Single Sign-On
    * Non-SAML with AWS Microsoft AD

- Using Federation, you don't need to create IAM users
(user management is outside of AWS)


# SAML 2.0 Federation
- To integrate Active Directory / ADFS with AWS (or any SAML 2.0)
- Provides access to AWS Console or CLI (through temporary creds)
- No need to create an IAM user for each of your employees

- Needs to set up a trust between AWS IAM and SAML ( both ways)
- SAML 2.0 enables web-based, cross domain SSO
- Uses the STS API:AssumeRoleWithSAML

NOTE: federation through SAML is the old way of doing things
- Amazon Single Sign On SSO Federation is the new managed and simpler way
