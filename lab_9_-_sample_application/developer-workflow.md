## Developer Workflow

{% hint style='info' %}
Now you will play the roles of the API consumer and API provider to reproduce a typical real-life scenario.
{% endhint %}

### As API Consumer

* Open a new web browser tab (don’t close this one!).
* Go to https://3scale.3scale.{{ book.suffix }}
* Click on **SIGN IN**.
* Click on **Sign up**.

![](../assets/Selection_427.png)

* Enter the following values:

| Parameter | Value |
| --- | --- |
| **Organization/Group Name** | RHBank2 |
| **Username** | dev1 |
| **Email** | dev1@rhbank.com |
| **Password** | password |
| **Password Confirmation** | password |

* Click on the **Sign Up** button.

![](../assets/Selection_428.png)

### As API Provider

* Go back to 3scale admin console browser tab.
* Click on the **Developers** tab.
* Click on **Activate** next to account **RHBank2**.

![](../assets/Selection_425.png)

* Click on the **RHBank2** account.
* Click on the **1 Service Subscription** link.

![](../assets/Selection_429.png)

* Click on the **Subscribe** link for the **Products** API.

![](../assets/Selection_430.png)

* Select the **Default Plan**.
* Click on the **Create Subscription** button.
* Repeat these steps for the **Stores** and **Stock** APIs.

![](../assets/Selection_431.png)

* Go back to the **Developer Portal** web browser tab.
* Click on **SIGN IN**.

![](../assets/Selection_432.png)

* Login as dev1/password.
* Click on **Applications**.
* Click on the **Create Application** button.

![](../assets/Selection_433.png)

* Click on **Products**.
* Enter the following values:
    * **Name**: ProductsApp
    * **Description: Products Application
* Click on **Review/Change**.

![](../assets/Selection_434.png)

* 
    







