# Reference material for Exercise B (Improve this)

Create a cloud RADIUS server without the hassle of physical servers. You can quickly roll out RADIUS service to your org to securely authenticate users to Wi-Fi, VPNs, switches, network devices, etc. Orgs can also enable RADIUS access using Entra ID credentials or JumpCloud for the identity provider. When using JumpCloud, the authentication method options include a passwordless method using certificates. This article outlines the steps for configuring and authenticating a RADIUS server.

To add a RADIUS server, start by logging into the JumpCloud Admin Portal, after which you will go to User Authentication and then Radius. To create a new RADIUS server configuration, click ( + ).

To configure the RADIUS server, enter a name for the server. This value can be anything you want it to be. In the Shared Secret field, provide a shared secret for the device or service endpoint you're pairing with the RADIUS server. Enter one or more public IP addresses and what that means is that is where your org's traffic will originate. If you want to enter the IP address based on your current location, click Yes below the IP Addresses textbox. The IP address is auto-populated. Don’t forget to click Save. Oh, and the RADIUS server doesn’t become operational until you add it to a user group. Oh, if you want to add multiple IP addresses to the same RADIUS server configuration, just simply click Add IP Address.

To set up primary authentication. Choose an identity provider select how your users will authenticate into this RADIUS server, click the Authentication tab and select an identity provider from the dropdown. JumpCloud is the default option.

If you select Entra ID, users can access the RADIUS server using their existing Entra ID credentials. MFA can’t be configured when Entra ID is the identity provider.

Oh, this is important, once Entra ID is selected and confirmed, this selection can’t be changed without deleting this RADIUS configuration and starting over also Entra ID doesn’t pass the user’s password to JumpCloud, so the user remains in a Password Pending status. If an Entra ID org is using JumpCloud exclusively for RADIUS, Admins don’t require users to create a password in JumpCloud, so the Password Pending status can be ignored.

RADIUS Authentication with Entra ID Credentials

If the selection is JumpCloud, Admins have the choice of Passwordless or Password for the Authentication Method.

How to Choosing an Authentication Method:

JumpCloud RADIUS supports both credential (with a password) and certificate (passwordless) based authentication. Though it requires additional steps, Certificate Based Authentication (CBA) is considered the most secure method of authentication, with the least amount of user friction. You might want to look up our Certificate Based Authentication to RADIUS for Admins article to learn more.

Before you can do any of the steps in this article you will probably need to configure your RADIUS setup, which can be a WAP, VPN, or through a Router. We also have a document for technical consideration you might want to check out.
