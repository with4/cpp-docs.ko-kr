---
title: "컴파일러 오류 C2993 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2993"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2993"
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2993
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 비형식 템플릿 매개 변수 'parameter'과\(와\) 맞지 않는 형식입니다.  
  
 템플릿을 구조체 또는 공용 구조체 인수와 함께 선언할 수 없습니다.  포인터를 사용하여 구조체 및 공용 구조체를 템플릿 매개 변수로서 전달하십시오.  
  
 다음 샘플에서는 C2993 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 부동 소수점 비형식 템플릿 매개 변수를 사용할 수 없기 때문에 이 오류가 발생할 수도 있습니다.  C\+\+ 표준에서는 부동 소수점 비형식 템플릿 매개 변수를 허용하지 않습니다.  
  
 함수 템플릿일 경우에는 함수 인수를 사용하여 부동 소수점 비형식 템플릿 매개 변수를 전달하십시오. 이렇게 하면 Visual Studio .NET 2003과 Visual Studio .NET 버전의 Visual C\+\+ 모두에서 올바른 코드가 됩니다.  클래스 템플릿일 경우에는 이 문제를 쉽게 해결할 수 있는 방법이 없습니다.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```