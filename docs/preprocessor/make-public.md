---
title: "make_public | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.make_public"
  - "make_public_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_public pragma"
  - "pragma, make_public"
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# make_public
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

네이티브 형식이 공용 어셈블리 액세스 가능성을 갖도록 지정합니다.  
  
## 구문  
  
```  
#pragma make_public(type)  
```  
  
#### 매개 변수  
 `type`은 공용 어셈블리 액세스 가능성을 갖도록 할 형식의 이름입니다.  
  
## 설명  
 `make_public`은 참조하려는 네이티브 형식이 변경할 수 없는 .h 파일에서 제공된 경우에 유용합니다.  공용 어셈블리 표시 유형이 있는 형식의 공용 함수 시그니처에서 네이티브 형식을 사용하려는 경우 해당 네이티브 형식에도 공용 어셈블리 액세스 가능성이 있어야 하며, 그렇지 않으면 컴파일러에서 경고를 생성합니다.  
  
 `make_public`은 전역 범위에서 지정해야 하며 선언된 지점부터 소스 코드 파일의 끝까지만 유효합니다.  
  
 네이티브 형식은 암시적으로 또는 명시적으로 전용일 수 있습니다. 자세한 내용은 [형식 표시 유형](../misc/type-visibility.md)을 참조하십시오.  
  
## 예제  
 다음 샘플은 두 네이티브 구조체에 대한 정의가 포함된 .h 파일의 내용입니다.  
  
```  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## 예제  
 다음 코드 샘플에서는 헤더 파일을 사용하며, `make_public`을 사용하여 네이티브 구조체를 명시적으로 public으로 표시하지 않는 경우 공용 관리되는 형식의 공용 함수 시그니처에서 네이티브 구조체를 사용하려고 하면 컴파일러에서 경고를 생성하는 것을 보여 줍니다.  
  
```  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)