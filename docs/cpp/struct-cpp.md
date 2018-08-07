---
title: 구조체 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- struct_cpp
dev_langs:
- C++
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23f5d7d21a19b589bbf71221cf4e5cfbdec7f6f6
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463030"
---
# <a name="struct-c"></a>struct (C++)
합니다 **구조체** 키워드 구조체 형식 및/또는 구조체 형식의 변수를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[template-spec] struct[ms-decl-spec] [tag [: base-list ]]  
{   
   member-list   
} [declarators];  
[struct] tag declarators;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *템플릿 사양*  
 선택적 템플릿 지정입니다. 자세한 내용은 참조 [템플릿 지정](templates-cpp.md)합니다.  
  
 *struct*  
 합니다 **구조체** 키워드입니다.  
  
 *ms-선언-사양*  
 선택적 저장소 클래스 지정입니다. 자세한 내용은 참조는 [__declspec](../cpp/declspec.md) 키워드입니다.  
  
 *태그*  
 구조체에 지정된 형식 이름입니다. 태그는 구조체의 범위 내에서 예약어가 됩니다. 태그는 선택 사항입니다. 생략할 경우 익명 구조체가 정의됩니다. 자세한 내용은 [익명 클래스 형식](../cpp/anonymous-class-types.md)합니다.  
  
 *기본-목록*  
 이 구조체가 해당 멤버를 파생할 클래스 또는 구조체의 선택적 목록입니다. 참조 [기본 클래스](../cpp/base-classes.md) 자세한 내용은 합니다. 각 기본 클래스 또는 구조체 이름 액세스 지정자 뒤에 올 수 있습니다 ([공용](../cpp/public-cpp.md)를 [개인](../cpp/private-cpp.md)하십시오 [보호](../cpp/protected-cpp.md)) 및 [가상](../cpp/virtual-cpp.md) 키워드입니다. 멤버 액세스 테이블을 참조 하세요 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) 자세한 내용은 합니다.  
  
 *멤버 목록*  
 구조체 멤버 목록입니다. 가리킵니다 [클래스 멤버 개요](../cpp/class-member-overview.md) 자세한 내용은 합니다. 여기에서 유일한 차이점 **구조체** 대신 사용 됩니다 **클래스**합니다.  
  
 *선언 자*  
 클래스의 이름을 지정하는 선언자 목록입니다. 선언자 목록은 구조체 형식의 하나 이상의 인스턴스를 선언합니다. 클래스의 모든 데이터 멤버를 선언 자 이니셜라이저 목록을 포함할 수 있습니다 **공용**합니다. 데이터 멤버는 이니셜라이저 목록은 구조에서 흔히 **공용** 기본적으로 합니다.  참조 [개요의 선언 자](../cpp/overview-of-declarators.md) 자세한 내용은 합니다.  
  
## <a name="remarks"></a>설명  
 구조체 형식은 사용자 정의 복합 형식입니다. 이 형식은 다른 형식을 가질 수 있는 필드 또는 멤버로 구성됩니다.  
  
 C + +에서 구조체는 클래스와 같은 해당 멤버는 한다는 **공용** 기본적으로 합니다.  
  
 관리 되는 클래스 및 구조체에 대 한 내용은 참조 하세요 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)합니다.  
  
## <a name="using-a-structure"></a>구조체 사용  
 C에서 명시적으로 사용 해야 합니다 **구조체** 구조체를 선언 하는 키워드입니다. C + +에서는 필요가 없습니다 사용 하는 **구조체** 형식을 정의한 후에 키워드입니다.  
  
 닫는 중괄호와 세미콜론 사이에 쉼표로 구분된 변수 이름을 하나 이상 넣어 구조체 형식이 정의될 때 변수를 선언하는 옵션이 있습니다.  
  
 구조체 변수를 초기화할 수 있습니다. 각 변수의 초기화는 중괄호로 묶어야 합니다.  
  
 관련 정보를 참조 하세요 [클래스](../cpp/class-cpp.md), [union](../cpp/unions.md), 및 [enum](../cpp/enumerations-cpp.md)합니다.  
  
## <a name="example"></a>예  
  
```cpp 
#include <iostream>  
using namespace std;  
  
struct PERSON {   // Declare PERSON struct type  
    int age;   // Declare member types  
    long ss;  
    float weight;  
    char name[25];  
} family_member;   // Define object of type PERSON  
  
struct CELL {   // Declare CELL bit field  
    unsigned short character  : 8;  // 00000000 ????????  
    unsigned short foreground : 3;  // 00000??? 00000000  
    unsigned short intensity  : 1;  // 0000?000 00000000  
    unsigned short background : 3;  // 0???0000 00000000  
    unsigned short blink      : 1;  // ?0000000 00000000  
} screen[25][80];       // Array of bit fields   
  
int main() {  
    struct PERSON sister;   // C style structure declaration  
    PERSON brother;   // C++ style structure declaration  
    sister.age = 13;   // assign values to members  
    brother.age = 7;  
    cout << "sister.age = " << sister.age << '\n';  
    cout << "brother.age = " << brother.age << '\n';  
  
    CELL my_cell;  
    my_cell.character = 1;  
    cout << "my_cell.character = " << my_cell.character;  
}  
// Output:  
// sister.age = 13  
// brother.age = 7  
// my_cell.character = 1  
```  