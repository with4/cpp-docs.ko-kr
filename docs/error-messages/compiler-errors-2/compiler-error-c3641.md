---
title: 컴파일러 오류 C3641 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3641
dev_langs:
- C++
helpviewer_keywords:
- C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99aef6bcfd8ac7ea89cb62fda37c7aec012e16de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704947"
---
# <a name="compiler-error-c3641"></a>컴파일러 오류 C3641

> '*함수*': 잘못 된 호출 규칙 'calling_convention' /clr을 사용 하 여 컴파일된 함수에 대 한: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

만 [__clrcall](../../cpp/clrcall.md) 호출 규칙은 사용할 수 [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예

다음 샘플에서는 C3641 오류가 생성 됩니다.

```cpp
// C3641.cpp
// compile with: /clr:pure /c
void __cdecl f() {}   // C3641
```