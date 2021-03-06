# Vipps Developer Portal: Getting Started

These are the steps after you have received in the onboarding email from Vipps.
You should have received proper credentials with username on email and password on the admin-phonenumber.
Use those credentials to log into Vipps Developer Portal in either Test or Production.

For in-depth information about the Vipps Developer Portal, see the PDF manual: https://github.com/vippsas/vipps-developers

**Please note:** _We have recently updated the colors for the Test (purple) and Production (orange) environments.
The screenshots in the documentation have not yet been updated, but the functionality is unchanged._

# Step 0

Make sure you have an active subscription to the relevant Vipps product(s): https://www.vipps.no/bedrift

We have sign-up pages for those who know what they want (https://vippsbedrift.no/signup/)
and also a "Find your Vipps" product selector: https://www.vipps.no/bedrift/vippshjelper.

For general questions about products, please use the contact form: https://www.vipps.no/bedrift/kontakt-oss

# Step 1

We start with the main page for the Test portal (https://apitest-portal.vipps.no/) and the sign-in screen:

![Frontpage](images/devportal-test-home.png)

![Sign in](images/devportal-test-signin.png)

You type in your username and password here:

![Sign in](images/devportal-test-login-username.png)

Please note the difference between the Test and Production environments,
both in appearance and login credentials:

## Test environment: Purple

The test environment has a purple header:

![Vipps Developer Portal: Test](images/devportal-test-home.png)

* Vipps Developer Portal URL: https://apitest-portal.vipps.no/
* A username that looks like this: username@**testapivipps**.no
* A default password.

## Production environment: Orange

The test environment has an orange header:

![Vipps Developer Portal: Production](images/devportal-prod-home.png)

* Vipps Developer Portal URL: https://api-portal.vipps.no/
* A username that looks like this: username@**apivipps**.no`
* A default password.

For password changes in either test or production, please [contact us](contact.md).

## Remember to log out of other Microsoft accounts

![Azure Error](images/devportal-test-login-azure-error.png)

If you get an error page similar to the one above:

1. Make sure that you are logged out of any Microsoft accounts, such as Office 365 accounts, _**or**_ make sure you are in "incognito mode" or "private window" in your browser.
2. Make sure you are using the correct URL and credentials for the Vipps Developer Portal: Test or Production.

# Step 2

After an successful log in you will see the account name up in the right corner of the screen ("FIRSTNAME LASTNAME" in this example). On the left you have several tabs.
The **"MANAGE USERS"** tab allows you to add users:

When adding a new developer, note that we don't support non-Latin characters such as
_**æ**_,_**ø**_,_**å**_. Adding a name like "_**Bjørn**_" will result in error.
This can be solved by using "_**Bjorn**_" instead.

![Users](images/devportal-test-users.png)

![Users: Add](images/devportal-test-users-add.png)

# Step 3

The next tab **"PRODUCTS"** shows you the APIs you currently have. As you see from the picture below you can have multiple products:

![Products](images/devportal-test-products.png)

You may have several APIs available.
In this example we will use `eCommerce-Express-Checkout-Signup-Login-Services`,
and this page is shown after you click the product name:

![Test the API(s)](images/devportal-test-products-ecommerce.png)

Click on the **"Try it"** button:
![Try it](images/devportal-test-getorderstatus-tryit.png)

Click on the **"TEST THE API(S)"** button (in this example: `GetOrderStatus_v2`):

![Test: Access Token](images/devportal-test-getorderstatus-0.png)

Add the the proper keys to initiate your request:

![Test: Access Token](images/devportal-test-getorderstatus-1.png)

![Test: Access Token](images/devportal-test-getorderstatus-2.png)

# Step 4

To get your API keys, open the **"APPLICATIONS"** tab (in a new browser tab)
and click on the correct sale unit number (Merchant Serial Number: MSN).
You will find both `client_id` and `client_secret`.

![Applications](images/devportal-test-applications.png)

![keys applications](images/devportal-test-applications-viewsecrets.png)

Under the tab **"REGISTER APPLICATION"** it should say, marked in red: 'All existing products have been subscribed':

![registerapplication](images/devportal-test-registerapplication.png)

If you need more Vipps applications, please contact integration@vipps.no.

# Step 5

Under the profile tab (the account name at the top right, "FIRSTNAME LASTNAME" in this example) you will find your two last keys:

* DEFAULT_ACCESSTOKEN
* ECOMMERCE-Vipps Integration XXXX (where XXXX is your MSN):

![Profile](images/devportal-test-profile.png)

Click "Show" to view the values:

![Profile: Keys shown](images/devportal-test-profile-subkey-show.png)

## Access tokens

You have the `Access Token` key on the top. You have to click "Show" on the right side to make the keys appear.
It is the `Primary key` you are after.
The `Secondary key` is only needed if you are changing installations or regenerating keys. They are normally not used.
If the key for some reason does not work, then you can hit "Regenerate", right next to "Show".

## Subscription keys
The `Ocp-Apim-Subscription-Key` is right below the `Access Token` key. You have to click "Show" on the right side to make the keys appear. And as marked in yellow, you can use
the `Primary key` or the `Secondary key`.

## Merchant serial number

The `MerchantSerialNumber` (MSN) is the number right next to the name of your Salesunit, `210575` in this example.

## Summary

Now you should have `Client_id`, `Client_secret`, `Access Token Subscription Key`, `Product Subscription Key` and `merchantSerialNumber`.

**Important**: While doing payments you will use the `Product Subscription Key` and when getting the access token you will use the `Access Token Subscription Key`.
