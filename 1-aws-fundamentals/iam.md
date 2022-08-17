# IAM Fundamentals

* Don't use the root user account unless it is for Initial Account setup
* One account = one physical user ( No Sharing )
* Assign users to groups. No Nested groups
* Multi-factor and MFA is needed
* Create Roles for giving permissions to access AWS Services, and test it with Policy Simulator
* Use Access Keys for Programmatic Access (CLI/SDK)
* Audit permissions using IAM Credentials Report
* Never share your access keys and IAM user accounts


IAM Policy

* A statement in an IAM Policy consists of:
- Sid,
- Effect,
- Principal,
- Action,
- Resource,
- Condition. Version is part of the IAM Policy itself, not the statement.

