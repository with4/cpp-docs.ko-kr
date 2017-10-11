---
title: "컴파일러 오류 C2146 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2146
dev_langs:
- C++
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 92e94ae29c1a7a3fc6adfdc0b3e82f5ce4dfcaf0
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2146"></a>컴파일러 오류 C2146
구문 오류: 'token' 'identifier' 식별자 앞 누락  
  
 예상 컴파일러 `token` 발견 `identifier` 대신 합니다.  가능한 원인:  
  
1.  대/소문자 또는 맞춤법 오류입니다.  
  
2.  식별자의 선언에서 누락 된 형식 지정자입니다.  
  
 이 오류는 입력 오류 때문일 수 있습니다. 오류 [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) 일반적으로이 오류를 앞에 옵니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c2146 오류가 발생 합니다.  
  
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
  
## <a name="example"></a>예제  
 이 오류는 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 있습니다: 누락 된 `typename` 키워드입니다.  
  
 다음 샘플 Visual Studio.NET 2002에서 컴파일되도록 하지만 Visual Studio.NET 2003에서는 실패 합니다.  
  
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
  
## <a name="example"></a>예제  
 Visual Studio.NET 2003에 대해 수행한 컴파일러 규칙 작업의 결과로이 오류도 표시 됩니다: 명시적 특수화에는 더 이상 기본 템플릿에서 템플릿 매개 변수가 검색 합니다.  
  
 사용 하는 `T` 기본 템플릿에서에서 허용 되지 않는 명시적 특수화입니다. Visual c + +의 Visual Studio.NET 2003 및 Visual Studio.NET 버전에 유효한 것으로 코드에 대 한 모든 인스턴스의 한 특수화에 템플릿 매개 변수를 명시적으로 특수화 된 형식으로 대체 합니다.  
  
 다음 샘플 Visual Studio.NET에서 컴파일되도록 하지만 Visual Studio.NET 2003에서는 실패 합니다.  
  
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
