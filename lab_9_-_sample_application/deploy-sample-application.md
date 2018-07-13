## Deploy the Sample Application

{% hint style='info' %}
The Benefits web app, will first invoke the Products API’s “getAll” operation to retrieve the entire list of products. Then, when the user clicks on a product, it will invoke the Stock API’s “stock” operation filtered by productid, which will return the list of store ids,with their amount of stock available. Finally the app will invoke the Stores API’s “store/{storeID}” operation for each store to retrieve the store’s name and geolocation, to place it on the map.
{% endhint %}

* Open a web browser and go to https://{{ book.hostname }}:8443
* Login as admin/admin.
* Click on the **New Project** button.

![](../images/image91.png)

1. Enter the following values:

1. Name: benefits
2. Display Name: Benefits

1. Click on the Create button.

![](images/image22.png)

1. Enter “benefits” in the Browse Catalog search field.
2. Click on the Select button in the found template.

![](images/image54.png)

1. Scroll down to the middle of the page, and enter:

1. Application Hostname: benefits.3scale[your instance #].rhtechofficelatam.com

![](images/image53.png)

1. Set the following values:

1. Products API URL: [https://products-apicast-staging.gateway.3scale[your instance #].rhtechofficelatam.com:443/rest/services/products](https://www.google.com/url?q=https://products-apicast-staging.gateway.3scale.rhtechofficelatam.com:443/rest/services/products&sa=D&ust=1530635179450000)
2. Stock API URL: [https://stock-apicast-production.gateway.3scale[your instance #].rhtechofficelatam.com/odata4/Stock-API/FederatedStock/stock](https://www.google.com/url?q=https://stock-apicast-production.gateway.3scale1.rhtechofficelatam.com/odata4/Stock-API/FederatedStock/stock&sa=D&ust=1530635179450000)
3. Stores API URL: [https://stores-apicast-production.gateway.3scale[your instance #].rhtechofficelatam.com/store/](https://www.google.com/url?q=https://stores-apicast-production.gateway.3scale1.rhtechofficelatam.com/store/&sa=D&ust=1530635179451000)

1. Open a new web browser tab (don’t close this one!).
2. Go to [https://3scale-admin.3scale[your instance #].rhtechofficelatam.com](https://www.google.com/url?q=https://3scale-admin.3scale1.rhtechofficelatam.com&sa=D&ust=1530635179451000)
3. Login as admin/admin
4. Click on the Applications tab.
5. Click on the ProductsAppPremium.

![](images/image201.png)

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