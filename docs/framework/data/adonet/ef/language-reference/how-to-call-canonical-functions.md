---
title: "방법: 정식 함수 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b3d84873-7403-4957-8e20-b4ae39f50214
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 97ad63ea2aeb5ef1ef1acd1988254e995dbc63e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-canonical-functions"></a>방법: 정식 함수 호출
<xref:System.Data.Objects.EntityFunctions> 클래스에는 LINQ to Entities 쿼리에 사용할 정식 함수를 노출하는 메서드가 포함되어 있습니다. 정식 함수에 대한 자세한 내용은 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)를 참조하세요.  
  
> [!NOTE]
>  <xref:System.Data.Objects.EntityFunctions.AsUnicode%2A> 클래스의 <xref:System.Data.Objects.EntityFunctions.AsNonUnicode%2A> 및 <xref:System.Data.Objects.EntityFunctions> 메서드에는 해당하는 정식 함수가 없습니다.  
  
 값 집합에 대한 계산을 수행하고 단일 값을 반환하는 정식 함수(집계 정식 함수라고도 함)는 직접 호출할 수 있습니다. 기타 정식 함수는 LINQ to Entities 쿼리의 일부로만 호출할 수 있습니다. 집계 함수를 직접 호출하려면 <xref:System.Data.Objects.ObjectQuery%601>를 함수로 전달해야 합니다. 자세한 내용은 아래 두 번째 예제를 참조하세요.  
  
 LINQ to Entities 쿼리에서 CLR(공용 언어 런타임) 메서드를 사용하여 일부 정식 함수를 호출할 수 있습니다. 정식 함수에 매핑되는 CLR 메서드에서만 목록은 참조 [정식 함수 매핑을 대 한 CLR 메서드](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)합니다. 이 예제에서는 <xref:System.Data.Objects.EntityFunctions.DiffDays%2A> 메서드를 사용하여 `SellEndDate`와 `SellStartDate`의 차이가 365일 미만인 제품을 모두 반환하는 LINQ to Entities 쿼리를 실행합니다.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#1)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#1)]  
  
## <a name="example"></a>예  
 다음 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)합니다. 이 예제에서는 집계 <xref:System.Data.Objects.EntityFunctions.StandardDeviation%2A> 메서드를 직접 호출하여 `SalesOrderHeader` 부분합의 표준 편차를 반환합니다. <xref:System.Data.Objects.ObjectQuery%601>는 LINQ to Entities 쿼리에 포함되지 않고 호출되도록 지정하는 함수로 전달됩니다.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#2)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities 쿼리에서 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
