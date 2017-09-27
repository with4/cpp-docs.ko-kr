---
title: __super | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __super_cpp
- __super
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
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
ms.openlocfilehash: 64600f8cf642b0c7906873a73aa4da41897a57f5
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="super"></a>__super
**Microsoft 전용**  
  
 재정의하는 함수에 대한 기본 클래스 구현을 호출하고 있음을 명시적으로 나타낼 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>설명  
 액세스할 수 있는 모든 기본 클래스 메서드가 오버로드 확인 단계에서 고려되고 가장 일치하는 함수가 호출되는 함수입니다.  
  
 `__super`는 멤버 함수의 본문 내에서만 나타날 수 있습니다.  
  
 `__super`는 using 선언과 함께 사용할 수 없습니다. 참조 [선언을 사용 하 여](../cpp/using-declaration.md) 자세한 정보에 대 한 합니다.  
  
 도입으로 [특성](../windows/cpp-attributes-reference.md) 코드를 삽입 하 여 코드 이름 해당 모를 수에 포함 된 메서드를 호출 하려는 하나 이상의 기본 클래스가 포함 될 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)
