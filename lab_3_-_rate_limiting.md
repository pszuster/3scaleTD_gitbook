# Lab 3 - Rate Limiting {#lab-3-rate-limiting}

{% hint style='info' %}
In this lab, you configure and test a rate limiting policy in an application plan for the API created in the previous lab.
{% endhint %}

* Go to https://3scale-admin.3scale.{{ book.suffix }}
* Login as admin/admin
* Click on the **APIs** tab.
* Expand the **Products** API.
* Scroll down to the **Published Application Plans** section.
* Click on the **ProductsBasicPlan**.

![](images/image202.png)

* Scroll down to the **Metrics, Methods &amp; Limits** section.
* Disable both **Create** and **Delete** methods by clicking on their **Enabled** column.

![](assets/Selection_481.png)

* Click on the **Limits** link for the **Get Product** method.
* Click on the **New usage limit** link.

![](images/image174.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Period** | hour |
| **Max. Value** | 5 |


* Click on the **Create usage limit** button.

![](images/image191.png)

* Click on the **Limits** link for the **Get All Products** method.
* Click on the **New usage limit** link.

![](images/image21.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Period** | minute |
| **Max. Value** | 1 |

* Click on the **Create usage limit** button.

![](images/image197.png)

*  Click on the Update Application Plan button.

![](images/image114.png)

* Click on the **Integration** tab.
* Click on the **edit APIcast configuration** link.

![](images/image1.png)

* Scroll down to the bottom of the page.
* Select and copy the url next to “curl”.

![](assets/Selection_322.png)

* Open a new web browser tab.
* Paste the URL and reload it 5 times.

{% hint style='tip' %}
After 6 invokations, you should receive an "**Limits exceeded**" message since you exceeded the application plan limit (5 per hour), as defined in the **Application Plan**:
{% endhint %}

![](images/image93.png)

* Go back to 3scale admin console.
* Click on the **Applications** tab.
* Click on the **ProductsApp** application.
* Scroll down to the bottom of the page, to the **Current Utilization** section.

![](assets/Selection_413.png)






