---
title: public (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- public
dev_langs:
- C++
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
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
ms.openlocfilehash: 7ce4262b3f32f48b61e6f4e273ce74c8334f8f0c
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="public-c"></a>public (C++)
## <a name="syntax"></a>구문  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## <a name="remarks"></a>설명  
 목록 앞에 오는 클래스 멤버는 **공용** 키워드 해당 멤버는 함수에서 액세스할 수 있도록 지정 합니다. 이 설정은 다음 액세스 지정자 또는 클래스 끝까지 선언된 모든 멤버에 적용됩니다.  
  
 이름 앞에 오는 기본 클래스의는 **공용** 키워드는 기본 클래스의 공용 및 보호 된 멤버는 공용 지정 각각 파생된 클래스의 멤버를 보호 합니다.  
  
 클래스에서 멤버의 기본 액세스는 전용입니다. 구조체나 공용 구조체에서 멤버의 기본 액세스는 공용입니다.  
  
 기본 클래스의 기본 액세스는 클래스에 대해 전용이고 구조체에 대해 공용입니다. 공용 구조체에 기본 클래스를 사용할 수 없습니다.  
  
 자세한 내용은 참조 [개인](../cpp/private-cpp.md), [보호](../cpp/protected-cpp.md), [friend](../cpp/friend-cpp.md), 멤버 액세스 테이블 및 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>/clr 관련  
 CLR 형식에서 c + + 액세스 지정자 키워드 (**공용**, `private`, 및 `protected`) 형식 및 어셈블리와 관련 된 메서드 표시 여부에 영향을 줄 수 있습니다. 자세한 내용은 참조 [멤버 액세스 제어](member-access-control-cpp.md)합니다.  
  
> [!NOTE]
>  으로 컴파일된 파일 [/LN](../build/reference/ln-create-msil-module.md) 이 동작에 의해 영향을 받지 않습니다. 이 경우 관리되는 클래스(공용 또는 전용)가 모두 표시됩니다.  
  
## <a name="end-clr-specific"></a>END /clr 관련  
  
## <a name="example"></a>예제  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 멤버에 대 한 액세스 제어](member-access-control-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)
