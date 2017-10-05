---
title: "상속 (c + +) | Microsoft Docs"
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
- derived classes
- derived classes, about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
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
ms.openlocfilehash: dba45acbc602465db876038e83cb0cd496b2337e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="inheritance--c"></a>상속(C++)
이 단원에서는 파생 클래스를 사용하여 확장 가능한 프로그램을 생성하는 방법을 설명합니다.  
  
## <a name="overview"></a>개요  
 "상속" 메커니즘을 사용 하 여 기존 클래스에서 새 클래스를 파생 될 수 있습니다 (시작 하는 정보를 참조 하십시오. [단일 상속](../cpp/single-inheritance.md)). 파생에 사용되는 클래스를 특정 파생 클래스의 "기본 클래스"라고 합니다. 파생 클래스는 다음 구문을 사용하여 선언됩니다.  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 클래스에 대한 태그(이름) 뒤에 콜론과 기본 사양 목록이 나타납니다.  그렇게 명명된 기본 클래스는 이전에 선언되어 있어야 합니다.  기본 사양은 키워드 중 하나인 액세스 지정자를 포함할 수 있습니다 **공용**, `protected` 또는 `private`합니다.  이러한 액세스 지정자는 기본 클래스 이름 앞에 나타나고 해당 기본 클래스에만 적용됩니다.  이러한 지정자는 기본 클래스의 멤버를 사용할 수 있는 파생 클래스의 권한을 제어합니다.  참조 [멤버 액세스 제어](../cpp/member-access-control-cpp.md) 기본 클래스 멤버에 대 한 액세스에 대 한 내용은 합니다.  액세스 지정자를 생략할 경우 해당 기본 클래스 멤버에 대한 액세스가 `private`으로 간주됩니다.  기본 사양은 키워드를 포함할 수 있습니다 **가상** 가상 상속을 나타냅니다.  이 키워드는 액세스 지정자(있는 경우) 앞이나 뒤에 나타날 수 있습니다.  가상 상속을 사용하는 경우 기본 클래스를 가상 기본 클래스라고 합니다.  
  
 여러 기본 클래스를 쉼표로 구분하여 지정할 수 있습니다.  상속 모델은 하나의 기본 클래스를 지정 하는 경우 [단일 상속](../cpp/single-inheritance.md)합니다. 둘 이상의 기본 클래스를 지정 하는 경우 상속 모델 이라고 [다중 상속](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 주제는 다음과 같습니다.  
  
-   [단일 상속](../cpp/single-inheritance.md)  
  
-   [다중 상속](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [다중 기본 클래스](../cpp/multiple-base-classes.md)  
  
-   [가상 함수](../cpp/virtual-functions.md)  
  
-   [명시적 재정](../cpp/explicit-overrides-cpp.md)  
  
-   [추상 클래스](../cpp/abstract-classes-cpp.md)  
  
-   [범위 규칙 요약](../cpp/summary-of-scope-rules.md)  
  
 [__super](../cpp/super.md) 및 [__interface](../cpp/interface.md) 키워드는이 섹션에 설명 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)
