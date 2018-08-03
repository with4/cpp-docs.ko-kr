---
title: 함수 템플릿의 명시적 특수화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8b6a56a0a1dce5d07007898dec486d0e3b080c4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407691"
---
# <a name="explicit-specialization-of-function-templates"></a>함수 템플릿의 명시적 특수화
함수 템플릿을 사용하면 특정 형식에 대한 함수 템플릿의 명시적 특수화(재정의)를 제공하여 해당 형식에 대한 특별한 동작을 정의할 수 있습니다. 예를 들어:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 이 선언에 대 한 다른 함수를 정의할 수 있도록 메시지를 표시 합니다 **이중** 변수입니다. 비템플릿 함수를 표준 형식 변환을 처럼 (같은 형식의 변수로 승격 **float** 하 **double**) 적용 됩니다.  
  
## <a name="example"></a>예  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>참고자료  
 [함수 템플릿](../cpp/function-templates.md)