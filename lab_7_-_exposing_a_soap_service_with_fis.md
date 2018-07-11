# Lab 7 - Exposing a SOAP Service with FIS {#lab-7-exposing-a-soap-service-with-fis}

{% hint style='info' %}
In this lab you will expose an existing SOAP based JEE application running on a JBoss EAP container in the same OCP cluster. To do this, you will deploy a Fuse on Openshift application (formerly known as Fuse Integration Services) to your Openshift cluster, which was built to expose the SOAP webservice as a REST API. 
{% endhint %}

* Open a web browser and go to [https://github.com/pszuster/3ScaleTD/blob/master/Stores/src/main/java/com/redhat/service/StoresWS.java](https://github.com/pszuster/3ScaleTD/blob/master/Stores/src/main/java/com/redhat/service/StoresWS.java)

{% hint style='tip' %}
This simple java class implements a JAX-WS SOAP webservice that allows consumers to create, delete or get Stores from RHMart. 
{% endhint %}

![](images/image203.png)

* Go to https://3scale-admin.3scale.{{ book.suffix }}:8443
* Login as admin/admin
* Select the **Stores API** project.
* Click on the **Browse Catalog** button.

![](assets/Selection_357.png)

* Select the **Stores SOAP API** template.
* Click on the **Next>** button.
*  Modify the **“Custom http Route Hostname”** parameter to: stores-soap.{{ book.suffix }}
* Scroll down to the bottom of the page and click on the **Create** button.
* Click on the **Continue to the project overview **link.
* After ~5min the Stores SOAP API should be up and running (there should be two blue circles).

![](assets/Selection_358.png)

* Open a new web browser tab, and go to [http://wsdlbrowser.com/](http://wsdlbrowser.com)
* Enter the following value:

* **WSDL URL**:  http://stores-soap.{{ book.suffix }}/StoresWS?wsdl

* Click on the **Browse** button.

![](images/image148.png)

* Click on the **getAllStores** Soap operation.
* Click on the **Call Function** button.

![](images/image97.png)

* Close the browser tab, and go back to OpenShift console.
* Make sure you are in the **Stores API **project.
* Click on the **Add to project ** dropdown button.
* Click on **Browse Catalog**.

![](assets/Selection_359.png)

* Select the **stores-fis** template.
* Click on the **Next>** button.
* Change the **HostName** parameter to: stores-fis.{{ book.suffix }}
* Click on the **Create** button.

![](assets/Selection_360.png)

* Click on the **Continue to project overview **link.
* After ~3min the Fuse Integration Services container should be up and running (there should be a blue circle).

![](assets/Selection_361.png)

{% hint style='info' %}
This Fuse Integration Services container, has a SpringBoot Camel route, that transforms REST requests to SOAP requests and XML SOAP responses to JSON documents.
{% endhint %}

* Open a new web browser tab, and go to http://stores-fis.{{ book.suffix }}/allstores/
* You should receive a JSON document generated from the SOAP response.
* Close the tab.
* Go to https://3scale-admin.3scale.{{ book.suffix }}
* Click on the **configuration** icon.
* Click on **Personal Settings**.

![](images/image50.png)

* Click on the **Tokens** tab.
* Click on the **Add Access Token** link.

![](images/image62.png)

* Enter **Name**: importer
* Check on the three scopes.
* Select Permission: **Read &amp; Write**
* Click on the **Create Access Token **button.

![](assets/Selection_362.png)

* Select and copy the generated Token.

![](assets/Selection_363.png)

* Open a new web browser tab and go to http://swagger-import.{{ book.suffix }}
* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Access Token** | &lt;paste the copied Token&gt; |
| **3Scale ID** | 3scale |
| **Wildcard Domain** | 3scale.{{ book.suffix }} |
| **Swagger File URL** | http://stores-fis.{{ book.suffix }}/api-docs|

* Click on the **Import API** button.

![](assets/Selection_364.png)

* After a couple of seconds, the import process should be done.

![](images/image86.png)

* Close the browser tab.
* Go back to  https://3scale-admin.{{ book.suffix }}
* Click on the **APIs** tab.
* Expand **Stores API**.
* Click on the **Create Application Plan** link

![](images/image179.png)

* Enter the following values:
    * **Name**: StoresPremiumPlan
    * **System Name**: storesPremiumPlan

* Click on the **Create Application Plan** button.

![](images/image176.png)

* Click on the **Publish** link.

![](images/image59.png)

* Click on the **Developers** tab.
* Click on the **RHBank** account.

![](images/image80.png)

* Click on the **3 Applications** Breadcrumb.
* Click on the **Create Application** link.

![](images/image144.png)

* Select the **StoresPremiumPlan**.
* Enter the following values:
    * **Name**: storesApp
    * **Description**: Stores Application

* Click on the **Create Application** button.

![](images/image169.png)

* Click on the **Stores API** link.

![](images/image35.png)

* Click on the **Integration** tab.
* Click on the **add the base URL of your API and save the configuration** button.

![](images/image182.png)

* Enter the following values:

    * **Private Base URL**: http://stores-fis.{{ book.suffix }}
    * **Staging Public Base URL**: https://stores-apicast-staging.3scale.{{ book.suffix }}
    * **Production Public Base URL**: https://stores-apicast-production.3scale.{{ book.suffix }}
    * **API test GET request**: /allstores
    * **Policy Chain**: CORS

* Click on the **Update &amp; test in Staging Environment** button.

![](assets/Selection_368.png)

* You should receive a successful validation.
* Click on the **Back to Integration &amp; Configuration** link.

![](images/image200.png)

* Click on the **Promote v1 to Production** button.

![](images/image46.png)

* Click on the **ActiveDocs** tab.
* Click on the **Edit** icon for the **Stores API** spec.

![](assets/Selection_366.png)

* Change the host attribute to: **stores-apicast-production.3scale.{{ book.suffix }}**
* Change the scheme from _http_ to _https_.
* For each of the four **user_key** parameters, add the following attribute: 

```
,&quot;x-data-threescale-name&quot;: &quot;user_keys&quot;

```

![](assets/Selection_369.png)

* Scroll down to the bottom of the page and click on the **Update Service** button.
* Open a web browser tab and go to https://stores-apicast-production.3scale.{{ book.suffix }} and accept the SSL certificate.
* Close the tab and go back to the **Stores API** ActiveDoc.
* Expand the **/allstores** operation.
* Click on the **user_key** parameter field and select the **storesApp** user key.
* Click on the **Try it out!** button.

![](images/image161.png)

1.  You should receive a JSON document with a list of stores.

![](images/image47.png)