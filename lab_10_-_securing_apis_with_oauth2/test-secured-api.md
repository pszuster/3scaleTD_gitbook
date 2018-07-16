## Test Secured API

{% hint style='info' %}
Now that RH-SSO is ready and the API has been secured in 3scale, you will test it.
{% endhint %}


* If you already don't have it, install Postman (https://www.getpostman.com/apps)
* Create a new Request and Collection.

![](../assets/Selection_464.png)

* Enter https://products-apicast-staging.3scale.{{ book.suffix }} as the **URL**.
* Select **OAuth 2.0** from the **Type** dropdown, under the **Authorization** section.
* Click on the **Get New Access Token** button.

![](../assets/Selection_465.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Callback URL** | https://www.getpostman.com/oauth2/callback |
| **Auth URL** | http://sso-unsecured.{{ book.suffix }}/auth/realms/3scaleRealm/protocol/openid-connect/auth |
| **Access Token URL** | http://sso-unsecured.{{ book.suffix }}/auth/realms/3scaleRealm/protocol/openid-connect/token |
| **Client ID** | |
| **Client Secret** | |
