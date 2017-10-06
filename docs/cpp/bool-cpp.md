---
title: bool (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
dev_langs:
- C++
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
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
ms.openlocfilehash: f2437d831ae155f916b69cc6b35d3b586be9819e
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="bool-c"></a>bool (C++)
이 키워드는 기본 제공 형식입니다. 이 유형의 변수 값을 가질 수 [true](../cpp/true-cpp.md) 및 [false](../cpp/false-cpp.md)합니다. 조건식은 `bool` 형식이며 `bool` 형식의 값을 갖습니다. 예를 들어 `i!=0` 이제 **true** 또는 **false** 값에 따라 `i`합니다.  

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 피연산자 후 위 또는 접두사 증가 또는 감소 연산자 아닐 형식의 `bool`합니다. 
  
 값 **true** 및 **false** 다음 관계를 포함 합니다.  
  
```  
!false == true  
!true == false  
```  
  
 다음 문에서  
  
```  
if (condexpr1) statement1;   
```  
  
 경우 `condexpr1` 은 **true**, `statement1` 은 항상 실행 되 고 `condexpr1` 은 **false**, `statement1` 실행 되지 않습니다.  
  
 후 위 또는 접두사 `++` 형식의 변수에 연산자가 적용 `bool`, 변수 설정은 **true**합니다. 
**Visual Studio 2017 버전 15.3 이상**: operator + + bool에 대 한 언어에서 제거 되었으며 더 이상 지원 합니다.

후위 또는 접두사 `--` 연산자를 이 형식의 변수에 적용할 수 없습니다.  
  
 `bool` 형식은 정수 계열 확장에 참여합니다. 형식의 r-value `bool` 형식의 r-value로 변환할 수 `int`와 **false** 0이 되 고 및 **true** 고 하나 있습니다. `bool`이 고유한 형식으로 오버로드 확인에 참여합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [기본 형식](../cpp/fundamental-types-cpp.md)
