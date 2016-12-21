---
title: "protected (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "protected"
  - "protected_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "protected 키워드[C++]"
  - "protected 키워드[C++], 멤버 액세스"
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# protected (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## 설명  
 `protected` 키워드는 *member\-list*의 클래스 멤버에 대한 액세스를 다음 액세스 지정자\(**public** 또는 `private`\) 또는 클래스 정의의 끝까지 지정합니다.  `protected`로 선언된 클래스 멤버는 다음에만 사용할 수 있습니다.  
  
-   원래 이 멤버를 선언한 클래스의 멤버 함수  
  
-   원래 이 멤버를 선언한 클래스의 friend  
  
-   원래 이 멤버를 선언한 클래스에서 공용 또는 보호된 액세스로 파생 클래스  
  
-   보호된 멤버에 대해 전용 액세스 권한이 있으며 전용으로 직접 파생 클래스  
  
 기본 클래스 이름 앞에 오는 `protected` 키워드는 기본 클래스의 공용 및 보호된 멤버가 파생된 해당 클래스의 보호된 멤버라고 지정합니다.  
  
 보호된 멤버는 선언된 클래스의 멤버에만 액세스할 수 있는 `private` 멤버만큼 전용은 아니지만 어느 함수에서나 액세스할 수 있는 **public** 멤버만큼 공용도 아닙니다.  
  
 **static**으로도 선언된 보호된 멤버는 파생 클래스의 friend나 멤버 함수에 액세스할 수 있습니다.  **static**으로 선언되지 않은 보호된 멤버는 파생 클래스의 포인터, 참조 또는 개체를 통해서만 파생 클래스의 friend와 멤버 함수에 액세스할 수 있습니다.  
  
 관련 정보는 [friend](../cpp/friend-cpp.md), [public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md) 및 [클래스 멤버에 대한 액세스 제어](../misc/controlling-access-to-class-members.md)의 멤버 액세스 테이블을 참조하세요.  
  
## \/clr 관련  
 CLR 형식에서 C\+\+ 액세스 지정자 키워드\(**public**, `private` 및 `protected`\)는 어셈블리와 관련된 형식 및 메서드의 표시 유형에 영향을 줄 수 있습니다.  자세한 내용은 [형식 멤버 표시 유형](../misc/type-and-member-visibility.md)을 참조하세요.  
  
> [!NOTE]
>  [\/LN](../build/reference/ln-create-msil-module.md)으로 컴파일된 파일은 이 동작의 영향을 받지 않습니다.  이 경우 관리되는 클래스\(공용 또는 전용\)가 모두 표시됩니다.  
  
## END \/clr 관련  
  
## 예제  
  
```  
// keyword_protected.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class X {  
public:  
   void setProtMemb( int i ) { m_protMemb = i; }  
   void Display() { cout << m_protMemb << endl; }  
protected:  
   int  m_protMemb;  
   void Protfunc() { cout << "\nAccess allowed\n"; }  
} x;  
  
class Y : public X {  
public:  
   void useProtfunc() { Protfunc(); }  
} y;  
  
int main() {  
   // x.m_protMemb;         error, m_protMemb is protected  
   x.setProtMemb( 0 );   // OK, uses public access function  
   x.Display();  
   y.setProtMemb( 5 );   // OK, uses public access function  
   y.Display();  
   // x.Protfunc();         error, Protfunc() is protected  
   y.useProtfunc();      // OK, uses public access function  
                        // in derived class  
}  
```  
  
## 참고 항목  
 [클래스 멤버에 대한 액세스 제어](../misc/controlling-access-to-class-members.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)