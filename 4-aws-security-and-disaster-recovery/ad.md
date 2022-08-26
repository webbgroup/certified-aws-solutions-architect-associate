# Active Directory

- Found on any Windows Server with AD Domain Services
- Database of Users, Accounts, Computers, Printers, File Shares, Security Groups
- Centralized Security Management, create account, assigned permissions
- Objects are organized in large trees
- A group of trees is called a forest

## AWS Directory Services

AWS Managed Microsoft AD
- Create your own AD in AWS, managed user locally, supports MFA
- Establish trust connections with your own on-premise AD

AD Connector
- Directory Gateway (proxy) to redirect to on-premise AD, supports MFA
- Users are managed on the on-premise AD

## Simple AD
- AD-compatible managed directory on AWS
- Cannot be joined with on-premise AD