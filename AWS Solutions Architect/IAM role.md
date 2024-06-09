**IAM-credentials-report**: Account level lists the users and the status of their credentials

**IAM-access-advisor**:  User level shows the services permissions granted to a user and when they lasted used them

**notes**: credentials-report: download as a csv file next rotation password last change keys mfa active access advisor: can use to see what access a user has and revok uneeded access

# IAM guidelines and best practices
**one**: Don't use the root account except for initial setup

**two**: One person is one aws user

**three**: strong passowrd

**four**: enable mfa

**five**: create and use roles for giving permissions to aws services

**six**: Will have to use access keys for the CLI 

# questions
**An IAM policy consists of one or more statements. A statement in an IAM Policy consists of the following, EXCEPT**: A statement in an IAM Policy consists of Sid, Effect, Principal, Action, Resource, and Condition. Version is part of the IAM Policy itself, not the statement.

**two**: What is the IAM access advisor?

**three**: What are some IAM guidelines and best practices?

