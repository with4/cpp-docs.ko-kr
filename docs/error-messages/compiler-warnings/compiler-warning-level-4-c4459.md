---
title: "컴파일러 경고 (수준 4) C4459 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47380915dd18387fa3cc2af54d42a3777aab3f5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4459"></a>컴파일러 경고 (수준 4) C4459
  
> 선언 '*식별자*' 전역 선언을 숨깁니다.
  
선언 *식별자* 로컬 범위에서 같은 이름의 선언을 숨깁니다 *식별자* 전역 범위에 있습니다. 이 경고를 사용 하면에 대 한 참조를 알 *식별자* 이 범위에 로컬로 선언 된 버전을 원래의 도와 아닐 수 있는 글로벌 버전이 아닌으로 확인 합니다. 일반적으로 좋은 엔지니어링 방법으로 전역 변수의 사용을 최소화 하는 것이 좋습니다. 전역 네임 스페이스의 충돌을 최소화 하려면 전역 변수에 대 한 명명된 된 네임 스페이스의 사용을 좋습니다.  
  
이 경고는 Visual c + + 컴파일러 버전 18.00 Visual Studio 2015의 새로운 했습니다. 컴파일러 또는 코드를 마이그레이션하는 동안 나중에 해당 버전에서 발생 한 경고를 표시 하지 않으려면 사용는 [/wv: 18](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다. 

## <a name="example"></a>예
  
 다음 샘플에서는 C4459 오류가 생성 됩니다.  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
이 문제를 해결 하는 한 가지 방법은 전역에 대 한 네임 스페이스를 만들고 있지만 사용 하지는 `using` 정규화 된 이름을 지시문을 가져와서 해당 네임 스페이스 범위에 대 한 모든 참조는 모호 하지 않은 사용 해야 합니다.  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  
