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

*  You should get an authorization error, since the application you are using (**RHBank’s App**) is subscribed to the **ProductsBasicPlan** which only allows the GET methods.

![](images/image134.png)

* Collapse the **POST** method by clicking on it.
* Click on the **Developers** tab.
* Click on the **RHBank** account.

![](images/image28.png)

* Click on the **2 Applications **breadcrumb.
* Click on the **Create Application** link.

![](images/image147.png)

* Select the **ProductsPremiumPlan**.
* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Name** | ProductsAppPremium |
| **Description** | RHBank Products Premium App |

*  Click on the **Create Application** button.

![](images/image177.png)

* Copy the **User Key** under **API Credentials**.

![](assets/Selection_346.png)

* Click on the **APIs** tab.
* Click on the **ActiveDocs** tab.
* Click on the **Products** spec.

![](images/image139.png)

* Expand the **POST** method.
* Click on the red circle icon with the exclamation mark.
* Paste the api_key in the **value** field.
* Click on the **Authorize** button.

![](assets/Selection_340.png)

* Click on the Model next to the body field.

![](assets/Selection_343.png)

* Remove the productid field from the sample json document.
* Replace “string” with “LED TV”.
* Replace “0” with “199.99”.
* Click on the **Try it out!** button.

![](images/image14.png)

* You should receive a successful response.

![](images/image162.png)

* Repeat these steps two times, to create two more products:

| productname | productprice |
| --- | --- |
| LED Smart TV | 299.99 |
| LED Smart TV 3D | 399.99 |

* Collapse the **POST** method by clicking on it.
* Expand the **GET /services/allproducts** operation.
* Click on the **Try it out!** button.

![](assets/Selection_347.png)

* You should receive a list of all existing products.
* Validate the products you created in the previous step are present.
* Click the **Try it out!** button several times, to generate some traffic.
* Collapse this operation by clicking on it.
* Expand the **GET /services/product/{productId}** operation.
* Enter a product id in the **productId** field (from the list of products retrieved in the previous step)
* Click on the **Try it out!** button.

![](assets/Selection_348.png)

* Click the **Try it out!** button several times to generate some traffic.
* Collapse the operation by clicking on it.
* Expand the **DELETE** operation.
* Enter a product id in the **productId** field (from the products created in the previous steps, should be 11, 12 and 13).
6.  Click on the **Try it out! **button.

![](assets/Selection_349.png)

* Execute this operation two times, changing the product id.
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