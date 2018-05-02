---
title: 인라인 어셈블리에서 c + + 함수 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], calling in inline assembly
- function calls, C++ functions
- function calls, in inline assembly
- Visual C++, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffbd8038d240bc2ab0240d172d914790b6ca02ab
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="calling-c-functions-in-inline-assembly"></a>인라인 어셈블리에서 C++ 함수 호출
## <a name="microsoft-specific"></a>Microsoft 전용  
 `__asm` 블록은 오버로드되지 않은 전역 C++ 함수만 호출할 수 있습니다. 오버로드된 전역 C++ 함수 또는 C++ 멤버 함수를 호출하면 컴파일러에서 오류가 발생합니다.  
  
 선언 된 함수를 호출할 수도 있습니다 **extern "C"** 링크 합니다. 이 통해는 `__asm` 모든 표준 헤더 파일을 라이브러리 함수를 선언 하기 때문에 C 라이브러리 함수를 호출 하는 c + + 프로그램 내에서 블록 **extern "C"** 링크 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [인라인 어셈블러](../../assembler/inline/inline-assembler.md)