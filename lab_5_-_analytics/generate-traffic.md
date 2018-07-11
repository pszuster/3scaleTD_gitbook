## Generate Traffic

* Click on the **APIs** tab.
* Click on the **ActiveDocs** tab.
* Click on the **Products** spec.

![](../images/image139.png)

* Expand the **POST** method.
* Click on the red circle icon with the exclamation mark.
* Paste the api_key in the **value** field.
* Click on the **Authorize** button.

![](../assets/Selection_340.png)

* Click on the Model next to the body field.

![](../assets/Selection_343.png)

* Remove the productid field from the sample json document.
* Replace “string” with “LED TV”.
* Replace “0” with “199.99”.
* Click on the **Try it out!** button.

![](../images/image14.png)

* You should receive a successful response.

![](../images/image162.png)

* Repeat these steps two times, to create two more products:

| productname | productprice |
| --- | --- |
| LED Smart TV | 299.99 |
| LED Smart TV 3D | 399.99 |

* Collapse the **POST** method by clicking on it.
* Expand the **GET /services/allproducts** operation.
* Click on the **Try it out!** button.

![](../assets/Selection_347.png)

* You should receive a list of all existing products.
* Validate the products you created in the previous step are present.
* Click the **Try it out!** button several times, to generate some traffic.
* Collapse this operation by clicking on it.
* Expand the **GET /services/product/{productId}** operation.
* Enter a product id in the **productId** field (from the list of products retrieved in the previous step)
* Click on the **Try it out!** button.

![](../assets/Selection_348.png)

* Click the **Try it out!** button several times to generate some traffic.
* Collapse the operation by clicking on it.
* Expand the **DELETE** operation.
* Enter a product id in the **productId** field (from the products created in the previous steps, should be 11, 12 and 13).
6.  Click on the **Try it out! **button.

![](../assets/Selection_349.png)

* Execute this operation two times, changing the product id.
