---
title: "final 지정자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: final_CPP
dev_langs: C++
helpviewer_keywords: final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3f7c5afd4010983ea943193b7abfb99f22eda38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="final-specifier"></a>final 지정자
`final` 키워드를 사용하여 파생 클래스에서 재정의할 수 없는 가상 함수를 지정할 수 있습니다. 상속할 수 없는 클래스를 지정하기 위해 해당 키워드를 사용할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>설명  
 `final`은 상황에 따라 다르며 함수 선언 또는 클래스 이름 뒤에 사용할 때만 특별한 의미를 갖습니다. 그렇지 않으면 예약된 키워드가 아닙니다.  
  
 `final`이 클래스 선언에 사용되는 경우 `base-classes`는 선언의 선택적 부분입니다.  
  
## <a name="example"></a>예  
 다음 예제는 `final` 키워드를 사용하여 가상 함수를 재정의할 수 없음을 지정합니다.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 멤버 함수를 재정의할 수 있음을 지정 하는 방법에 대 한 정보를 참조 하십시오. [재정의 지정자는](../cpp/override-specifier.md)합니다.  
  
 다음 예제는 `final` 키워드를 사용하여 클래스를 상속할 수 없음을 지정합니다.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [override 지정자](../cpp/override-specifier.md)