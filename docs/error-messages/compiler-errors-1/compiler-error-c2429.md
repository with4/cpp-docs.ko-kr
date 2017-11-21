---
title: "컴파일러 오류 C2429 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2429
dev_langs: C++
helpviewer_keywords: C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f263673e6b325557694b26b1fd71e86c22029d05
ms.sourcegitcommit: 78f3f8208d49b7c1d87f4240f4a1496b7c29333e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="compiler-error-c2429"></a>컴파일러 오류 C2429

> '*언어 기능*'컴파일러 플래그 필요'*컴파일러 옵션*'

언어 기능 지원에 대 한 특정 컴파일러 옵션을 사용 해야 합니다.

오류 **C2429: 언어 기능 ' 중첩 된 네임 스페이스-정의 ' 필요 컴파일러 플래그 ' / std:c + + 17'** 정의 하려는 경우에 생성 되는 *복합 네임 스페이스*를 하나 이상 포함 하는 네임 스페이스 Visual Studio 2015 업데이트 5에 시작 되는 범위를 중첩 된 네임 스페이스 이름입니다. (Visual Studio 2017 15.3, 버전에에서는 **/std:c + + 최신** 스위치는 필요 합니다.) 복합 네임 스페이스 정의 C + + 17 하기 전에 c + +에서 사용할 수 없습니다. 컴파일러 복합 네임 스페이스 정의 지원 때는 [/std:c + + 17](../../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 지정 합니다.

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```
