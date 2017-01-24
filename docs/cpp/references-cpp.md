---
title: "참조 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "선언, 참조"
  - "개체[C++], 참조"
  - "참조"
  - "참조, 선언"
  - "참조, 포인터"
  - "개체 참조, 선언자 구문"
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 참조 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

참조는 포인터와 마찬가지로, 메모리의 다른 위치에 있는 개체의 주소를 저장합니다.  하지만 포인터와는 달리, 참조는 초기화되고 나면 다른 개체를 참조하도록 설정하거나 null로 설정할 수 없습니다.  명명된 변수를 참조하는 lvalue 참조와 [임시 개체](../cpp/temporary-objects.md)를 참조하는 rvalue 참조 등, 두 가지 종류의 참조가 있습니다.  & 연산자는 lvalue 참조를 나타내고, && 연산자는 컨텍스트에 따라 rvalue 참조나 범용 참조\(rvalue 또는 lvalue\)를 나타냅니다.  
  
 참조를 선언할 수 있는 구문은 다음과 같습니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 참조를 지정하는 임의의 유효한 선언자를 사용할 수 있습니다.  참조가 함수 또는 배열 형식에 대한 참조가 아닌 한 다음 단순화된 구문이 적용됩니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 참조를 선언하는 시퀀스는 다음과 같습니다.  
  
 1.  선언 지정자:  
  
-   선택적 저장소 클래스 지정자.  
  
-   선택적 **const** 및\/또는 `volatile` 한정자  
  
-   형식 지정자: 형식의 이름  
  
-   2.  선언자:  
  
-   선택적 Microsoft 전용 한정자.  자세한 내용은 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)를 참조하세요.  
  
-   & 연산자 또는 && 연산자입니다.  
  
-   선택적 **const** 및\/또는 `volatile` 한정자  
  
-   식별자입니다.  
  
 3.  선택적 이니셜라이저입니다.  
  
 배열 및 함수에 대한 포인터의 더 복잡한 선언자 형태도 배열 및 함수에 대한 참조에 적용됩니다. [포인터](../cpp/pointers-cpp.md) 및 [선언자](http://msdn.microsoft.com/ko-kr/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)를 참조하세요.  
  
 여러 선언자와 이니셜라이저가 단일 선언 지정자 뒤에 쉼표로 구분된 목록으로 나타날 수 있습니다.  예:  
  
```  
int &i;   
int &i, &j;   
```  
  
 참조, 포인터 및 개체를 함께 선언할 수 있습니다.  
  
```  
int &ref, *ptr, k;   
```  
  
 참조는 개체의 주소를 보유하지만 구문적으로 개체처럼 동작합니다.  
  
 다음 프로그램에서 개체 이름인 `Today`와 개체에 대한 참조인 `TodayRef`를 프로그램에서 동일하게 사용할 수 있습니다.  
  
## 예제  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
  **3**  
**3**  
**4**  
**4**   
## 주석  
 이 단원의 항목:  
  
-   [참조 형식 함수 인수](../cpp/reference-type-function-arguments.md)  
  
-   [참조 형식 함수 반환](../cpp/reference-type-function-returns.md)  
  
-   [포인터에 대한 참조](../cpp/references-to-pointers.md)  
  
## 참고 항목  
 [참조 초기화](../misc/initializing-references.md)