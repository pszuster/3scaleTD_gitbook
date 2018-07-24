# Lab 7 - Exposing a SOAP Service with FIS {#lab-7-exposing-a-soap-service-with-fis}

{% hint style='info' %}
In this lab you will expose an existing SOAP based JEE application running on a JBoss EAP container in the same Openshift cluster. To do this, you will deploy a [Fuse](https://developers.redhat.com/products/fuse/overview/) on Openshift application (formerly known as Fuse Integration Services) to your Openshift cluster, which was built to expose the SOAP webservice as a REST API. 
{% endhint %}

* Open a web browser and go to [https://github.com/pszuster/3ScaleTD/blob/master/Stores/src/main/java/com/redhat/service/StoresWS.java](https://github.com/pszuster/3ScaleTD/blob/master/Stores/src/main/java/com/redhat/service/StoresWS.java)

{% hint style='tip' %}
This simple java class implements a JAX-WS SOAP webservice that allows consumers to create, delete or get Stores from RHMart. 
{% endhint %}

![](images/image203.png)