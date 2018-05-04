---
title: bool (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2af648b2b93d2d01eaf66f5b642b6514063577d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="bool-c"></a>bool (C++)

이 키워드는 기본 제공 형식입니다. 이 유형의 변수 값을 가질 수 [true](../cpp/true-cpp.md) 및 [false](../cpp/false-cpp.md)합니다. 조건식은 `bool` 형식이며 `bool` 형식의 값을 갖습니다. 예를 들어 `i!=0` 이제 **true** 또는 **false** 값에 따라 `i`합니다.  

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 피연산자 후 위 또는 접두사 증가 또는 감소 연산자 아닐 형식의 **bool**합니다. 즉, 변수가 **b** 형식의 **bool**, 이러한 식이 허용 되는 더 이상:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
값 **true** 및 **false** 다음 관계를 포함 합니다.  
  
```cpp  
!false == true  
!true == false  
```  
  
다음 문에서  
  
```cpp  
if (condexpr1) statement1;   
```  
  
경우 `condexpr1` 은 **true**, `statement1` 은 항상 실행 되 고 `condexpr1` 은 **false**, `statement1` 실행 되지 않습니다.  
  
후 위 또는 접두사 **++** 형식의 변수에 연산자가 적용 **bool**, 변수 설정은 **true**합니다. 
**Visual Studio 2017 버전 15.3 이상**: operator + +에 대 한 **bool** 언어 제거 되었으며 더 이상 지원 합니다.

후 위 또는 접두사 **--** 연산자는이 형식의 변수에 적용할 수 없습니다.  
  
 **bool** 형식은 정수 계열 확장에 참여 합니다. 형식의 r-value **bool** 형식의 r-value로 변환할 수 **int**와 **false** 0이 되 고 및 **true** 고 하나 있습니다. 고유한 형식으로 **bool** 오버 로드 확인에 참여 합니다.  
  
## <a name="see-also"></a>참고자료

[키워드](../cpp/keywords-cpp.md)<br/>
[기본 형식](../cpp/fundamental-types-cpp.md)<br/>
