---
title: 초기 바인딩 및 런타임에 바인딩(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aceffe59fb6043b3089621b9a3f95b0425f9a522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="early-and-late-binding-visual-basic"></a>초기 바인딩 및 런타임에 바인딩(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러는 개체가 개체 변수에 할당될 때 `binding`이라는 프로세스를 수행합니다. 개체는 특정 개체 형식으로 선언된 변수에 할당되면 *초기 바인딩*됩니다. 초기 바인딩된 개체는 응용 프로그램이 실행되기 전에 컴파일러가 메모리를 할당하고 기타 최적화를 수행할 수 있도록 합니다. 예를 들어 다음 코드 조각에서는 변수를 <xref:System.IO.FileStream> 형식으로 선언합니다.  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 <xref:System.IO.FileStream>이 특정 개체 형식이므로 `FS`에 할당된 인스턴스는 초기에 바인딩됩니다.  
  
 반대로 개체에 `Object` 형식으로 선언된 변수에 할당되면 *런타임에 바인딩*됩니다. 이 형식의 개체는 모든 개체에 대한 참조를 유지할 수 있지만 초기 바인딩 개체의 다양한 장점은 제공하지 못합니다. 예를 들어 다음 코드 조각에서는 `CreateObject` 함수가 반환하는 개체를 포함하도록 개체 변수를 선언합니다.  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a>초기 바인딩의 장점  
 초기 바인딩된 개체는 컴파일러가 보다 효율적인 응용 프로그램을 생성하는 중요한 최적화를 수행할 수 있도록 하므로 가능한 경우 항상 초기 바인딩된 개체를 사용하는 것이 좋습니다. 초기 바인딩된 개체는 런타임에 바인딩된 개체보다 훨씬 더 빠르며, 사용되는 개체 종류를 정확히 언급하여 코드를 보다 쉽게 읽고 유지 관리하도록 합니다. 초기 바인딩의 또 다른 장점은 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] IDE(통합 개발 환경)가 코드를 편집할 때 작업하는 개체의 형식을 정확히 파악할 수 있으므로 자동 코드 완성 및 동적 도움말 같은 유용한 기능을 사용할 수 있다는 것입니다. 초기 바인딩의 경우 프로그램이 컴파일될 때 컴파일러가 오류를 보고할 수 있으므로 런타임 오류의 수와 심각도도 줄어듭니다.  
  
> [!NOTE]
>  런타임에 바인딩은 `Public`으로 선언된 형식 멤버에 액세스하는 데만 사용할 수 있습니다. `Friend` 또는 `Protected Friend`로 선언된 멤버에 액세스하면 런타임 오류가 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [개체 수명: 개체가 만들어지고 제거되는 방법](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)
