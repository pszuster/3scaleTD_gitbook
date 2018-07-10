# Lab 2 - Create your first API {#lab-2-create-your-first-api}

{% hint style='info' %}
In this lab, you will create your first API in 3Scale API Management, exposing a REST JEE application which is running in a JBoss Enterprise Application Platform (EAP) container in the same OCP cluster.
{% endhint %}


* Open a new web browser tab.
* Go to https://3scale-admin.3scale.{{ book.suffix }}.
* Login as admin/admin
* If a "_connection not private_" warning appears, click on **Proceed to ..**
* Login with admin/admin.

![](images/image110.png)

* Click on the grey **X** to dismiss the Getting started wizard.

![](images/image65.png)

{% hint style='tip' %}
Notice there is a pre-built API called “API” that is useful for learning/testing only.
{% endhint %}


![](images/image43.png)

* Click on the **Create Service** link.

![](images/image17.png)

* Enter the following values:

|Parameter|Value|
|---|---|
| **Name** | Products |
| **System name** | products\_system |
| ** Description** | RHMart Products API |


![](images/image33.png)

* Scroll down to the bottom of the page, and make sure API Key is selected as authentication method.
* Click on the **Create Servic**e button.

![](images/image138.png)

* In the APIs section, expand the **Products** API and scroll down to the **Published Application Plans** section.
* Click on the **Create Application Plan** link.

![](images/image186.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Name** | ProductsBasicPlan |
| **System name** | products/basic |



* Click on the **Create Application Plan** button.

![](images/image113.png)

* Click on the **Create Application Plan** link.

![](images/image155.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Name** | ProductsPremiumPlan |
| **System name** | products/premium |


* Click on the **Create Application Plan** button.

![](images/image98.png)

* Click on the **Publish** link for both **Basic** and **Premium** plans.

![](images/image12.png)

{% hint style='info' %}
Plans are used for granting access to specific APIs and endpoints, limiting traffic and monetizing API usage. Application plans let you configure access rights to an API by specifying rate limits and pricing rules. All applications must be associated with a plan. Application plans can be customized for one application.
{% endhint %}

* Click on the **Developers** tab.
* Click on the **Create** link.

![](images/image52.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Username** | rhbankdev |
| **Email** | developer@rhbank.com |
| **Password** | rhbank |
| **Organization** | RHBank |


![](images/image38.png)

* Click on the **1 Application** breadcrumb.
{% hint style='info' %}
Notice there is one default application for the built-in “API” service.
{% endhint %}

![](images/image3.png)

* Click on the **Create Application** link.
* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Application Plan** | ProductsBasicPlan |
| **Name** | ProductsApp |
| **Description** | Products Application |

 
* Click on the **Create Application** button.

![](images/image145.png)

* Click on the **APIs** tab.
* Expand the **Products** API and click on **Integration**.

![](images/image51.png)

* Click on the **add the base URL of your API and save the configuration** button.

![](images/image108.png)

* Expand the **Mapping Rules** section.
* Click on the **Define Metric/Method**  link.

![](images/image2.png)

* Click on the **New Method** link in the **Methods** section.

![](images/image49.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Friendly Name** | Get Product |
| **System Name** | product/get |
| **Description** | Get a product by ID |


* Click on the **Create Method** button.

![](images/image123.png)

* Repeat this procedure for the following methods:

| Friendly Name | System Name | Description |
| --- | --- | --- |
| Create Product | product/create | Create a new Product |
| Delete Product | product/delete | Delete a product by ID |
| Get All Products | product/getall | Get all products |

![](images/image136.png)

* Click on any of the “**Add a Mapping rule**” links.
* Click on the **edit** icon next to the **GET** mapping rule.
* Enter `/rest/services/product/{id}` as the **Pattern**.
* Select **product/get** as **Method**.

![](assets/Selection_317.png)

* Click on the **Add Mapping Rule** link.
* Repeat this procedure for the following values:

| Verb | Pattern | Method |
| --- | --- | --- |
| POST | /rest/services/product | product/create |
| DELETE | /rest/services/product/{id} | product/delete |
| GET | /rest/services/allproducts | product/getall |

![](assets/Selection_318.png)

* Open a new web browser tab, and go to https://{{ book.hostname }}:8443/console/project/products-api/overview

![](images/image163.png)
* Take note of the Products API http route. It should be http://products.{{ book.suffix }}

![](images/image87.png)

{% hint style='info' %}
The Products API is a restful service built on Java \(JAX-RS\), deployed on JBoss EAP and connected to a PostgreSQL DB.
{% endhint %}

* Go back to 3Scale web browser tab.
* Enter the following values:

| Parameter | Value |
| --- | --- |
|**Private Base URL** | http://products.{{ book.suffix }} |
|**Staging Public Base URL** | https://products-apicast-staging.3scale.{{ book.suffix }}:443|
|**Production Public Base URL** | https://products-apicast-production.3scale.{{ book.suffix }}:443|

![](assets/Selection_319.png)

* Expand the **Policies** section.
* Click on the **Add Policy** link.

![](assets/Selection_344.png)

* Click on the **CORS** policy.

![](assets/Selection_345.png)

{% hint style='info' %}
Cross-origin resource sharing (CORS) is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served. We will need this policy enabled later, to be able to make API calls from an OpenAPI document.
{% endhint %}


* Scroll down to **API Test GET request**.
* Enter  `/rest/services/product/1`.
* Click on the **Update & Test in Staging Environment**.
![](assets/Selection_321.png)

* You should get a success message.

![](assets/Selection_341.png)

* Select the URL after “curl” and copy it.

![](assets/Selection_322.png)

* Open a new web browser tab, and paste the URL.
* You should get a json document describing a product.

![](assets/Selection_323.png)

