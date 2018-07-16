## Setup Red Hat Single Sign-on

{% hint style='info' %}
In this part of the lab, you will setup all the required configurations to make RH-SSO work with 3scale API Management.
{% endhint %}

* Go to **https://sso.{{ book.suffix }}/auth/admin**
* Accept the self-signed SSL certificate.
* Login as **admin/passwod**.

![](../assets/Selection_442.png)

* Make sure the **3scaleRealm** realm is selected.
* Click on the **Login** tab.
* Select **none** for the **Require SSL** field.
* Click on the **Save** button.

![](../assets/Selection_459.png)

* Click on **Clients**.
* Click on the **Create** button.

![](../assets/Selection_443.png)

* Enter the following values:
    * **Client ID**: 3scale-client
    * **Client Protocol**: openid-connect
* Click on the **Save** button.

![](../assets/Selection_444.png)

* Set the following parameters:

| Parameter | Value |
| --- | --- |
| **Access Type** | confidential |
| **Standard Flow Enabled** | OFF |
| **Direct Access Grants Enabled** | OFF |
| **Service Accounts Enabled** | ON |

* Click on the **Save** button.

![](../assets/Selection_445.png)

* Click on the **Service Account Roles** tab.
* Select **realm-management** in the **Client Roles** drop-down.
* Select **manage-clients** in the **Available Roles** list.
* Click on the **Add selected >>** button.

![](../assets/Selection_446.png)

* Click on the **Credentials** tab.
* Take note of the **Secret**, you will need it later.

![](../assets/Selection_447.png)

* Click on **Users** (under **Manage**).
* Click on the **Add user** button.

![](../assets/Selection_448.png)

* Enter **user1** as the **Username**.
* Click on the **Save** button.

![](../assets/Selection_449.png)

* Click on the **Credentials** tab.
* Enter "password" as **New Password** and **Password Confirmation**.
* Set **Temporary** to **OFF**.
* Click on the **Reset Password** button.

![](../assets/Selection_450.png)

* Accept the warning.




