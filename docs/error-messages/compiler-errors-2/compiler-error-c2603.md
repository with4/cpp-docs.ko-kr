---
title: "컴파일러 오류 C2603 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2603
dev_langs: C++
helpviewer_keywords: C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c06c5747a3d785242e8b926fe6e1eaa251a2d8b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2603"></a>컴파일러 오류 C2603  
  
> '*함수*': 함수에서 생성자/소멸자가 있는 너무 많은 블록 범위 정적 개체가  
  
버전의 Visual Studio 2015 하기 전에 Visual c + + 컴파일러의 경우 또는 [/Zc:threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) 컴파일러 옵션이 지정 되어, 31 외부에서 볼 수 있는 인라인 함수에 포함할 수 정적 개체의 수에 제한이 있습니다 .  
  
이 문제를 해결 하려면 최신 버전의 Visual c + + 컴파일러 도구 집합을 적용 하거나 가능 하면 /Zc:threadSafeInit-컴파일러 옵션을 제거는 것이 좋습니다. 없는 경우에 정적 개체를 결합 하는 것이 좋습니다. 개체가 동일한 형식의 않으면는 해당 유형의 단일 정적 배열 사용 하 여을 필요에 따라 개별 멤버를 참조 합니다.
  
## <a name="example"></a>예  
  
다음 코드에서는 C2603 경고가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C2603.cpp  
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };  
extern inline void f1() {  
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;  
    static C C32;   // C2603 Comment this line out to avoid error  
}  
```
