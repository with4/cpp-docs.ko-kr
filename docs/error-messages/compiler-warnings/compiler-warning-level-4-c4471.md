---
title: "컴파일러 경고 (수준 4) C4471 | Microsoft Docs"
ms.custom: 
ms.date: 04/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4471
dev_langs:
- C++
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
caps.latest.revision: 1
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d7d097b399d3681ef523d8787ecc38af472840f6
ms.openlocfilehash: fc0ddb07ec768804be61185211bbac0ee6fbf2b6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/28/2017

---
# <a name="compiler-warning-level-4-c4471"></a>컴파일러 경고 (수준 4) C4471
'*열거형*': 범위가 지정 되지 않은 열거형의 정방향 선언에 (int로 가정)는 내부 형식이 있어야 합니다.  
  
범위가 지정 되지 않은 열거형의 정방향 선언 내부 형식에 대해 지정 자가 없는 찾았습니다. 기본적으로 Visual c + + 가정 `int` 열거형의 내부 형식입니다. 다른 형식 정의에 사용 되는 열거형, 예를 들어 다른 명시적 형식을 지정 하는 경우 또는 다른 종류는 이니셜라이저에 의해 암시적으로 설정 되어 있으면이 인해 문제가 발생할 수 있습니다. 이식성 문제; 할 수도 있습니다. 다른 컴파일러 가정 하지 않습니다 `int` 열거형의 내부 형식이 있습니다.  
  
이 경고는 기본적으로 해제 되어 /Wall 또는 /w 사용할 수 있습니다*N*#pragma 사용 하거나 명령줄에서 설정 하려면 4471 [경고](../../preprocessor/warning.md) 원본 파일에 있습니다.  
  
일부 경우에이 경고는 잘못 된 합니다. 열거형에 대 한 정방향 선언 정의 다음 표시 되 면이 경고가 실행 될 수 있습니다. 예를 들어이 코드는 C4471 않을 경우에 유효 합니다.  
  
```cpp  
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```  
  
## <a name="example"></a>예제  
일반적으로 범위가 지정 되지 않은 열거형의 정방향 선언 하는 대신 전체 정의 사용 하는 안전 합니다. 헤더 파일에는 정의 넣을 수 있으며 참조 하는 소스 파일에 포함할 수 있습니다. 이 기능은 C + + 98 이상용으로 작성 된 코드에서 작동 합니다. 이 솔루션을 portability 및 유지 관리의 편의성을 사용 하는 것이 좋습니다.  
  
```cpp  
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```  
  
## <a name="example"></a>예제  
C + + 11에서는 범위가 지정 되지 않은 열거 하 고 정방향 선언 명시적 형식을 추가할 수 있습니다. 복잡 한 헤더 포함 논리 정방향 선언 대신 정의 사용을 금지 하는 경우에이 솔루션을 좋습니다. 이 솔루션을 유지 관리 문제를 발생 시킬 수 있습니다: 열거형 정의에 사용 되는 기본 형식을 변경 하면 모든 정방향 선언에 맞게 변경 해야 하거나 코드에서 자동 오류를 할 수 있습니다. 이 문제를 최소화 하기 위해 헤더 파일로 정방향 선언에 넣을 수 있습니다.  
  
```cpp  
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```  
  
```cpp  
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```  
  
열거형에 대 한 명시적 형식을 지정 하면 경고도 사용 하는 것이 좋습니다 [C4369](compiler-warning-level-1-C4369.md), 기본적으로 켜져 있는 합니다. 에 열거형 항목 명시적으로 지정 된 종류와 다른 type을 필요한 경우를 식별 합니다.
  
## <a name="example"></a>예제  
범위가 지정 된 열거형, C + + 11의 새로운 기능을 사용 하 여 코드를 변경할 수 있습니다. 범위가 지정 된 열거형을 사용 하도록 정의와 열거형 형식을 사용 하는 클라이언트 코드를 변경 해야 합니다. 사용 하면 범위가 지정 된 열거형 네임 스페이스 충돌 문제가 있는 경우 정의 된 열거형 항목 이름에는 열거형의 범위로 제한 하는 것이 좋습니다. 범위가 지정 된 열거형의 또 다른 기능은 해당 멤버를 다른 정수 계열 또는 열거형 형식으로 감지 하기 어려운 버그의 원인이 될 수 있는 암시적으로 변환 될 수 없습니다.

```cpp  
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```  
  
```cpp  
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```  
  

