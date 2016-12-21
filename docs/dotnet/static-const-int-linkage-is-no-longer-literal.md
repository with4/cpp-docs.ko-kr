---
title: "Static Const Int 링크가 더 이상 리터럴이 아닙니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상수, 선언"
  - "정수 계열 상수 식"
  - "literal 특성[C++]"
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Static Const Int 링크가 더 이상 리터럴이 아닙니다.
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 클래스의 상수 멤버를 선언하는 방법이 Managed Extensions for C\+\+와 다르게 변경되었습니다.  
  
 `static const` 정수 계열 멤버는 여전히 지원되지만 이들 멤버의 링크 특성이 변경되었습니다.  이전 링크 특성은 이제 리터럴 정수 계열 멤버에 포함됩니다.  예를 들어 다음과 같은 Managed Extensions 클래스를 살펴 봅니다.  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 이 코드에서는 다음과 같은 필드에 대한 내부 CIL 특성을 생성합니다. 여기서 리터럴 특성에 주목하십시오.  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 다음과 같은 코드는 새 구문에서도 컴파일됩니다.  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 그러나 리터럴 특성이 더 이상 생성되지 않으므로 CLR 런타임에서 상수로 인식되지 않습니다.  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 동일한 언어간 리터럴 특성을 얻으려면 선언을 다음과 같이 새로 지원되는 `literal` 데이터 멤버로 변경해야 합니다.  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## 참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [literal](../windows/literal-cpp-component-extensions.md)