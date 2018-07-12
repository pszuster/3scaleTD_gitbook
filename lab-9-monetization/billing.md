## Execute Monthly Billing

{% hint style='info' %}
Now you will force the execution of the monthly billing to see how it works. (normally it would happen automatically once a month)
{% endhint %}

* Go to https://master-admin.3scale.{{ book.suffix }}/p/admin/user/access_tokens
* Login as master/master

{% hint style='tip' %}
You will access the **Master Tenant** wich is the admin console for the super admin, that manages all the created _tenants_.
{% endhint %}

* Click on **Add Access Token**.

![](../assets/Selection_404.png)

* Enter **Name**: billing
* Select the two available scopes: **Account Management API** and** Analytics API**
* Select **Read&Write**.
* Click on the **Create Access token** button.

![](../assets/Selection_405.png)

* Copy the generated **Token** and paste it in a text editor (notepad, etc.)
* Click on **Documentation** -> **3scale API Docs**.

![](../assets/Selection_406.png)

* Scroll down to the bottom of the page.
* Click on the **Trigger Billing** API.
* Enter the following values:
| Paramter | Value |
| --- | --- |
| **access_token** | <paste token here> |
| **provider_id** | 2 |
| 
