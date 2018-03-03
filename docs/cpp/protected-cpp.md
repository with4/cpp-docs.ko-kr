---
title: protected (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- protected_cpp
dev_langs:
- C++
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02366a53f02142f66aa5dca493c5460c9f2d1d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="protected-c"></a>protected (C++)
## <a name="syntax"></a>구문  
  
```  
protected:  
   [member-list]  
protected base-class  
```  
  
## <a name="remarks"></a>설명  
 `protected` 키워드의 클래스 멤버에 대 한 액세스를 지정는 *멤버 목록* 까지 다음 액세스 지정자 (**공용** 또는 `private`) 또는 클래스 정의의 끝입니다. `protected`로 선언된 클래스 멤버는 다음에만 사용할 수 있습니다.  
  
-   원래 이 멤버를 선언한 클래스의 멤버 함수  
  
-   원래 이 멤버를 선언한 클래스의 friend  
  
-   원래 이 멤버를 선언한 클래스에서 공용 또는 보호된 액세스로 파생 클래스  
  
-   보호된 멤버에 대해 전용 액세스 권한이 있으며 전용으로 직접 파생 클래스  
  
 기본 클래스 이름 앞에 오는 `protected` 키워드는 기본 클래스의 공용 및 보호된 멤버가 파생된 해당 클래스의 보호된 멤버라고 지정합니다.  
  
 보호 된 멤버 만큼 전용 없는 `private` 멤버는 선언 하지만 만큼 공용도 아닌 클래스의 멤버에만 액세스할 수 있는 **공용** 모든 함수에 액세스할 수 있는 멤버입니다.  
  
 보호 된 구성원으로도 선언 된 **정적** 파생된 클래스의 모든 친구 또는 멤버 함수에 액세스할 수 있어야 합니다. 보호 된 구성원으로 선언 되지 않은 **정적** 친구와 파생된 클래스의 개체 또는 포인터, 참조, 통해서만 파생된 클래스에서 멤버 함수에 액세스할 수 있어야 합니다.  
  
 관련된 정보를 참조 하십시오. [friend](../cpp/friend-cpp.md), [공용](../cpp/public-cpp.md), [개인](../cpp/private-cpp.md), 멤버 액세스 테이블 및 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>/clr 관련  
 CLR 형식에서 c + + 액세스 지정자 키워드 (**공용**, `private`, 및 `protected`) 형식 및 어셈블리와 관련 된 메서드 표시 여부에 영향을 줄 수 있습니다. 자세한 내용은 참조 [멤버 액세스 제어](member-access-control-cpp.md)합니다.  
  
> [!NOTE]
>  으로 컴파일된 파일 [/LN](../build/reference/ln-create-msil-module.md) 이 동작에 의해 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.  
  
## <a name="end-clr-specific"></a>END /clr 관련  
  
## <a name="example"></a>예  
  
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
  
## <a name="see-also"></a>참고 항목  
 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)