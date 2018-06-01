---
title: 컴파일러 오류 C2812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5469e4f7be3c164cc63fa30f5069009846be48
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705025"
---
# <a name="compiler-error-c2812"></a>컴파일러 오류 C2812

> \#/clr을 사용한 가져오기가 지원 되지 않습니다: pure 및 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

[#import 지시문](../../preprocessor/hash-import-directive-cpp.md) 지원 되지 않습니다 **/clr: pure** 및 **/clr: safe** 때문에 `#import` 네이티브 컴파일러 지원 라이브러리를 사용 해야 합니다.

## <a name="example"></a>예

다음 샘플에서는 C2812 오류가 발생 합니다.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```