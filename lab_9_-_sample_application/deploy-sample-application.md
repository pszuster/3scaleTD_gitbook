## Deploy the Sample Application

{% hint style='info' %}
The Benefits web app, will first invoke the Products API’s “getAll” operation to retrieve the entire list of products. Then, when the user clicks on a product, it will invoke the Stock API’s “stock” operation filtered by productid, which will return the list of store ids,with their amount of stock available. Finally the app will invoke the Stores API’s “store/{storeID}” operation for each store to retrieve the store’s name and geolocation, to place it on the map.
{% endhint %}

* Open a web browser and go to https://{{ book.hostname }}:8443
* Login as admin/admin.
* Click on the **benefits-app** template.

![](../assets/Selection_419.png)

* Click on the **Next >** button.
* Select **Create Project**.
* Enter the following values:
    * **Project Name**: benefits
    * **Project Display Name**: Benefits App
    
![](../assets/Selection_420.png)
    
* Scroll down to the middle of the page, and enter:

    * **Application Hostname**: benefits.{{ book.suffix }}
    
![](../assets/Selection_421.png)

* Set the following values:

    * **Products API URL**: https://products-apicast-staging.3scale.{{ book.suffix }}/rest/services/allproducts
    * **Stock API URL**: https://stock-apicast-production.3scale.{{ book.suffix }}/odata4/Stock-API/FederatedStock/stock
    * **Stores API URL**: https://stores-apicast-production.3scale.{{ book.suffix }}/store/

* Open a new web browser tab (don’t close this one!).
* Go to https://3scale.3scale.{{ book.suffix }}
* Login as rhbankdev/rhbank
4. Click on the **Applications** tab.

![](../assets/Selection_422.png)

1. Select and copy the User Key.

![](images/image48.png)

1. Go back to the Openshift console tab.
2. Paste the user key, in the Products API Key parameter.

![](images/image170.png)

1. Go back to the 3Scale dashboard’s browser tab.
2. Click on the Applications tab.
3. Click on the storesApp application.
4. Select and copy the User Key.

![](images/image185.png)

1. Switch back to the Openshift console browser tab.
2. Paste the user key to the Stores API Key.

![](images/image83.png)

1. Go back to the 3Scale dashboard’s browser tab.
2. Click on the Applications tab.
3. Click on the StockApp application.
4. Select and copy the User Key.

![](images/image106.png)

1. Switch back to the Openshift console browser tab.
2. Paste the user key to the Stock API Key.

![](images/image118.png)

1. Click on the Create button.
2. Click on the Continue to overview link.
3. After ~2min, there should be a nodeJS container deployed to Openshift.