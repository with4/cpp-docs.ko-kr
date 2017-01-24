---
title: "클래스 (C++) | Microsoft Docs"
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
  - "class_cpp"
  - "class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "class 키워드[C++]"
  - "클래스 형식, class 문"
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클래스 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`class` 키워드는 클래스 형식을 선언하거나 클래스 형식의 개체를 정의합니다.  
  
## 구문  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### 매개 변수  
 `template-spec`  
 선택적 템플릿 지정입니다.  자세한 내용은 [템플릿 지정](../Topic/Template%20Specifications.md)을 참조하십시오.  
  
 `class`  
 `class` 키워드입니다.  
  
 `ms-decl-spec`  
 선택적 저장소 클래스 지정입니다.  자세한 내용은 [\_\_declspec](../cpp/declspec.md) 키워드를 참조하십시오.  
  
 `tag`  
 클래스에 지정된 형식 이름입니다.  태그는 클래스의 범위 내에서 예약어가 됩니다.  태그는 선택 사항입니다.  생략할 경우 익명 클래스가 정의됩니다.  자세한 내용은 [익명 클래스 형식](../cpp/anonymous-class-types.md)을 참조하십시오.  
  
 `base-list`  
 클래스 또는 구조체의 선택적 목록 이 클래스가 해당 멤버를 파생합니다.  자세한 내용은 [기본 클래스](../cpp/base-classes.md)를 참조하십시오.  각 기본 클래스 또는 구조체 이름 앞에는 액세스 지정자\([public](../cpp/public-cpp.md), [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md)\) 및 [virtual](../cpp/virtual-cpp.md) 키워드가 올 수 있습니다.  자세한 내용은 [클래스 멤버에 대한 액세스 제어](../misc/controlling-access-to-class-members.md)의 멤버 액세스 테이블을 참조하십시오.  
  
 `member-list`  
 클래스 멤버 목록  자세한 내용은 [클래스 멤버 개요](../cpp/class-member-overview.md)를 참조하십시오.  
  
 `declarators`  
 클래스 형식의 하나 이상의 인스턴스의 이름을 지정하는 선언자 목록입니다.  선언자는 클래스의 모든 데이터 멤버가 `public`인 경우 이니셜라이저 목록을 포함할 수 있습니다.  이것은 클래스에서 보다 데이터 멤버가 기본적으로 `public`인 구조체에서 더 일반적입니다.  자세한 내용은 [선언자 개요](../cpp/overview-of-declarators.md)를 참조하십시오.  
  
## 설명  
 일반적으로 클래스에 대한 자세한 내용은 다음 항목 중 하나를 참조 하십시오.  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [\_\_multiple\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_single\_inheritance](../cpp/inheritance-keywords.md)  
  
-   [\_\_virtual\_inheritance](../cpp/inheritance-keywords.md)  
  
 관리되는 클래스 및 구조체에 대한 자세한 내용은 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
  
```  
// class.cpp  
// compile with: /EHsc  
// Example of the class keyword  
// Exhibits polymorphism/virtual functions.  
  
#include <iostream>  
#include <string>  
#define TRUE = 1  
using namespace std;  
  
class dog  
{  
public:  
   dog()  
   {  
      _legs = 4;  
      _bark = true;  
   }  
  
   void setDogSize(string dogSize)  
   {  
      _dogSize = dogSize;  
   }  
   virtual void setEars(string type)      // virtual function  
   {  
      _earType = type;  
   }  
  
private:  
   string _dogSize, _earType;  
   int _legs;  
   bool _bark;  
  
};  
  
class breed : public dog  
{  
public:  
   breed( string color, string size)  
   {  
      _color = color;  
      setDogSize(size);  
   }  
  
   string getColor()  
   {  
      return _color;  
   }  
  
   // virtual function redefined  
   void setEars(string length, string type)  
   {  
      _earLength = length;  
      _earType = type;  
   }  
  
protected:  
   string _color, _earLength, _earType;  
};  
  
int main()  
{  
   dog mongrel;  
   breed labrador("yellow", "large");  
   mongrel.setEars("pointy");  
   labrador.setEars("long", "floppy");  
   cout << "Cody is a " << labrador.getColor() << " labrador" << endl;  
}  
```  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)