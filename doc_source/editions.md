# Editions<a name="editions"></a>

Amazon QuickSight offers Standard and Enterprise editions\. Use this topic to learn more about the differences in availability, user management, permissions, and security between the two versions\. 

Both editions offer a full set of features for creating and sharing data visualizations\. Enterprise edition additionally offers encryption at rest and Microsoft Active Directory \(AD\) integration\. In Enterprise edition, you select a Microsoft AD directory in AWS Directory Service\. You use that active directory to identify and manage your Amazon QuickSight users and administrators\. 

For more information about the features offered by the Amazon QuickSight editions and also pricing, see [Amazon QuickSight](https://quicksight.aws)\. 

## Availability<a name="edition-availability"></a>

Currently, you must choose the US East \(N\. Virginia\) Region as your Amazon QuickSight capacity region if you want to use Amazon QuickSight Enterprise edition\. The Microsoft AD directory you select to integrate with Amazon QuickSight must reside in that region\. This region is also where default SPICE capacity for your account is allocated\. You can still access AWS resources in any AWS Region, and also purchase SPICE capacity in any region supported by Amazon QuickSight\.

## User Management<a name="edition-user-management"></a>

User management is different between the Amazon QuickSight Standard and Enterprise editions\. Both editions support identity federation, or federated single\-signon \(SSO\), through Security Assertion Markup Language 2\.0 \(SAML 2\.0\)\.

\.

### User Management for Standard Edition<a name="edition-user-management-standard"></a>

In Standard edition, you can invite an AWS Identity and Access Management \(IAM\) user and allow that user to use their credentials to access Amazon QuickSight\. Alternatively, you can invite any person with an email address to create an Amazon QuickSight–only user account\. When you create a user account, Amazon QuickSight sends email to that user inviting them to activate their account\. 

When you create a user account, you also choose to assign it either an administrative or a user role\. This role assignment determines the user's permissions in Amazon QuickSight\. You perform all management of users by adding, changing, and deleting user accounts in Amazon QuickSight\. 

For more information about managing Standard edition user accounts, see [Managing User Accounts in Amazon QuickSight Standard Edition](managing-users.md)\.

### User Management for Enterprise Edition<a name="edition-user-management-enterprise"></a>

In Enterprise edition, you can select one or more Microsoft AD active directory groups in AWS Directory Service for administrative access\. All users in these groups are authorized to sign in to Amazon QuickSight as administrators\. You can also select one or more Microsoft AD active directory groups in AWS Directory Service for user access\. All users in these groups are authorized to sign in to Amazon QuickSight as users\. 

**Important**  
Administrators and users added in this way are not automatically notified of their access to Amazon QuickSight\. You must email users with the sign\-in URL, the account name, and their credentials\.

You can only add or remove Enterprise edition user accounts by adding or removing a person from a Microsoft AD group that you associated with Amazon QuickSight\. When you add a user account, the permissions it gets rely on whether the Microsoft AD group is an administrative group or a user group in Amazon QuickSight\. 

You can also bulk add or remove user accounts by integrating Microsoft AD groups with, or removing Microsoft AD groups from, Amazon QuickSight\. 

Deactivating a user by removing the user from a Microsoft AD group, or by removing their Microsoft AD group from integration with Amazon QuickSight, doesn't delete the associated Amazon QuickSight user account for that person\. 

For more information about managing Enterprise edition user accounts, see [Managing User Accounts in Amazon QuickSight Enterprise Edition](managing-users-enterprise.md)\.

## Permissions<a name="edition-permissions"></a>

For Standard edition, all Amazon QuickSight administrative users have permissions to manage subscriptions and SPICE capacity\. They can also add, modify, and delete user accounts\. 

Additional AWS permissions are required to manage Amazon QuickSight permissions to AWS resources and to unsubscribe from Amazon QuickSight\. These tasks can only be performed by an IAM user who also has administrative permissions in Amazon QuickSight, or by the IAM user or AWS account that created the Amazon QuickSight account\.

For Enterprise edition, all Microsoft AD users that are added as Amazon QuickSight administrative users have permissions to manage subscriptions and SPICE capacity\. In Enterprise edition, you must add AD users or groups to an IAM role that has QuickSight permissions, rather than adding IAM users individually\.

Additional AWS permissions are required to manage Microsoft AD groups and Amazon QuickSight permissions to AWS resources, and to unsubscribe from Amazon QuickSight\. The administrative user is prompted for AWS or IAM credentials to perform these tasks\.

For more information about the permissions needed for tasks that affect AWS resources, see [Setting Your IAM Policy](set-iam-policy.md)\.

## Secure Transmission and Storage<a name="security"></a>

In both editions of Amazon QuickSight, all transfers of data \(for example, from the data source to SPICE, or from SPICE to the user interface\) are encrypted\. Database connections are secured using Secure Sockets Layer \(SSL\), and all other transfers are secured using Transport Layer Security \(TLS\)\.

In Enterprise edition, data at rest in SPICE is also encrypted using block\-level encryption with AWS\-managed keys\.