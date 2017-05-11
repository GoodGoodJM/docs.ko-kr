---
title: "&lt;clientCredentials&gt; 요소의 &lt;windows&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;clientCredentials&gt; 요소의 &lt;windows&gt;
클라이언트를 나타내는 데 사용되는 Windows 자격 증명의 설정을 지정합니다.  
  
## 구문  
  
```  
  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`allowedImpersonationLevel`|클라이언트가 서버에 전달하는 가장 기본 설정을 지정합니다.  클라이언트에서 선택하는 가장 모드는 서버에 적용되지 않습니다.  유효한 값은 다음과 같습니다.<br /><br /> -   Identification: 서버는 클라이언트의 ID 및 권한을 가져올 수 있지만 클라이언트를 가장할 수는 없습니다.<br />-   Impersonation: 서버는 로컬 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.<br />-   Delegation: 서버는 원격 시스템에서 클라이언트의 보안 컨텍스트를 가장할 수 있습니다.<br />-   Anonymous: 서버는 클라이언트를 가장 또는 식별할 수 없습니다.<br />-   None: 가장 수준이 지정되지 않습니다.<br /><br /> 기본값은 Identification입니다.  이 특성은 <xref:System.Security.Principal.TokenImpersonationLevel> 형식입니다.|  
|`allowNtlm`|이 속성을 `true`로 설정하면 Kerberos를 사용할 수 없는 경우 NTLM으로 인증을 다운그레이드할 수 있습니다.<br /><br /> 이 속성을 `false`로 설정하면 NTLM이 사용되는 경우 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서 예외를 throw합니다.  이 속성을 `false`로 설정하면 유선을 통해 NTLM 자격 증명을 보낼 수 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>   
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)