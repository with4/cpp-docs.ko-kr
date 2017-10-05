---
title: "클래스 및 구조체 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: db6fd2ff70e805e6681adb9eeca6adac41a38f0b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="classes-and-structs-c"></a>클래스 및 구조체(C++)
이 섹션에서는 C++ 클래스 및 구조체를 소개합니다. 구조체에서는 기본 접근성이 공용이고, 클래스에서는 기본값이 개인이라는 점을 제외하면 C++에서 두 구문이 동일합니다.  
  
 클래스와 구조체는 고유한 형식을 정의하는 데 사용되는 구문입니다. 클래스와 구조체 모두형식의 상태 및 동작을 설명하는 데 사용되는 데이터 멤버와 멤버 함수를 포함합니다.  
  
 주제는 다음과 같습니다.  
  
-   [class](../cpp/class-cpp.md)  
  
-   [truct](../cpp/struct-cpp.md)  
  
-   [클래스 멤버 개요](../cpp/class-member-overview.md)  
  
-   [멤버 액세스 제어](../cpp/member-access-control-cpp.md)  
  
-   [상속](../cpp/inheritance-cpp.md)  
  
-   [정적 멤버](../cpp/static-members-cpp.md)  
  
-   [사용자 정의 형식 변환](../cpp/user-defined-type-conversions-cpp.md)  
  
-   [변경할 수 있는 데이터 멤버 (변경할 수 있는 지정자)](../cpp/mutable-data-members-cpp.md)  
  
-   [중첩 클래스 선언](../cpp/nested-class-declarations.md)  
  
-   [익명 클래스 형식](../cpp/anonymous-class-types.md)  
  
-   [멤버에 대한 포인터](../cpp/pointers-to-members.md)  
  
-   [this 포인터](../cpp/this-pointer.md)  
  
-   [C++ 비트 필드](../cpp/cpp-bit-fields.md)  
  
 세 가지 클래스 형식은 구조체, 클래스 및 공용 구조체입니다. 사용 하 여 선언 된는 [구조체](../cpp/struct-cpp.md), [클래스](../cpp/class-cpp.md), 및 [union](../cpp/unions.md) 키워드 (참조 [클래스 형식 정의](http://msdn.microsoft.com/en-us/e8c65425-0f3a-4dca-afc2-418c3b1e57da)). 다음 표에서는 세 가지 클래스 형식 간의 차이점을 보여 줍니다.  
  
 공용 구조체에 대 한 자세한 내용은 참조 하십시오. [공용 구조체](../cpp/unions.md)합니다. 관리 되는 클래스와 구조체에 대 한 정보를 참조 하십시오. [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>구조체, 클래스 및 공용 구조체의 Access Control 및 제약 조건  
  
|구조체|클래스|공용 구조체|  
|----------------|-------------|------------|  
|클래스 키가 `struct`임|클래스 키가 **클래스**|클래스 키가 **공용 구조체**|  
|기본 액세스가 공용임|기본 액세스가 개인임|기본 액세스가 공용임|  
|사용 제약 조건 없음|사용 제약 조건 없음|한 번에 한 멤버만 사용|  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)
