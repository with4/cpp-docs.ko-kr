---
title: "함수 템플릿 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- function templates
- templates, function
- function templates, about function templates
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4186329b164ab3fe6daba12ed3cbbd2008085fb9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="function-templates"></a>함수 템플릿
클래스 템플릿은 인스턴스화할 때 클래스에 전달되는 형식 인수를 기반으로 하는 관련 클래스 패밀리를 정의합니다. 함수 템플릿은 클래스 템플릿과 유사하지만 함수 패밀리를 정의합니다. 함수 템플릿을 사용하면 동일한 코드를 기반으로 하지만 서로 다른 형식이나 클래스에서 작동하는 함수 집합을 지정할 수 있습니다. 다음 함수 템플릿은 두 항목을 바꿉니다.  
  
```cpp
// function_templates1.cpp  
template< class T > void MySwap( T& a, T& b ) {  
   T c(a);   
   a = b;   
   b = c;  
}  
int main() {  
}  
```  
  
 이 코드는 인수 값을 바꾸는 함수 패밀리를 정의합니다. 이 서식 파일에서 바꾸는 함수를 생성할 수 있습니다 **int** 및 **긴** 형식 및 사용자 정의 형식입니다. 클래스의 복사 생성자와 대입 연산자가 제대로 정의된 경우 `MySwap`으로 클래스도 바꿀 수 있습니다.  
  
 또한 컴파일러는 컴파일 타임에 `a` 및 `b` 매개 변수의 형식을 알기 때문에 함수 템플릿을 사용하면 형식이 서로 다른 개체를 바꿀 수 없게 됩니다.  
  
 이 함수는 void 포인터를 사용하여 템플릿이 아닌 함수로 실행할 수 있지만 템플릿 버전은 형식 안정적입니다. 다음 호출을 참조하십시오.  
  
```cpp
int j = 10;  
int k = 18;  
CString Hello = "Hello, Windows!";  
MySwap( j, k );          //OK  
MySwap( j, Hello );      //error  
```  
  
 컴파일러가 형식이 다른 매개 변수를 사용하여 `MySwap` 함수를 생성할 수 없으므로 두 번째 `MySwap` 호출은 컴파일 타임 오류를 트리거합니다. void 포인터가 사용된 경우 두 함수 호출 모두 올바르게 컴파일되지만 런타임에는 함수가 제대로 작동하지 않습니다.  
  
 함수 템플릿에 대한 템플릿 인수는 명시적으로 지정할 수 있습니다. 예:  
  
```cpp
// function_templates2.cpp  
template<class T> void f(T) {}  
int main(int j) {  
   f<char>(j);   // Generate the specialization f(char).  
   // If not explicitly specified, f(int) would be deduced.  
}  
```  
  
 템플릿 인수가 명시적으로 지정되면 함수 인수를 해당 함수 템플릿 매개 변수의 형식으로 변환하기 위해 표준 암시적 변환이 수행됩니다. 위의 예제에서 컴파일러는 변환 `char j` 입력 `int`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서식 파일](../cpp/templates-cpp.md)   
 [함수 템플릿 인스턴스화](../cpp/function-template-instantiation.md)   
 [명시적 인스턴스화](../cpp/explicit-instantiation.md)   
 [함수 템플릿의 명시적 특수화](../cpp/explicit-specialization-of-function-templates.md)
