# Lab 9 - Monetization

{% hint style='info' %}
In this lab you will explore the monetization feature of 3scale API Management.
{% endhint %}

* Go to https://3scale-admin.3scale.{{ book.suffix }}
* Login as admin/admin
* Click on the **APIs** tab.
* Expand the **Products** API.
* Click on the **Application Plans** link.

![](assets/Selection_386.png)

* Click on the **Create Application Plan** link.

![](assets/Selection_387.png)

* Enter the following values:
    * **Name**: ProductsPaidPlan
    * **System Name**: products/paid
* Click on the **Create Application Plan** button.   

![](assets/Selection_388.png)


{% hint style='info' %}
Note that you could also set things like a **Trial Period**, **Setup fee** and **Monthly Cost**
{% endhint %}

* Click on **Publish**.

![](assets/Selection_389.png)

* Click on the **Settings** tab.
* Check the **Developers can select a plan when creating a new application** checkbox under **Application Plan Changing**.
* Click on the **Update Service** button.

![](assets/Selection_390.png)

* Click on **ProductsPaidPlan**.
* Click on **Pricing** next to **Get All Products**.
* Click on **new pricing rule**.

![](assets/Selection_392.png)

* Enter the following values:
    * **From**: 1
    * **To**: 5
    * ** Cost per unit**: 1
* Click on the **Create** button.

![](assets/Selection_392.png)
![](assets/Selection_393.png)

* 

