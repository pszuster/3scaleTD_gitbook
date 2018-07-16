## Secure an API using OpenID Connect

* Go back to **3scale admin console** (https://3scale-admin.3scale.{{ book.suffix }}.
* Login as admin/admin.
* Click on the **APIs** tab.
* Expand the **Products** API.
* Click on **Inregration**.

![](../assets/Selection_451.png)

* Click on **edit integration settings**.

![](../assets/Selection_452.png)

* Scroll down to the bottom of the page.
* Click on **OpenID Connect**.
* Click on the **Update Service** button.
* Accept the warning.

![](../assets/Selection_453.png)

* Click on **edit APIcast configuration**.

![](../assets/Selection_454.png)

* Expand the **Authentication Settings** section.
* Enter the following value for the **OpenID Conect Issuer**: https://3scale-client:&lt;Paste your CLIENT SECRET&gt;@sso.{{ book.suffix }}/auth/realms/3scaleRealm