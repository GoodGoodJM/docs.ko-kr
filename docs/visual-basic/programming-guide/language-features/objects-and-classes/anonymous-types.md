---
title: 익명 형식(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: 46
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 530e21e1595f9bbc3436280418287413e2a48111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-types-visual-basic"></a>익명 형식(Visual Basic)
Visual Basic에서는 익명 형식, 데이터 형식에 대 한 클래스 정의 작성 하지 않고 개체를 만들 수 있도록 지원 합니다. 대신 컴파일러가 클래스를 생성합니다. 클래스는 사용 가능한 이름이 없으므로에서 직접 상속 <xref:System.Object>, 개체를 선언할 지정 하는 속성을 포함 합니다. 데이터 형식의 이름을 지정 되어 있지 않으므로 것 이라고는 *익명 형식*합니다.  
  
 다음 예제에서는 선언 하 고 변수를 만듭니다 `product` 두 속성이 있는 익명 형식의 인스턴스로 `Name` 및 `Price`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 A *쿼리 식* 익명 형식을 사용 하 여 쿼리를 통해 선택 된 데이터의 열을 결합 합니다. 특정 쿼리를 선택할 수 있는 열을 예측할 수 없는 사전에 결과의 형식을 정의할 수 없습니다. 익명 형식을 사용 순서에 관계 없이 임의 개수의 열을 선택 하는 쿼리를 작성할 수 있습니다. 컴파일러에 지정된 된 속성 및 지정된 된 순서와 일치 하는 데이터 형식을 만듭니다.  
  
 다음 예에서 `products` 는 많은 속성이 있으며 각 제품 개체 목록이 나와 있습니다. 변수 `namePriceQuery` 실행 될 때 두 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의 보유 `Name` 및 `Price`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 변수 `nameQuantityQuery` 실행 될 때 두 속성이 있는 익명 형식의 인스턴스 컬렉션을 반환 하는 쿼리 정의 보유 `Name` 및 `OnHand`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 익명 형식에 대 한 컴파일러에서 만든 코드에 대 한 자세한 내용은 참조 [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)합니다.  
  
> [!CAUTION]
>  익명 형식의 이름은 컴파일러에서 생성 되며 컴파일할 다를 수 있습니다. 코드를 사용 하거나 프로젝트를 다시 컴파일할 때 이름이 변경 될 수 있으므로 익명 형식의 이름을 사용 하지 않습니다.  
  
## <a name="declaring-an-anonymous-type"></a>익명 형식 선언  
 익명 형식의 인스턴스 선언 형식의 속성을 지정 하려면 이니셜라이저 목록을 사용 합니다. 익명 형식, 메서드 또는 이벤트와 같은 다른 클래스 요소 하지 선언 하는 경우 속성에 대해서만 지정할 수 있습니다. 다음 예에서 `product1` 두 속성이 있는 익명 형식의 인스턴스가: `Name` 및 `Price`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 키 속성으로 속성을 지정 하는 경우 익명 형식의 두 인스턴스가 같은지를 비교 하려면 사용할 수 있습니다. 그러나 키 속성의 값을 변경할 수 없습니다. 자세한 내용은이 항목의 뒷부분에 나오는 키 속성 섹션을 참조 하십시오.  
  
 익명 형식의 인스턴스 선언은 개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 선언 하 고 지 사항:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 익명 형식 속성을 지정 하는 다른 방법에 대 한 자세한 내용은 참조 [하는 방법: 익명 형식 선언에서 속성 이름 유추 및 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)합니다.  
  
## <a name="key-properties"></a>키 속성  
 키 속성 몇 가지 기본 방법에서 키가 아닌 속성과 다릅니다.  
  
-   두 인스턴스가 같은지 여부를 결정 하기 위해 키 속성의 값만 비교 됩니다.  
  
-   키 속성의 값 읽기 전용 이며 변경할 수 없습니다.  
  
-   익명 형식에 대 한 컴파일러에서 생성 된 해시 코드 알고리즘에만 키 속성 값 포함 됩니다.  
  
### <a name="equality"></a>같음  
 익명 형식의 인스턴스를 동일한 익명 형식의 인스턴스인 경우에 같을 수 있습니다. 컴파일러는 다음 조건을 충족 하는 경우 두 인스턴스가 동일한 형식의 인스턴스로 처리:  
  
-   동일한 어셈블리에 선언 됩니다.  
  
-   같은 이름의 동일한 유추 형식, 그룹 속성과 동일한 순서에도 선언 됩니다. 이름을 비교할 때는 대/소문자 구분 하지 않습니다.  
  
-   각 동일한 속성은 키 속성으로 표시 됩니다.  
  
-   각 선언에서 하나 이상의 속성이 키 속성이입니다.  
  
 키 속성이 없는 익명 형식의 인스턴스 자체에 같습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 해당 키 속성의 값이 같으면 동일한 익명 형식의 두 인스턴스가 같은지 합니다. 다음 예에서는 같음 테스트 되는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### <a name="read-only-values"></a>읽기 전용 값  
 키 속성의 값을 변경할 수 없습니다. 예를 들어 `prod8` 이전 예에서 `Name` 및 `Price` 필드는 `read-only`, 하지만 `OnHand` 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>쿼리 식에서 익명 형식  
 쿼리 식에서는 익명 형식 만들 항상 필요 하지 않습니다. 가능 하면 있습니다를 사용 하 여 기존 형식을 열 데이터입니다. 이 쿼리가 데이터 원본 또는 각 레코드의 필드 하나만의 전체 레코드 중 하나는 반환 될 때 발생 합니다. 다음 코드 예제에서 `customers` 은 개체의 컬렉션을 `Customer` 클래스입니다. 클래스에는 많은 속성이 고 하나 이상의 순서에 관계 없이 쿼리 결과에 포함할 수 있습니다. 처음 두 예제에서 쿼리 명명 된 형식의 요소를 선택 하기 때문에 익명 형식이 없습니다가 필요 합니다.  
  
-   `custs1`때문에 문자열의 컬렉션을 포함 `cust.Name` 는 문자열입니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2`컬렉션을 포함 `Customer` 때문에 개체의 각 요소 `customers` 는 `Customer` 개체 및 전체 요소는 쿼리에서 선택 됩니다.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 그러나 적절 한 명명 된 형식을 사용할 수 없는 경우가 있습니다. 고객 이름 및 고객 ID 번호, 다른 경우와 다른 위치에 대 한 주소 및 고객 이름, 주소 및 주문 기록을 선택 수 있습니다. 익명 형식을 사용 첫 번째 결과를 저장할 새 명명 된 형식을 선언 하지 않고 어떤 순서로 든 속성을 원하는 대로 선택할 수 있습니다. 대신, 컴파일러는 속성의 각 컴파일에 대 한 익명 형식을 만듭니다. 각 고객의 이름과 ID 번호를 선택 하는 다음 쿼리 `Customer` 개체 `customers`합니다. 따라서 컴파일러는 이러한 두 속성만 포함 하는 익명 형식을 만듭니다.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 이름과 익명 형식에서 속성의 데이터 형식은 모두에 대 한 인수에서 가져온 `Select`, `cust.Name` 및 `cust.ID`합니다. 쿼리에 의해 생성 된 익명 형식 속성은 항상 키 속성입니다. 때 `custs3` 다음에서 실행 `For Each` 루프, 결과 두 개의 키 속성이 있는 익명 형식의 인스턴스 컬렉션 `Name` 및 `ID`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 표시 되는 컬렉션의 요소 `custs3` 은 강력한 형식에서 사용 가능한 속성을 통해 탐색 하 고 해당 형식을 확인할 IntelliSense를 사용할 수 있습니다.  
  
 자세한 내용은 참조 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>익명 형식 사용할 것인지 결정  
 익명 클래스의 인스턴스 개체를 만들기 전에 가장 적합 한 옵션 인지 하는 것이 좋습니다. 예를 들어 관련된 데이터를 포함 하는 임시 개체를 만들려고 할 다른 필드와 완전 한 클래스가 포함 될 수 있는 방법에 대 한 필요 하지 않은 경우 익명 형식은 적합 한 솔루션입니다. 각 선언에 대 한 속성의 다른 선택 하려는 경우 또는 속성의 순서를 변경 하려는 경우 익명 형식은 편리 하 게 됩니다. 그러나 프로젝트에 고정 된 순서로 동일한 속성이 있는 여러 개체를 선언할 수 있습니다 더 쉽게 클래스 생성자가 있는 명명된 된 형식을 사용 하 여 합니다. 예를 들어 적절 한 생성자에서 쉽습니다의 여러 인스턴스를 선언 하는 `Product` 익명 형식의 여러 인스턴스를 선언 하는 것 보다 클래스입니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 명명 된 형식의 또 다른 이점은 컴파일러 속성 이름의 실수로 잘못 입력을 catch 할 수 있습니다. 앞의 예에서 `firstProd2`, `secondProd2`, 및 `thirdProd2` 동일한 익명 형식의 인스턴스 수입니다. 그러나 실수로 선언 `thirdProd2` 다음 방법 중 하나에 해당 형식을 다른 것 `firstProd2` 및 `secondProd2`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 무엇 보다도 명명 된 형식의 인스턴스는 적용 되지 않는 익명 형식의 사용에 제한이 있습니다. `firstProd2``secondProd2`, 및 `thirdProd2` 는 동일한 익명 형식의 인스턴스입니다. 그러나 공유 익명 형식에 대 한 이름을 사용할 수 없어서 형식 이름이 필요한 코드에 표시 될 수 없습니다. 예를 들어 다른 변수 또는 필드 또는 모든 형식 선언에서 선언 하는 메서드 시그니처를 정의 하는 익명 형식을 사용할 수 없습니다. 따라서 메서드 간에 정보를 공유 하는 경우 익명 형식은 적합 하지 않습니다.  
  
## <a name="an-anonymous-type-definition"></a>익명 형식 정의  
 익명 형식의 인스턴스 선언에 대 한 응답, 컴파일러는 지정 된 속성을 포함 하는 새 클래스 정을 만듭니다.  
  
 익명 형식 하나 이상의 키 속성에 포함 된 경우 정의에서 상속 되며, 세 명의 멤버를 재정의 하는 <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다. 코드 생성 같음 테스트 및 키 속성만 고려 하는 해시 코드 값을 결정 합니다. 익명 형식 없는 키 속성을 포함 하는 경우 <xref:System.Object.ToString%2A> 재정의 됩니다. 익명 형식을 명시적으로 명명 된 속성은 이러한 생성 된 메서드와 충돌 하지 않습니다. 사용할 수 없습니다, 즉 `.Equals`, `.GetHashCode`, 또는 `.ToString` 속성 이름을 지정 합니다.  
  
 하나 이상 포함 하는 익명 형식 정의 키 속성이 구현은 <xref:System.IEquatable%601?displayProperty=nameWithType> 인터페이스, 여기서 `T` 유형 익명 형식입니다.  
  
 컴파일러와 재정의 된 메서드의 기능에서 만든 코드에 대 한 자세한 내용은 참조 [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [익명 형식 정의](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [키](../../../../visual-basic/language-reference/modifiers/key.md)
