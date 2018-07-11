## Deploy the SOAP webservice
 
* Go to https://{{ book.hostname }}:8443
* Login as admin/admin
* Select the **Stores API** project.
* Click on the **Browse Catalog** button.

![](../assets/Selection_357.png)

* Select the **Stores SOAP API** template.
* Click on the **Next>** button.
* Modify the **“Custom http Route Hostname”** parameter to: **stores-soap.{{ book.suffix }}**
* Scroll down to the bottom of the page and click on the **Create** button.
* Click on the **Continue to the project overview **link.
* After ~5min the **Stores SOAP API** should be up and running (there should be two blue circles).

![](../assets/Selection_358.png)

* Open a new web browser tab, and go to [http://wsdlbrowser.com/](http://wsdlbrowser.com)
* Enter the following value:

* **WSDL URL**:  http://stores-soap.{{ book.suffix }}/StoresWS?wsdl

* Click on the **Browse** button.

![](../images/image148.png)

* Click on the **getAllStores** Soap operation.
* Click on the **Call Function** button.

![](../images/image97.png)

