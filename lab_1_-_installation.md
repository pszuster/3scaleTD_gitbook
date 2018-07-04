# Lab 1 - Installation {#lab-1-installation}

| ![RH\_Icon\_Compass\_Button.png](images/image26.png) | In this lab, you will deploy a Red Hat 3Scale API Management Platform \(AMP\) instance to an Openshift Container Platform \(OCP\) cluster. |
| --- | --- |


* Open a web browser and go to https://{{) book.hostname }}:8443 
* Login as admin/admin.
* Click on the **3scale API Management **icon in the Catalog.

![](/assets/3scale-openshift-catalog.png)

* Click **Next &gt;.**
* Select **Create Project**.
* Enter the following values:

| Parameter | Value |
| :--- | :--- |
| **Project Name** | 3scale |
| **Project Display Name** | 3scale API Management |

![](/assets/create-3scale-project.png)

* Scroll down and complete the following values:

| Parameter | Value |
| :--- | :--- |
| ADMIN\_PASSWORD | admin |
| WILDCARD\_DOMAIN | {{ book.suffix }} |
| MASTER\_PASSWORD | master |

* Click on the **Create** button.

* Click on the "**Continue to the project overview"** link.

![](/assets/3scale-project-created.png)

* After ~5 minutes, all the pods should have a blue circle, meaning 3Scale AMP is up and running.

![](images/image188.png)

