---
title: "컴파일러 오류 C3265 | Microsoft Docs"
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
  - "C3265"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3265"
ms.assetid: 10ab3e17-4a9f-4120-bab5-21473869b70f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3265
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 'managed construct'을\(를\) 관리되지 않는 'unmanaged construct'에서 선언할 수 없습니다.  
  
 관리되는 개체를 관리되지 않는 컨텍스트에 포함시킬 수 없습니다.  
  
 다음 샘플에서는 C3265 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3265_2.cpp  
// compile with: /clr /LD  
#include <vcclr.h>  
  
ref class A { };  
  
class B  
// try the following line instead  
// ref class B   
{  
   A ^a;   // C3265  
   // or embed the managed handle using gcroot  
   // try the following line instead  
   // gcroot<A^> a;  
};  
```  
  
 다음 샘플에서는 C3265 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3265.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc class A { };  
  
__nogc class B  
// try the following line instead  
// __gc class B   
{  
   A *a;   // C3265  
};  
```  
  
 C3265 오류는 관리되는 포인터를 관리되지 않는 클래스 안에 직접 포함하는 경우에도 발생할 수 있습니다.  이 오류를 해결하려면 `gcroot`를 사용하십시오.  
  
```  
// C3265b.cpp  
// compile with: /clr:oldSyntax  
#include <vcclr.h>  
#using <mscorlib.dll>  
  
namespace TestNS {  
   __gc public class Test{};  
}  
  
template<class T>  
struct Container {  
  T* m_px;   // C3265  
};  
__gc public class ClassA {  
public:  
  ClassA (){}  
   ~ClassA(){}  
  
private:  
   Container<TestNS::Test*>  vctTest;  
   // try the following line instead  
   Container<gcroot<TestNS::Test* > > vctTest2;  
};  
```