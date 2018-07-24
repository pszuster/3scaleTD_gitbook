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
| **access_token** | &lt;paste token here&gt; |
| **provider_id** | 2 |
| **date** | &lt;current year, four digits&gt;-&lt;NEXT month, two digits&gt;-01 |

{% hint style='info' %}
So if today is 10th of July 2018, date should be: 2018-08-01
{% endhint %}

* Click on the **Send Request** button.

![](../assets/Selection_407.png)

* Close the **Master Tenant** browser tab.
* Go back to the 3scale admin console.
* Click on the **Billing** tab.
* Click on the **Invoices** tab.

![](../assets/Selection_408.png)

* Click on **Show Invoice**.
* Scroll down to the bottom of the invoice.

![](../assets/Selection_409.png)

{% hint style='tip' %}
You should see the 5 request charged USD 1 each.
{% endhint %}

{% hint style='info' %}
The invoices could be paid directly in the platform when configured to be integrated with a payment gateway like **Braintree**, **Adyen** or **Stripe**. More info in the [documentation](https://access.redhat.com/documentation/en-us/red_hat_3scale/2.2/html/billing/).
{% endhint %}
