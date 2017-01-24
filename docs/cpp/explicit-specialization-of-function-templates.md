---
title: "함수 템플릿의 명시적 특수화 | Microsoft Docs"
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
  - "함수 선언, 함수 템플릿의 특수화"
  - "함수 템플릿의 명시적 특수화"
  - "함수 템플릿, 특수화"
  - "재정의, 함수"
  - "함수 템플릿의 특수화"
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 함수 템플릿의 명시적 특수화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

함수 템플릿을 사용하면 특정 형식에 대한 함수 템플릿의 명시적 특수화\(재정의\)를 제공하여 해당 형식에 대한 특별한 동작을 정의할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
template<> void MySwap(double a, double b);  
```  
  
 이 선언으로 **double** 변수에 대한 다른 함수를 정의할 수 있습니다.  비템플릿 함수와 마찬가지로, 표준 형식 변환\(예: **float** 형식의 변수를 **double**로 확장\)이 적용됩니다.  
  
## 예제  
  
```  
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
  
## 참고 항목  
 [함수 템플릿](../cpp/function-templates.md)