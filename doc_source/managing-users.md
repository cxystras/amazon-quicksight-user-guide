# Managing User Accounts in Amazon QuickSight Standard Edition<a name="managing-users"></a>

Use this topic to learn more about managing user accounts in Amazon QuickSight Standard edition\. For information about managing user accounts in Amazon QuickSight Enterprise edition, see [Managing User Accounts in Amazon QuickSight Enterprise Edition](managing-users-enterprise.md)\.

If you have administrative privileges in Amazon QuickSight, you can create and delete user accounts\. You can create user accounts based on AWS Identity and Access Management \(IAM\) credentials, or you can create Amazon QuickSight\-only user accounts using the email address of the user\. You can't create Amazon QuickSight user accounts using non\-IAM AWS credentials\.

Each Amazon QuickSight Standard edition account can have up to 100 user accounts, including the AWS root account or IAM account that created the Amazon QuickSight account\. If you need an exception to this limit, follow the instructions at [AWS Service Limits](http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html) to submit a limit increase request\.

Use the following procedures to add, view, and delete Amazon QuickSight Standard edition user accounts\.

## Inviting Users to Access Amazon QuickSight<a name="inviting-users"></a>

You can invite any person with a valid email address to use Amazon QuickSight\. When they sign up, a new Amazon QuickSight\-only user account is created for them\. You can also invite IAM users in your AWS account to use Amazon QuickSight\. In this case, they can use their IAM credentials to sign in to Amazon QuickSight\. Any IAM user you invite must have a password associated with their IAM credentials, and you must also have an email address for them\. 

User accounts are created in two steps\. First, you invite a user to join Amazon QuickSight\. This creates an inactive user account in Amazon QuickSight, and sends an invitation email to the user\. When the user accepts the invitation and signs in for the first time, the user creates a password to activate the user account\.

For information about signing in for the first time as an invited user, see [Getting Access as a New Amazon QuickSight Standard Edition User](request-access.md#request-access-standard)\.

Use the following procedure to invite a user to access Amazon QuickSight\.

1. Choose your user name on the application bar and then choose **Manage QuickSight**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/admin-menu.png)

1. Choose **Manage Users**\.

1. Choose **Invite users**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/invite-users.png)

1. In the **Type an IAM user name or email** box, type the IAM user name or the email address of a person to whom you want to grant access to Amazon QuickSight and then press **Enter**\. Note that a user's IAM user name may be the same as their email address, and this is fine\.

   Repeat this step until you have entered information for everyone you want to invite\.

1. For **Email**, type an email address for the user account\.

1. For **IAM User**, verify that it says **Yes** for accounts that are associated with IAM users, and **No** for those that are Amazon QuickSight\-only\.

1. For **Role**, choose the role to assign to each person you are inviting\. A role determines the permission level to grant to that user account\.

   + Choose **USER** if you want the user to be able to use Amazon QuickSight but not perform any administrative tasks like managing users or purchasing SPICE capacity\.

   + Choose **ADMIN** if you want the user to be able to both use Amazon QuickSight and perform administrative tasks\.

     There are some differences in what administrative tasks IAM admin users and Amazon QuickSight admin users can perform, because some administrative tasks require permissions in AWS, which Amazon QuickSight\-only users lack\.

     + Amazon QuickSight admin users can manage users, SPICE capacity, and subscriptions\. 

     + IAM admin users can manage users, SPICE capacity, and subscriptions as well\. They can also manage Amazon QuickSight permissions to AWS resources, and unsubscribe from Amazon QuickSight\.

   If you are creating an IAM admin user, check with your AWS administrator and make sure that user has the all necessary statements in their IAM permissions policy to work with Amazon QuickSight resources\. For more information about what statements are required, see [Setting Your IAM Policy](set-iam-policy.md)\.

1. Choose **Invite**\.

## Resend an Invitation to a User<a name="resend-invitation"></a>

The sign\-up URL in the invitation email expires after 24 hours\. Use the following procedure if you need to resend an invitation to someone\.

1. Choose your user name on the application bar and then choose **Manage QuickSight**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/admin-menu.png)

1. Choose **Manage Users**\.

1. Find the entry for the person you want to re\-invite, and choose **Resend invitation**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/resend-email.png)

1. Choose **Confirm**\.

## Viewing User Account Details<a name="view-user-accounts"></a>

After a user account is created, you can view the account on the **Manage Users** page\. Use the following procedure to view a user account\.

1. Choose your user name on the application bar and then choose **Manage QuickSight**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/admin-menu.png)

1. Choose **Manage Users**\.

1. Locate the user account you want view\.

   You can browse, or you can search to locate a specific user account by typing a search term into **Search for a user**\. Any user account email address that starts with the search term is shown\. Search is case\-insensitive and wildcards are not supported\. To clear the search results and view all user accounts, delete the search term\.

1. You can review the user name, email, assigned role, and status\. The status field shows either **ACTIVE** or **INACTIVE** to indicate whether or not the user has responded to the invitation email and activated an account\.

## Deleting a User Account<a name="delete-a-user-account"></a>

Use the following procedure to delete a user account\.

1. Choose your user name on the application bar and then choose **Manage QuickSight**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/admin-menu.png)

1. Choose **Manage Users**\.

1. Locate the user account you want to delete and then choose the delete icon\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/delete-user.png)

1. Choose to either delete or transfer any resources owned by the user and then choose **OK**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/xfer-user1.png)

1. Do one of the following:

   + If you chose to transfer user resources, type the user name of the account to transfer them to and then choose **Delete and transfer resources**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/xfer-user2.png)

   + If you chose to delete user resources, choose **Delete**\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/quicksight/latest/user/images/xfer-user3.png)