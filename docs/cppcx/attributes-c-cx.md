---
title: "특성(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 특성(C++/CX)
특성은 메타데이터 생성에서 특정 동작을 지정하기 위해 대괄호에 포함되어 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 및 메서드 앞에 추가될 수 있는 특수한 종류의 ref 클래스입니다. 몇 가지 미리 정의된 특성\(예: [Windows::Foundation::Metadata::WebHostHidden](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.webhosthiddenattribute.aspx)\)은 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 코드에서 일반적으로 사용됩니다. 이 예제에서는 특성이 클래스에 적용되는 방식을 보여 줍니다.  
  
 [!code-cpp[cx_attributes#01](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#01)]  
  
## 사용자 지정 특성  
 사용자 지정 특성을 정의할 수도 있습니다. 사용자 지정 특성은 다음과 같은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 규칙을 따라야 합니다.  
  
-   사용자 지정 특성에는 공용 필드만 포함될 수 있습니다.  
  
-   사용자 지정 특성 필드는 특성이 클래스에 적용될 때 초기화될 수 있습니다.  
  
-   필드는 다음 형식 중 하나일 수 있습니다.  
  
    -   int32\(int\)  
  
    -   uint32\(unsigned int\)  
  
    -   bool  
  
    -   Platform::String^  
  
    -   Windows::Foundation::HResult  
  
    -   Platform::Type^  
  
    -   public enum 클래스\(사용자 정의 열거형 포함\)  
  
 다음 예제에서는 사용자 지정 특성을 정의한 다음 사용할 때 초기화하는 방법을 보여 줍니다.  
  
 [!code-cpp[cx_attributes#02](../snippets/cpp/VS_Snippets_Misc/cx_attributes/cpp/class1.h#02)]  
  
## 참고 항목  
 [형식 시스템\(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)