---
title: "onPremisesPublishing resource type"
description: "Represents an Application Proxy onPremisesPublishing object."
localization_priority: Normal
author: "japere"
ms.prod: "microsoft-identity-platform"
doc_type: resourcePageType
---

# onPremisesPublishing resource type

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

An on-premises application published via Application Proxy is represented by an [application](application.md) object and its associated **onPremisesPublishing** object. An **onPremisesPublishing** object represents the set of properties for configuring Application Proxy for an on-premises [application](application.md). After creating an application, the Application Proxy settings for the applicaiton can be configured by [updating the application's](../api/application-update.md) onPremisesPublishing object's properties.

## Properties

| Property|Type|Description|
|:---------------|:--------|:----------|
|applicationServerTimeout|String| The duration the connector will wait for a response from the backend application before closing the connection. At default, the backend application timeout has a length of 85 seconds. When set to long, the backend timeout is increased to 180 seconds. Possible values are `default`, `long`. Use `long` if your server takes more than 85 seconds to respond to requests or if you are unable to access the application and the error status is "Backend Timeout".|
|applicationType|String| <!--need description!--> |
|externalAuthenticationType|String| Details the pre-authentication setting for the application Possible values are: `passthru`, `aadPreAuthentication`. |
|externalUrl|String| The published external url for the application. For example, https://intranet-contoso.msappproxy.net/.  |
|internalUrl|String| The internal url of the application. For example, https://intranet/. |
|isHttpOnlyCookieEnabled|Boolean| Indicates if the HTTPOnly cookie flag should be set in the HTTP response headers. Set this value to Yes to have Application Proxy cookies include the HTTPOnly flag in the HTTP response headers. If using Remote Desktop Services, set this value to No. Default value is No. |
|isOnPremPublishingEnabled|Boolean| Indicates if the application is currently being published via Application Proxy or not. |
|isPersistentCookieEnabled|Boolean| Indicates if the Persistent cookie flag should be set in the HTTP response headers. Keep this value set to No. Only use this setting for applications that can't share cookies between processes. For more information about cookie settings, see [Cookie settings for accessing on-premises applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-cookie-settings). |
|isSecureCookieEnabled|Boolean| Indicates if the Secure cookie flag should be set in the HTTP response headers. Set this value to Yes to transmit cookies over a secure channel such as an encrypted HTTPS request. Default value is Yes.|
|isTranslateHostHeaderEnabled|Boolean| Indicates if the application should translate urls in the reponse headers. Keep this value as Yes unless your application required the original host header in the authentication request. |
|isTranslateLinksInBodyEnabled|Boolean| Indicates if the application should translate urls in the application body. Keep this value as No unless you have hardcoded HTML links to other on-premises applications and don't use custom domains. For more information, see [Link translation with Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-hard-coded-link-translation).|
|singleSignOnSettings|[onPremisesPublishingSingleSignOn](onpremisespublishingsinglesignon.md)| Represents the single sign-on configuration for the on-premises application. |
|verifiedCustomDomainCertificatesMetadata|[verifiedCustomDomainCertificatesMetadata](verifiedcustomdomaincertificatesmetadata.md)| Details of the certificate associated with the application when a custom domain is in use. Null when using the default domain. |
|verifiedCustomDomainKeyCredential|[keyCredential](keycredential.md)| The associated key credential for the custom domain used. |
|verifiedCustomDomainPasswordCredential|[passwordCredential](passwordcredential.md)| The associated password credential for the custom domain used. |



## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.onPremisesPublishing"
}-->

```json
{
  "applicationServerTimeout": "String",
  "applicationType": "String",
  "externalAuthenticationType": "String",
  "externalUrl": "String",
  "internalUrl": "String",
  "isHttpOnlyCookieEnabled": true,
  "isOnPremPublishingEnabled": true,
  "isPersistentCookieEnabled": true,
  "isSecureCookieEnabled": true,
  "isTranslateHostHeaderEnabled": true,
  "isTranslateLinksInBodyEnabled": true,
  "singleSignOnSettings": {"@odata.type": "microsoft.graph.onPremisesPublishingSingleSignOn"},
  "verifiedCustomDomainCertificatesMetadata": {"@odata.type": "microsoft.graph.verifiedCustomDomainCertificatesMetadata"},
  "verifiedCustomDomainKeyCredential": {"@odata.type": "microsoft.graph.keyCredential"},
  "verifiedCustomDomainPasswordCredential": {"@odata.type": "microsoft.graph.passwordCredential"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2019-02-04 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "onPremisesPublishing resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
