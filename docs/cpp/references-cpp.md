---
title: 참조 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 174ab622b177766a33dd55f6b3c78ac38c26ded1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956595"
---
# <a name="references-c"></a>참조 (C++)
참조는 포인터와 마찬가지로, 메모리의 다른 위치에 있는 개체의 주소를 저장합니다. 하지만 포인터와는 달리, 참조는 초기화되고 나면 다른 개체를 참조하도록 설정하거나 null로 설정할 수 없습니다. 두 가지 종류의 참조: 참조 하는 명명 된 변수 및 rvalue 참조에 대 한 참조는 lvalue 참조를 [임시 개체](../cpp/temporary-objects.md)합니다. & 연산자는 lvalue 참조를 나타내고, && 연산자는 컨텍스트에 따라 rvalue 참조나 범용 참조(rvalue 또는 lvalue)를 나타냅니다.  
  
 참조를 선언할 수 있는 구문은 다음과 같습니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 참조를 지정하는 임의의 유효한 선언자를 사용할 수 있습니다. 참조가 함수 또는 배열 형식에 대한 참조가 아닌 한 다음 단순화된 구문이 적용됩니다.  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 참조를 선언하는 시퀀스는 다음과 같습니다.  
  
 1. 선언 지정자:  
  
-   선택적 저장소 클래스 지정자.  
  
-   선택적 **상수** 및/또는 **volatile** 한정자입니다.  
  
-   형식 지정자: 형식의 이름  
  
-   2. 선언자:  
  
-   선택적 Microsoft 전용 한정자. 자세한 내용은 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)합니다.  
  
-   & 연산자 또는 && 연산자입니다.  
  
-   선택적 **상수** 및/또는 **volatile** 한정자입니다.  
  
-   식별자입니다.  
  
 3. 선택적 이니셜라이저입니다.  
  
 더 복잡 한 선언 자 형태도 배열 및 함수에 대 한 참조 배열 및 함수에 대 한 포인터에 적용할 참조 [포인터](../cpp/pointers-cpp.md)합니다.  
  
 여러 선언자와 이니셜라이저가 단일 선언 지정자 뒤에 쉼표로 구분된 목록으로 나타날 수 있습니다. 예를 들어:  
  
```cpp 
int &i;   
int &i, &j;   
```  
  
 참조, 포인터 및 개체를 함께 선언할 수 있습니다.  
  
```cpp 
int &ref, *ptr, k;   
```  
  
 참조는 개체의 주소를 보유하지만 구문적으로 개체처럼 동작합니다.  
  
 다음 프로그램에서 개체 이름인 `Today`와 개체에 대한 참조인 `TodayRef`를 프로그램에서 동일하게 사용할 수 있습니다.  
  
## <a name="example"></a>예  
  
```cpp 
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
  
```Output  
3  
3  
4  
4  
```  
  
## <a name="comment"></a>주석  
 이 단원의 항목:  
  
-   [참조 형식 함수 인수](../cpp/reference-type-function-arguments.md)  
  
-   [참조 형식 함수 반환](../cpp/reference-type-function-returns.md)  
  
-   [포인터에 대한 참조](../cpp/references-to-pointers.md)  
  
