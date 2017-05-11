---
title: "요소 트리 및 serialization | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AutoGeneratedOrientationPage"
helpviewer_keywords: 
  - "요소 트리"
  - "serialization"
  - "트리[WPF]"
ms.assetid: 8f57e879-180b-421f-b3d0-ac007ff2ce80
caps.latest.revision: 71
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 70
---
# 요소 트리 및 serialization
WPF 프로그래밍 요소는 서로 트리 관계 형태로 존재하는 경우가 많습니다.  예를 들어 XAML로 만들어진 응용 프로그램 UI는 개체 트리로 개념화될 수 있습니다.  요소 트리는, 서로 별개지만 경우에 따라 병렬적인 트리로 나타나는 [논리 트리](GTMT)와 [시각적 트리](GTMT)로 나눌 수 있습니다.  WPF에서 serialization에는 이 두 트리의 상태와 응용 프로그램 상태를 저장하고 이를 파일에 XAML 등으로 쓰는 작업이 포함됩니다.  
  
## 단원 내용  
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [XamlWriter.Save의 serialization 제한](../../../../docs/framework/wpf/advanced/serialization-limitations-of-xamlwriter-save.md)  
 [개체 트리에 없는 개체 요소 초기화](../../../../docs/framework/wpf/advanced/initialization-for-object-elements-not-in-an-object-tree.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/element-tree-and-serialization-how-to-topics.md)  
  
## 참조  
 <xref:System.Windows.Markup>  
  
 <xref:System.Windows.LogicalTreeHelper>  
  
 <xref:System.Windows.Media.VisualTreeHelper>  
  
## 관련 단원  
 [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
 [WPF의 XAML](../../../../docs/framework/wpf/advanced/xaml-in-wpf.md)  
 [기본 요소](../../../../docs/framework/wpf/advanced/base-elements.md)  
 [속성](../../../../docs/framework/wpf/advanced/properties-wpf.md)  
 [이벤트](../../../../docs/framework/wpf/advanced/events-wpf.md)  
 [입력](../../../../docs/framework/wpf/advanced/input-wpf.md)  
 [리소스](../../../../docs/framework/wpf/advanced/resources-wpf.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [스레딩 모델](../../../../docs/framework/wpf/advanced/threading-model.md)