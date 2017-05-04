---
title: "템플릿 ref 클래스(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# 템플릿 ref 클래스(C++/CX)
C\+\+ 템플릿은 메타데이터에 게시되지 않으므로 프로그램에서 public 또는 protected 액세스 가능성을 가질 수 없습니다. 물론 표준 C\+\+ 템플릿을 프로그램에서 내부적으로 사용할 수 있습니다. 또한 private ref 클래스를 템플릿으로 정의하고 명시적으로 특수화된 템플릿 ref 클래스를 public ref 클래스에서 private 멤버로 선언할 수 있습니다.  
  
## ref 클래스 템플릿 작성  
 다음 예제에서는 private ref 클래스를 템플릿으로 선언하는 방법 및 표준 C\+\+ 템플릿을 선언하는 방법과 이 둘을 public ref 클래스에서 멤버로 선언하는 방법을 보여 줍니다. 표준 C\+\+ 템플릿은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식\(이 경우에는 Platform::String^\)으로 특수화될 수 있습니다.  
  
 [!code-cpp[cx_templates#01](../snippets/cpp/VS_Snippets_Misc/cx_templates/cpp/class1.h#01)]  
  
## 참고 항목  
 [형식 시스템\(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)