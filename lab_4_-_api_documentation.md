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


*  Select **File** -&gt; **Import URL**.
*  Enter the following URL: http://products.{{ book.suffix }}/rest/swagger.yaml 
*  Click **OK**.

![](images/image79.png)

*  In the YAML editor, make the following change:

1.  Go to line #7 and change host to: products-apicast-staging.gateway.3scale[your instance #].rhtechofficelatam.com:443

1.  For each of the available operations, you will add a query parameter (user_key) which contains the required authentication for 3Scale.
2.  Go to line #25 and add the following:

|       - name: &quot;user_key&quot; |
| --- |

![](images/image204.png)

1.  Go to line #50 and add the user_key query parameter.

![](images/image7.png)

1.  Go to line #74 and add the user_key query parameter:

![](images/image121.png)

1.  Go to line #99, delete the square brackets, and add the user_key query parameter.

![](images/image126.png)

1.  Click on File -&gt; Download JSON.
2.  Save the JSON file to your disk.
3.  Close the browser tab.
4.  Go back to the 3Scale web browser ta3b.
5.  Open the downloaded swagger.json file with any text editor, and copy its contents.
6.  Paste it into the API JSON Spec field.

![](images/image196.png)

1.  Scroll down to the bottom of the page, and click on the Create Service button.
2.  Click on the  Publish link.

![](images/image187.png)

1.  Expand the GET /services/products operation.
2.  Go to the Parameters section.
3.  Click on the user_key value field.
4.  Select the ProductsApp user_key.

![](images/image116.png)

1.  Click on the Try it Out! Button.
2.  You should get a successful response like the following:

![](images/image74.png)

1.  If you get a “No Content” error, copy the displayed URL, open a new tab and paste the URL.
2.  Accept the certificate.
3.  Close the tab and test the API again.