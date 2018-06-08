---
title: 컴파일러 오류 C3389 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b540f87458c75ddf7d57626b6251248652b96213
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704307"
---
# <a name="compiler-error-c3389"></a>컴파일러 오류 C3389

> __declspec (*키워드*) /clr 함께 사용할 수 없습니다: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

A [__declspec](../../cpp/declspec.md) 사용 되는 한정자 의미는 당 프로세스 상태입니다.  [/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md) 의미는 당 [appdomain](../../cpp/appdomain.md) 상태입니다.  따라서 사용 하 여 변수를 선언에서 `keyword` **__declspec** 한정자와 사용 하 여 컴파일할 **/clr: 순수** 허용 되지 않습니다.

## <a name="example"></a>예

다음 샘플에서는 C3389 오류가 생성 됩니다.

```cpp
// C3389.cpp
// compile with: /clr:pure /c
__declspec(dllexport) int g2 = 0;   // C3389
```