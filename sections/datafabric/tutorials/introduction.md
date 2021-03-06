---
author: Veracity
description: Description of introduction section
---

# Introduction

Veracity uses API Management. In order to get access, you will need to:
* Register at https://api-portal.veracity.com/
* Subscribe to the Veracity Platform API – Product, this will give you access to our DataAPI and ProvisionAPI with a subscription ID  

## Standard structure of API Call

Call header:
* **Ocp-Apim-Subscription-Key** - this header attribute is for API Management authentication
* **Authorization** - this header attribute needs to contain the Bearer Token that is received through authorization on Veracity  

Example:  

    GET https://api.veracity.com/veracity/datafabric/data/api/1/users/me HTTP/1.1
    Host: api.veracity.com
    Ocp-Apim-Subscription-Key: {subscription-Key}
    Authorization: Bearer {token}  

C# example:  

    var httpClient = new System.Net.Http.HttpClient();
    var request = new HttpRequestMessage(httpMethod, "https://api.veracity.com/veracity/datafabric/data/api/1/users/me");
    request.Headers.Add("Ocp-Apim-Subscription-Key", "{Subscription-Key}");
    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", "{accessToken}");

    var response = await httpClient.SendAsync(request);
