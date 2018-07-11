# Lab 5 - Analytics {#lab-5-analytics}

{% hint style='info' %}
In this lab you will generate some load for the API and then check out the analytics graphics to understand API’s traffic.
{% endhint %}

* Open a web browser and go to https://3scale-admin.3scale.{{ book.suffix }}
* Login as admin/admin.
* Click on the **Applications** tab.
* Click on the **ProductsApp** application.
* Copy the **User Key** under **API Credentials**.

![](assets/Selection_337.png)

* Click on the **APIs** tab.
* Click on the **ActiveDocs** tab.

![](images/image71.png)

* Click on the **Products** spec.

![](images/image10.png)

* Expand the **POST** method.
* If already not logged in:
    * Click on the red circle icon with the exclamation mark.
    * Paste the api_key in the **value** field.
    * Click on the **Authorize** button.

![](assets/Selection_340.png)
*  Click on the Model next to the body field.

![](assets/Selection_343.png)

* Remove the **productid** field from the sample json document.
* Click on the **Try it out!** button.

![](images/image192.png)

{% hint style='danger' %}
You should get an authorization error, since the application you are using (**RHBank’s App**) is subscribed to the **ProductsBasicPlan** which only allows the GET methods.
{% endhint %}

![](images/image134.png)

* Collapse the **POST** method by clicking on it.






* Click on the **Analytics** tab.
* Click on the **Products** API.

![](images/image130.png)

* You should see a graphic similar to this one:

![](assets/Selection_350.png)

* Hover over the bars to see detailed information per period.

![](images/image15.png)

* Hover over the operation names to the right of the chart.

![](images/image142.png)

* Click on the different period options (7 days, 30 days, 12 months).
* Click on the **Daily Averages** tab.
* Select an operation from the dropdown.

![](images/image104.png)

* Click on the **Hourly Averages** tab.

![](images/image68.png)

* Click on the **Traffic** tab.

![](images/image112.png)

* Click on the **Applications** tab.
* Click on the **ProductsApp** application.

![](images/image198.png)

* Scroll down to the **Current Utilization** section.

![](images/image94.png)

{% hint style='tip' %}
Here you can monitor an application’s limits.
{% endhint %}

* Click on the **Applications** tab.
* Click on the **ProductsAppApremium** application.

![](images/image24.png)

* Click on the **Analytics** breadcrumb.
* Here you can monitor a specific application’s usage:

![](images/image90.png)