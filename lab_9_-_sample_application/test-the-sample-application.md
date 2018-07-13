## Test the sample application

{% hint style='info' %}
Now that the sample application is deployed and the APIs are available, you are going to simulate a web app consuming your APIs.
{% endhint %}

* Open a new web browser tab and go to http://benefits.{{ book.suffix }}
* Click on any Product from the products table.

![](../images/image122.png)

1. It should invoke the Stock API to query about stores with stock available for that products, and invoke the Stores API to retrieve their name/location.
2. You can review the nodejs code of the Benefits App here: [https://github.com/pszuster/3ScaleTD/blob/master/Benefits/views/index.html](https://www.google.com/url?q=https://github.com/pszuster/3ScaleTD/blob/master/Benefits/views/index.html&sa=D&ust=1530635179456000)
3. Switch back to the 3Scale dashboard’s browser tab.
4. Click on the Analytics tab.
5. Click on the Products API, Stores API and Stock API.
6. You should see the traffic created by the Benefits application (specifically for the “Get All Products”, “store_storeID_GET” and stock “Hits” operations.

![](images/image73.png)

![](images/image45.png)

![](images/image120.png)

1. Open a web browser tab and go to [https://3scale.3scale[your instance #].rhtechofficelatam.com](https://www.google.com/url?q=https://3scale.3scale3.rhtechofficelatam.com&sa=D&ust=1530635179457000)
2. Click on the Statistics tab.
3. Cycle through the involved plans to view the API activity (ProductAppPremium, storesApp, StockApp).

![](images/image84.png)

