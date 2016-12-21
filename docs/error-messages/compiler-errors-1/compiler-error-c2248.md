---
title: "컴파일러 오류 C2248 | Microsoft Docs"
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
  - "C2248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2248"
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 'class' 클래스에 선언된 'access' 멤버에 액세스할 수 없습니다.  
  
 파생 클래스의 멤버는 기본 클래스의 `private` 멤버에 액세스할 수 없습니다.  클래스 인스턴스의 `private` 또는 `protected` 멤버에 액세스할 수 없습니다.  
  
 C2248에 대한 자세한 내용은 기술 자료 문서 KB243351을 참조하십시오.  
  
 다음 샘플에서는 C2248 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2248.cpp  
#include <stdio.h>  
class X {  
public:  
   int  m_pubMemb;  
   void setPrivMemb( int i ) {  
      m_privMemb = i;  
      printf_s("\n%d", m_privMemb);  
   }  
protected:  
   int  m_protMemb;  
  
private:  
   int  m_privMemb;  
} x;  
  
int main() {  
   x.m_pubMemb = 4;  
   printf_s("\n%d", x.m_pubMemb);  
   x.m_protMemb = 2;   // C2248 m_protMemb is protected  
   x.m_privMemb = 3;   // C2248  m_privMemb is private  
   x.setPrivMemb(0);   // OK uses public access function  
}  
```  
  
 컴파일러 규칙에 따라 템플릿 friend 및 특수화를 사용하는 경우에도 C2248이 발생할 수 있습니다.  자세한 내용은 [링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)를 참조하십시오.  
  
```  
// C2248_b.cpp  
template<class T>  
void f(T t) {  
   t.i;   // C2248  
}  
  
struct S {  
private:  
   int i;  
  
public:  
   S() {}  
   // Delete the following line to resolve.  
   friend void f(S);   // refer to the non-template function void f(S)  
  
   // Uncomment the following line to resolve.  
   // friend void f<S>(S);  
};  
  
int main() {  
   S s;  
   f<S>(s);  
}  
```  
  
 컴파일러 규칙에 따라 클래스의 friend를 선언할 때 클래스 범위 안에서 이 클래스가 friend 선언에 보이지 않는 경우에도 C2248이 발생할 수 있습니다.  이러한 경우 오류를 해결하려면 바깥쪽 클래스를 friend로 선언하십시오.  
  
```  
// C2248_c.cpp  
// compile with: /c  
class T {  
   class S {  
      class E {};  
   };  
   friend class S::E;   // C2248  
};  
  
class A {  
   class S {  
      class E {};  
      friend class A;   // grant friendship to enclosing class  
   };  
   friend class S::E;   // OK  
};  
```