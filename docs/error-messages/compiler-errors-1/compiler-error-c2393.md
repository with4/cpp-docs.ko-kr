---
title: 컴파일러 오류 C2393 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 057537c8efcf6e827d9ac9aaf36c0eace6d24156
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704032"
---
# <a name="compiler-error-c2393"></a>컴파일러 오류 C2393

> '*기호*': 세그먼트에 appdomain 별 기호를 할당할 수 없습니다 '*세그먼트*'

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

사용 [appdomain](../../cpp/appdomain.md) 변수 의미와 컴파일하는 **/clr: pure** 또는 **/clr: safe**, 안전 또는 순수 이미지는 데이터 세그먼트를 포함할 수 없습니다.

참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 자세한 정보에 대 한 합니다.

## <a name="example"></a>예

다음 샘플에서는 C2393 오류가 발생 합니다. 이 문제를 해결 하려면 데이터 세그먼트를 만들지 마십시오.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```