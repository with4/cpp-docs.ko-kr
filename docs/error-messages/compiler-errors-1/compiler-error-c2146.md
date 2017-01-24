---
title: "컴파일러 오류 C2146 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2146"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2146"
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2146
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 'token'이\(가\) 'identifier' 식별자 앞에 없습니다.  
  
 `token`이 필요한 위치에 `identifier`가 대신 사용되었습니다.  가능한 원인  
  
1.  철자 또는 대문자 표시 오류입니다.  
  
2.  식별자의 선언 부분에 형식 지정자가 없습니다.  
  
 이 오류는 입력 오류 때문에 발생할 수도 있습니다.  일반적으로 오류 [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md)가 이 오류보다 먼저 발생합니다.  
  
## 예제  
 다음 샘플에서는 C2146 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2146.cpp  
class CDeclaredClass {};  
  
class CMyClass {  
   CUndeclared m_myClass;   // C2146  
   CDeclaredClass m_myClass2;   // OK  
};  
  
int main() {  
   int x;  
   int t x;   // C2146 : missing semicolon before 'x'  
}  
```  
  
## 예제  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 `typename` 키워드를 사용하지 않기 때문에 이 오류가 발생할 수도 있습니다.  
  
 다음 샘플은 Visual Studio .NET 2002에서는 컴파일되지만 Visual Studio .NET 2003에서는 컴파일되지 않습니다.  
  
```  
// C2146b.cpp  
// compile with: /c  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
  
template <typename T>  
X<T>::Y func() { }   // C2146  
  
// OK  
template <typename T>  
typename X<T>::Y func() { }  
```  
  
## 예제  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 명시적 특수화를 통해 기본 템플릿에서 템플릿 매개 변수를 찾지 않기 때문에 이 오류가 발생할 수도 있습니다.  
  
 Visual Studio .NET 2003에서는 기본 템플릿의 `T`를 명시적 특수화에 사용할 수 없습니다.  Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 되도록 하려면 특수화에 사용된 모든 템플릿 매개 변수의 인스턴스를 명시적으로 특수화된 형식으로 바꾸십시오.  
  
 다음 샘플은 Visual Studio .NET에서는 컴파일되지만 Visual Studio .NET 2003에서는 컴파일되지 않습니다.  
  
```  
// C2146_c.cpp  
// compile with: /c  
template <class T>   
struct S;  
  
template <>   
struct S<int> {  
   T m_t;   // C2146  
   int m_t2;   // OK  
};  
```