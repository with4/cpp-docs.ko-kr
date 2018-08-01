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
ms.openlocfilehash: 058979420e5bb1426879522e70ec8b1ac768d9cc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407405"
---
# <a name="bool-c"></a>bool (C++)

이 키워드는 기본 제공 형식입니다. 이 형식의 변수에 값을 가질 수 있습니다 [true](../cpp/true-cpp.md) 하 고 [false](../cpp/false-cpp.md)합니다. 형식이 조건식 **bool** 형식의 값을 해야 하므로 **bool**합니다. 예를 들어 `i!=0` 이제 값에 따라 TRUE 또는 FALSE가 `i`입니다.  

**Visual Studio 2017 버전 15.3 이상** (사용할 수 있습니다 [/std: c + + 17](../build/reference/std-specify-language-standard-version.md)): 피연산자 접두사 또는 후 위 증가 또는 감소 연산자는 형식의 되지 않을 수 있습니다 **bool**합니다. 즉, 변수에 지정 된 `b` 형식의 **bool**, 이러한 식이 허용 되는 더 이상:

```cpp
    b++;
    ++b;
    b--;
    --b;
```
  
값 TRUE 및 FALSE 다음 관계를 포함 합니다.  
  
```cpp  
!false == true  
!true == false  
```  
  
다음 문에서  
  
```cpp  
if (condexpr1) statement1;   
```  
  
하는 경우 `condexpr1` 가 TRUE 인 `statement1` 이 항상 실행 하는 경우 `condexpr1` 은 FALSE `statement1` 실행 되지 않습니다.  
  
후 위 또는 접두사 **++** 형식의 변수에 연산자를 적용할 **bool**, 변수는 TRUE로 설정 됩니다. 
**Visual Studio 2017 버전 15.3 이상**: operator + + **bool** 언어에서 제거 되었습니다 및는 지원 되지 않습니다.

후 위 또는 접두사 **--** 연산자는이 형식의 변수에 적용할 수 없습니다.  
  
 합니다 **bool** 형식은 정수 계열 확장에 참여 합니다. 형식의 r-value **bool** 형식의 r-value로 변환할 수 있습니다 **int**FALSE 되는 것으로, 0 및 1 TRUE입니다. 고유 형식으로 **bool** 오버 로드 확인에 참여 합니다.  
  
## <a name="see-also"></a>참고자료
[키워드](../cpp/keywords-cpp.md)  
[기본 형식](../cpp/fundamental-types-cpp.md)  