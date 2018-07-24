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
You should get a "Limits exceeded" error, since the application you are using (**RHBank’s App**) is subscribed to the **ProductsBasicPlan** which only allows the GET methods.
{% endhint %}

![](images/image134.png)

* Collapse the **POST** method by clicking on it.