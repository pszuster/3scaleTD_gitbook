## Setup Red Hat Single Sign-on

{% hint style='info' %}
In this part of the lab, you will setup all the required configurations to make RH-SSO work with 3scale API Management.
{% endhint %}

* Go to **https://sso.{{ book.suffix }}/auth/admin**
* Accept the self-signed SSL certificate.
* Login as **admin/passwod**.

![](../assets/Selection_442.png)

* Make sure the **3scaleRealm** realm is selected.
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





