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
ms.openlocfilehash: 8bf975a9d64508368ac5d61c82fecc07edda28b5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943212"
---
# <a name="class-c"></a>클래스 (C++)
합니다 **클래스** 키워드는 클래스 형식 선언 또는 클래스 형식의 개체를 정의 합니다.  
  
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
 *템플릿 사양*  
 선택적 템플릿 지정입니다. 자세한 내용은 참조 [템플릿](templates-cpp.md)합니다.  
  
 *class*  
 합니다 **클래스** 키워드입니다.  
  
 *ms-선언-사양*  
 선택적 저장소 클래스 지정입니다. 자세한 내용은 참조는 [__declspec](../cpp/declspec.md) 키워드입니다.  
  
 *태그*  
 클래스에 지정 된 형식 이름입니다. 태그에는 클래스의 범위 내에서 예약어가 됩니다. 태그는 선택 사항입니다. 생략 하면 익명 클래스 정의 됩니다. 자세한 내용은 [익명 클래스 형식](../cpp/anonymous-class-types.md)합니다.  
  
 *기본-목록*  
 클래스 또는 구조체의 선택적 목록이이 클래스는 해당 멤버에서 파생 됩니다. 참조 [기본 클래스](../cpp/base-classes.md) 자세한 내용은 합니다. 각 기본 클래스 또는 구조체 이름 액세스 지정자 뒤에 올 수 있습니다 ([공용](../cpp/public-cpp.md)를 [개인](../cpp/private-cpp.md)하십시오 [보호](../cpp/protected-cpp.md)) 및 [가상](../cpp/virtual-cpp.md) 키워드입니다. 멤버 액세스 테이블을 참조 하세요 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) 자세한 내용은 합니다.  
  
 *멤버 목록*  
 클래스 멤버 목록입니다. 가리킵니다 [클래스 멤버 개요](../cpp/class-member-overview.md) 자세한 내용은 합니다.  
  
 *선언 자*  
 하나 이상의 클래스 유형 인스턴스 이름을 지정 하는 선언 자 목록입니다. 클래스의 모든 데이터 멤버를 선언 자 이니셜라이저 목록을 포함할 수 있습니다 **공용**합니다. 이 해당 데이터 멤버는 구조체에서 더 일반적 **공용** 보다는 기본적으로 클래스입니다. 참조 [개요의 선언 자](../cpp/overview-of-declarators.md) 자세한 내용은 합니다.  
  
## <a name="remarks"></a>설명  
 클래스에 대 한 자세한 내용은 다음 항목 중 하나를 참조 일반적으로.  
  
-   [struct](../cpp/struct-cpp.md)  
  
-   [union](../cpp/unions.md)  
  
-   [__multiple_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__single_inheritance](../cpp/inheritance-keywords.md)  
  
-   [__virtual_inheritance](../cpp/inheritance-keywords.md)  
  
 관리 되는 클래스와 구조체에 대 한 정보를 참조 하세요. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)  
  
## <a name="example"></a>예  
  
```cpp 
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