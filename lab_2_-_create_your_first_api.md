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

* Click on the Create Service link.

![](images/image17.png)

* Enter the following values:
| Parameter | Value |
| --- | --- |
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

* Click on the **Create Application Pla**n link.

![](images/image155.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Name** | ProductsPremiumPlan |
| **System name** | products/premium |


* Click on the Create Application Plan button.

![](images/image98.png)

* Select the **ProductsBasicPlan** as **Default Plan**.
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
|**Username** | rhbankdev |
| **Email** | developer@rhbank.com |
| **Password** | rhbank |
| **Organization** | RHBank |


![](images/image38.png)

* Click on the **1 Application** breadcrumb.
* Notice there is one default application for the built-in “API” service.

![](images/image3.png)

1. Click on the Create Application link.
2. Enter the following values:

3. Application Plan: ProductsBasicPlan

4. Name: ProductsApp
5. Description: Products Application

6. Click on the Create Application button.

![](images/image145.png)

1. Click on the APIs tab.
2. Expand the Products API and click on Integration.

![](images/image51.png)

1. Click on the add the base URL of your API and save the configuration button.

![](images/image108.png)

1. Expand the Mapping Rules section.
2. Click on the Define Metric/Method  link.

![](images/image2.png)

1. Click on the New Method link in the Methods section.

![](images/image49.png)

1. Enter the following values:

2. Friendly Name: Get Product

3. System Name: product/get
4. Description: Get a product by ID.

5. Click on the Create Method button.

![](images/image123.png)

1. Repeat this procedure for the following methods:

| Friendly Name | System Name | Description |
| --- | --- | --- |
| Create Product | product/create | Create a new Product |
| Delete Product | product/delete | Delete a product by ID |
| Get All Products | product/getall | Get all products |

![](images/image136.png)

1. Click on any of the “Add a Mapping rule” links.
2. Click on the edit icon next to the GET mapping rule.
3. Enter /rest/services/product/ as the Pattern.
4. Select product/get as Method.

![](images/image117.png)

1. Click on the Add Mapping Rule link.
2. Repeat this procedure for the following values:

| Verb | Pattern | Method |
| --- | --- | --- |
| POST | /rest/services/product | product/create |
| DELETE | /rest/services/product/ | product/delete |
| GET | /rest/services/products | product/getall |

![](images/image85.png)

1. Open a new web browser tab, and go to [https://threescale.3scale\[your instance \#\].rhtechofficelatam.com:8443/console/](https://www.google.com/url?q=https://threescale.3scale1.rhtechofficelatam.com:8443/console/&sa=D&ust=1530635179318000) 
2. Click on the Products API project.

![](images/image163.png)

1. Take note of the Products API http route. It should be [http://products.3scale\[](http://products.3scale[) your instance \#\].rhtechofficelatam.com

![](images/image87.png)

| ![general\_info\_polished.png](images/image34.png) | The Products API is a restful service built on Java \(JAX-RS\), deployed on JBoss EAP and connected to a PostgreSQL DB. |
| --- | --- |


1. Go back to 3Scale web browser tab.
2. Enter the following values:

3. Private Base URL:  [http://products.3scale\[](http://products.3scale[) your instance \#\].rhtechofficelatam.com

4. Staging Public Base URL: [https://products-apicast-staging.gateway.3scale\[](https://products-apicast-staging.gateway.3scale[) your instance \#\].rhtechofficelatam.com:443
5. Production Public Base URL: [https://products-apicast-production.gateway.3scale\[](https://products-apicast-production.gateway.3scale[) your instance \#\].rhtechofficelatam.com:443

![](images/image111.png)

1. Scroll down to the API Test GET request.
2. Enter  /rest/services/product/1.
3. Click on the Update & Test in Staging Environment.

![](images/image124.png)

1. You should get a success message.
2. Click on  the Back to Integration & Configuration link.

![](images/image69.png)

1. Select the URL after “curl” and copy it.

![](images/image42.png)

1. Open a new web browser tab, and paste the URL.
2. You should get a json document describing a product.

![](images/image164.png)

