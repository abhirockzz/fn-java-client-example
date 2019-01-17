# Example for a Java client invoking a Function HTTP endpoint

Function endpoints are protected and need to be invoked using valid authentication context. You would need to use OCI Request Signature [as outlined in this document](https://docs.cloud.oracle.com/iaas/Content/API/Concepts/signingrequests.htm?TocPath=Developer%20Tools%20|REST%20APIs%20|_____4). This example shows how to invoke Functions HTTP endpoints using OCI Request Signature based Java Client

## Make sure you have the following information....

- your tenancy OCID, user OCID, fingerprint, private Key - [details here](https://docs.cloud.oracle.com/iaas/Content/API/Concepts/apisigningkey.htm)
- to find the HTTP endpoint for your function - execute `fn inspect fn <app_name> <function_name>` and the look out for value of `fnproject.io/fn/invokeEndpoint` attribute

## Details

- The HTTP interaction is in `FnClientCommon.java`
	- it is based [on this](https://docs.cloud.oracle.com/iaas/Content/API/Concepts/signingrequests.htm?TocPath=Developer%20Tools%20|REST%20APIs%20|_____4#Java)
	- it uses the [Apache HTTP Client](https://hc.apache.org/) (but you should be able to build an implementation using a client library of your choice)

- `FnHTTPGet.java` and `FnHTTPPost.java` are examples of invoking HTTP `GET` and `POST` respectively using `FnClientCommon.java`
