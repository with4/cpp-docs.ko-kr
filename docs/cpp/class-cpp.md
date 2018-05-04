---
title: 클래스 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- class_cpp
dev_langs:
- CPP
helpviewer_keywords:
- class types [C++], class statements
- class keyword [C++]
ms.assetid: dd23c09f-6598-4069-8bff-69c7f2518b9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bffa79760e9c597c5a6d736104dc856fc1de16b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="class-c"></a>클래스 (C++)
`class` 키워드 클래스 형식을 선언 또는 클래스 형식의 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [template-spec]  
       class [ms-decl-spec] [tag [: base-list ]]  
{  
   member-list  
} [declarators];  
[ class ] tag declarators;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `template-spec`  
 선택적 템플릿 지정입니다. 자세한 내용은를 참조 [템플릿](templates-cpp.md)합니다.  
  
 `class`  
 `class` 키워드입니다.  
  
 `ms-decl-spec`  
 선택적 저장소 클래스 지정입니다. 자세한 내용은 참조는 [__declspec](../cpp/declspec.md) 키워드입니다.  
  
 `tag`  
 클래스에 지정 된 형식 이름입니다. 태그에는 클래스의 범위 내에서 예약어가 됩니다. 태그는 선택 사항입니다. 생략 하는 경우 익명 클래스 정의 됩니다. 자세한 내용은 참조 [익명 클래스 형식](../cpp/anonymous-class-types.md)합니다.  
  
 `base-list`  
 클래스 또는 구조체의 선택적 목록이이 클래스는 해당 멤버를 파생 됩니다. 참조 [기본 클래스가 클래스](../cpp/base-classes.md) 자세한 정보에 대 한 합니다. 각 기본 클래스 또는 구조체 이름 앞에 나와야 액세스 지정자 ([공용](../cpp/public-cpp.md), [개인](../cpp/private-cpp.md), [보호](../cpp/protected-cpp.md)) 및 [가상](../cpp/virtual-cpp.md) 키워드입니다. 멤버 액세스 테이블을 참조 하십시오. [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) 자세한 정보에 대 한 합니다.  
  
 `member-list`  
 클래스 멤버의 목록입니다. 참조 [클래스 멤버 개요](../cpp/class-member-overview.md) 자세한 정보에 대 한 합니다.  
  
 `declarators`  
 하나 이상의 인스턴스 클래스 형식의 이름을 지정 하는 선언 자 목록입니다. 선언자는 클래스의 모든 데이터 멤버가 `public`인 경우 이니셜라이저 목록을 포함할 수 있습니다. 이 해당 데이터 멤버는 구조체에서 더 많이 `public` 보다 기본적으로 클래스입니다. 참조 [선언 자 개요](../cpp/overview-of-declarators.md) 자세한 정보에 대 한 합니다.  
  
## <a name="remarks"></a>설명  
 클래스에 대 한 자세한 내용은 다음 항목 중 하나를 참조 일반적으로.  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 관리 되는 클래스와 구조체에 대 한 정보를 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)