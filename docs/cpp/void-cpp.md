---
title: "void (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "void"
  - "void_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "함수[C++], void"
  - "포인터, void"
  - "void 키워드[C++]"
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# void (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수 반환 형식으로 사용된 경우 `void` 키워드는 함수가 값을 반환하지 않도록 지정합니다.  함수의 매개 변수 목록에 사용된 경우 void는 함수가 매개 변수를 사용하지 않도록 지정합니다.  포인터 선언에 사용된 경우 void는 포인터를 "범용"으로 지정합니다.  
  
 포인터 형식이 **void \***이면 포인터가 **const** 또는 `volatile` 키워드로 선언되지 않은 모든 변수를 가리킬 수 있습니다.  void 포인터는 다른 형식으로 캐스팅되지 않은 경우 역참조할 수 없습니다.  void 포인터를 다른 형식의 데이터 포인터로 변환할 수 있습니다.  
  
 void 포인터는 함수를 가리킬 수 있지만 C\+\+의 클래스 멤버는 가리킬 수 없습니다.  
  
 void 형식의 변수는 선언할 수 없습니다.  
  
## 예제  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [void 형식에 대한 포인터](../misc/pointers-to-type-void.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)