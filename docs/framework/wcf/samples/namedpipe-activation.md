---
title: "NamedPipe 활성화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2d7c722078947e86e677f57c67d87ba69a0f524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="namedpipe-activation"></a>NamedPipe 활성화
이 샘플에서는 WAS(Windows Process Activation Service)를 사용하는 서비스를 호스트하여 이름 파이프를 통해 통신하는 서비스를 활성화하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 으로 이루어지며 [!INCLUDE[wv](../../../../includes/wv-md.md)] 실행 되도록 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플은 WAS(Windows Process Activation Services)에 의해 활성화된 작업자 프로세스에서 호스트되는 서비스 라이브러리(.dll) 및 클라이언트 콘솔 프로그램(.exe)으로 구성됩니다. 콘솔 창에는 클라이언트 동작이 표시됩니다.  
  
 이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다. 계약은 다음 샘플 코드처럼 수학 연산(더하기, 빼기, 곱하기 및 나누기)을 노출시키는 `ICalculator` 인터페이스에서 정의됩니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 클라이언트에서는 지정된 수학 연산을 동기적으로 요청하고 서비스 구현에서는 계산을 통해 올바른 결과를 반환합니다.  
  
```  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 샘플에서는 보안 없이 수정된 `netNamedPipeBinding` 바인딩을 사용합니다. 클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다. 서비스의 바인딩 형식은 다음 샘플 구성과 같이 끝점 요소의 `binding` 특성에 지정됩니다.  
  
 보안이 설정된 명명된 파이프 바인딩을 사용하려면 서버의 보안 모드를 원하는 보안 설정으로 변경하고 클라이언트에서 svcutil.exe를 다시 실행하여 업데이트된 클라이언트 구성 파일을 가져옵니다.  
  
```xml  
<system.serviceModel>  
        <services>  
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
  
        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->  
        <endpoint address=""   
                  binding="netNamedPipeBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexNamedPipeBinding"  
                  contract="IMetadataExchange" />  
      </service>  
        </services>      
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="Binding1" >  
                    <security mode = "None">  
                    </security>  
                </binding >  
            </netNamedPipeBinding>  
        </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 클라이언트의 끝점 정보는 다음 샘플 코드와 같이 구성됩니다.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <endpoint name=""  
                          address="net.pipe://localhost/servicemodelsamples/service.svc"   
                          binding="netNamedPipeBinding"   
                          bindingConfiguration="Binding1"   
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
    <bindings>  
  
      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.  
            Each property is configured with the default value.   -->  
  
      <netNamedPipeBinding>  
        <binding name="Binding1"   
                         maxBufferSize="65536"  
                         maxConnections="10">  
          <security mode = "None">  
          </security>  
        </binding >  
  
      </netNamedPipeBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다. 클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[iisver](../../../../includes/iisver-md.md)]이 설치되어 있는지 확인합니다. [!INCLUDE[iisver](../../../../includes/iisver-md.md)]은 WAS 활성화에 필요합니다.  
  
2.  수행 했는지 확인는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
     또한 HTTP가 아닌 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 활성화 구성 요소를 설치해야 합니다.  
  
    1.  **시작** 메뉴 선택 **제어판**합니다.  
  
    2.  선택 **프로그램 및 기능**합니다.  
  
    3.  클릭 **Windows 구성 요소를 켜거나 끄려면**합니다.  
  
    4.  확장 된 **Microsoft.NET Framework 3.0** 노드와 검사는 **Windows Communication Foundation 비-HTTP 활성화** 기능입니다.  
  
3.  명명된 파이프 활성화를 지원하도록 WAS(Windows Process Activation Service)를 구성합니다.  
  
     편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 AddNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.  
  
    1.  net. pipe 활성화를 지원하려면 먼저 기본 웹 사이트를 net. pipe 프로토콜에 바인딩해야 합니다. 이 작업은 IIS 7.0 관리 도구 집합과 함께 설치되는 appcmd.exe를 사용하여 수행할 수 있습니다. 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        -+bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
         이 명령은 기본 웹 사이트에 net.pipe 사이트 바인딩을 추가합니다.  
  
    2.  사이트 내의 모든 응용 프로그램에서 공통된 net.pipe 바인딩을 공유하지만 각 응용 프로그램에서 net.pipe 지원을 개별적으로 사용하도록 설정할 수 있습니다. /servicemodelsamples 응용 프로그램에서 net.pipe를 사용하도록 설정하려면 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
         이 명령을 실행하면 http://localhost/servicemodelsamples와 net.tcp://localhost/servicemodelsamples를 모두 사용하여 /servicemodelsamples 응용 프로그램에 액세스할 수 있습니다.  
  
4.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
5.  이 샘플에 대해 추가한 net. pipe 사이트 바인딩을 제거합니다.  
  
     편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.  
  
    1.  권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 사용된 프로토콜 목록에서 net.tcp를 제거합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
    2.  권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
