# Lab 4 - API Documentation {#lab-4-api-documentation}

{% hint style='info' %}
In this lab, you will generate and test an ActiveDocs documentation for the API created in the 2nd lab.
{% endhint %}

*  Open a web browser and go to https://3scale-admin.3scale.{{ book.suffix }}
*  Login as admin/admin
*  Click on the **APIs** tab.
*  Click on the **AciveDocs** link.

![](images/image31.png)

*  Click on the **Create a new spec**.

![](images/image102.png)

*  Enter the following values:

| Parameter | Value |
| --- | --- |
| **Name** | Products |
| **System Name** | products_spec |
| **Publish?** | checked |
| **Description** | Products API Documentation |

![](images/image75.png)

* Open a new web browser tab, and go to http://apicurio-studio.{{ book.suffix }}
* Click on the **Register** link.

![](assets/Selection_325.png)
* Complete the form with the following values:

| Parameter | Value |
| --- | --- |
| **First Name** | Username |
| **Last Name** | Lastname |
| **Email** | user@mail.com |
| **Password** | password |
| **Confirm Password** | password |

* Click on the **Register** button.

![](assets/Selection_326.png)

* Click on the **Import API** button.

![](assets/Selection_342.png)

* Enter the following URL:  http://products.{{ book.suffix }}/rest/swagger.yaml

{% hint style='tip' %}
This API was built using [Swagger/OpenAPI annotations](https://github.com/swagger-api/swagger-core/wiki/annotations), so it will automatically and dynamically generate an OpenAPI document that describes its operations, parameters, etc. that you can get by accessing that URL (/rest/swagger.yaml).
{% endhint %}


* Click on the **Import API** button.

![](assets/Selection_328.png)

* Click on the **Edit API** button.

![](assets/Selection_329.png)
{% hint style='tip' %}
You will add a "security scheme" to the API to secure it using API Keys.
{% endhint %}

* Click on the **Add a security scheme** link.

![](assets/Selection_330.png)

* Enter the following values:

| Parameter | Value |
| -- | -- |
| **Name** | apiKey |
| **Security** | API Key |
| **Key Location** | Query Parameter |
| **Name** | user_key |


* Click on the **OK** button.
![](assets/Selection_331.png)

* Click on the **Add security requirement** link.

![](assets/Selection_332.png)

* Check the **apiKey** security requirement.
* Click on the **OK** button.

![](assets/Selection_333.png)

* Click on the APIs >> **Products** breadcrumb link.
* Click on the three dots in the **Products** API and select **Download (JSON)**.

![](assets/Selection_334.png)

* Save the **Products.json** file in your computer.
* Close Apicurio, and go back to the 3Scale admin console web browser tab.
* Open the downloaded **Products.json** file with any text editor, and copy its contents.
* Paste it into the API JSON Spec field.

![](assets/Selection_335.png)

* Replace **host** field value with: **products-apicast-staging.3scale.{{book.suffix }}:443**
* Change the **http** scheme to **https**.
* Scroll down to the bottom of the page, and click on the **Create Service** button.

![](assets/Selection_336.png)

* Click on the **Applicatios** tab.
* Click on the **ProductsApp** application.
* Copy the **User Key** under **API Credentials**

![](assets/Selection_337.png)

* Click on the **APIs** tab.
* Click on the **ActiveDocs** tab.
* Click on the **Products** spec.

![](assets/Selection_338.png)

* Expand the **GET** **/services/allproducts** operation.
* Click on the red circle with an exclamation sign.
* Paste the **User Key** into the **value** field.
* Click on the **Authorize** button.

![](assets/Selection_339.png)
* Click on the **Try it Out!** button.
* You should get a successful response like the following:

![](images/image74.png)

* If you get a “**No Content**” error, copy the **Request URL**, open a new tab and paste the URL.
* Accept the certificate.
* Close the tab and test the API again.