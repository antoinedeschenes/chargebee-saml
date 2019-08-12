## Setup Chargebee SSO with Azure AD

1. Login to the [Azure Portal](https://portal.azure.com/) 
2. Reach the [Enterprise applications](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AllApps/menuId/) page

![Enterprise applications](1-azure-apps.png)

3. Create a "New application"

![New application](2-azure-add-app.png)

4. Select "Non-gallery application", name and add your application. 

![Add application](3-azure-name-app.png)

5. Go in the "Single sign-on" settings and click "SAML"

![Use SAML](4-azure-use-saml.png)

6. Set the "Basic SAML Configuration":
  - Identifier (Entity ID) is your Chargebee subdomain (`https://<domain>.chargebee.com/`)
  - Set Reply URL (Assertion Consumer Service URL) to the following: `https://app.chargebee.com/saml/<domain>/acs`

![Configure SAML (Azure)](5-azure-configure-saml.png)

7. Get the "Login URL" and download the "Certificate"

![Get SAML config for Chargebee](6-azure-get-attributes.png)

8. Connect to your [Chargebee](https://app.chargebee.com) account 
9. Reach the SAML settings

![Use SAML (Chargebee)](7-chargebee-use-saml.png)

10. Fill the SAML configuration
  - Paste "Login URL" from the Azure application page.
  - Paste contents from downloaded Certificate (Base64) in the Chargebee "SAML Certificate" text box
  - Click "Confirm"

![Configure SAML (Chargebee)](8-chargebee-configure-saml.png)

11. In Azure, click "Users and groups" to allow users to login to the Chargebee application

![Assign users (Azure)](9-azure-assign-users.png)
