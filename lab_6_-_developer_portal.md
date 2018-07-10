# Lab 6 - Developer Portal {#lab-6-developer-portal}

{% hint style='info' %}
In this lab you will work on the Developer Portal to make it more friendly/branded for customers/partners/consumers.
{% endhint %}

* Open a web browser.
* Download this two files:
    * [https://github.com/pszuster/3ScaleTD/raw/v2.2/DevPortal/RHMartLogo.png](https://www.google.com/url?q=https://github.com/pszuster/3ScaleTD/raw/v2.2/DevPortal/RHMartLogo.png&sa=D&ust=1530635179364000)
    * [https://github.com/pszuster/3ScaleTD/raw/v2.2/DevPortal/RHMartBackground.jpg](https://www.google.com/url?q=https://github.com/pszuster/3ScaleTD/raw/v2.2/DevPortal/RHMartBackground.jpg&sa=D&ust=1530635179365000) 

* Go to https://3scale-admin.3scale.{{ book.suffix }}
* Login as admin/admin
* Click on the **Developer Portal** tab.
* Click on the arrow next to **New Page** button.
* Click on **New File**.

![](images/image20.png)

* Set **Section** to **images**.
* Set **Path** to **/images/RHMartLogo.png**
* Click on the **Choose File** button.
* Select the **RHMartLogo.png** file you downloaded in the first step.
* Click on the **Create File** button.

![](images/image13.png)

* Click on the **New File** button.

![](images/image119.png)

* Set **Section** to **images**.
* Set **Path** to **/images/RHMartBackground.jpg**
* Click on the **Choose Fil**e button.
* Select the **RHMartBackground.jpg** file you downloaded in the first step.
* Click on the **Create File** button.

![](images/image199.png)

* Click on the **All** button.
* Click on the **Layouts** icon.
* Click on **Main Layout**.

![](images/image99.png)

* Go to line **#46**.
* Replace it with the following:

```html
<div class="logo">
       <a href="#"><img src="/images/RHMartLogo.png" alt="" style="height:100px; width:150px;">
       </a>
    </div>
```

* Scroll down to the bottom of the page, and click on the **Save** button.

![](images/image183.png)

* Click on the **Pages** icon.
* Click on **Documentation**.

![](images/image151.png)

* Go to line #3 and replace **"Echo"** with **"RHMart"**.
* Go to line #5.
* Replace the line with the following:

```
{% active_docs version: "2.0" services: "products_spec" %}
```

* Click on the **Save** button.

![](images/image32.png)

* Click on **Homepage**.

![](images/image11.png)

* Go to the **HTML editor**, and perform a search and replace of "**Echo"** (with capital "_E_") to **"RHMart"** in lines #19, #98 and #112.
* Go to line #5.
* Replace it with the following:

```html
<h1 style="text-shadow: 4px 4px #000000;">RH Mart API</h1>
```

* Scroll down to the bottom of the page and click on the **Save** button.
* Click on **default.css**, under the **css** folder.

![](images/image146.png)

* Go to line #22.
* Replace it with the following:


```
background-image: url('/images/RHMartBackground.jpg');
```

* Scroll down to the bottom of the page.
* Click on the **Save** button.
* Click on the **0 Drafts** tab.
* Click on **Publish All**.
* Accept the warning.

![](images/image193.png)

* Click on the **Visit Developer Portal** button.

![](images/image18.png)
* Click on **SIGN IN**.

![](images/image135.png)

* Login as
    * **Username**: rhbankdev
    * **Password**: rhbank

* Click on **Applications**.
* Review available applications for the RHBank account.
* Click on **Statistics**.
* Take a look at the traffic by application.

![](images/image141.png)

* Click on **Documentation**.
* Expand an operation and test it.

![](images/image190.png)