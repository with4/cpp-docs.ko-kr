---
title: 컴파일러 오류 C3862 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b21e457feb6d090e4abaf531293987eb3504457
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704973"
---
# <a name="compiler-error-c3862"></a>컴파일러 오류 C3862

> '*함수*': /clr으로 관리 되지 않은 함수를 컴파일할 수 없습니다: pure 또는 /clr: safe

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

사용한 컴파일을 **/clr: pure** 또는 **/clr: safe** 는 유일한 이미지 MSIL을 네이티브 (비관리) 코드를 사용 하 여 이미지를 생성 합니다.  따라서 사용할 수 없습니다는 `unmanaged` 에 pragma는 **/clr: pure** 또는 **/clr: safe** 컴파일 합니다.

자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [관리, 관리 되지 않는](../../preprocessor/managed-unmanaged.md)합니다.

## <a name="example"></a>예

다음 샘플에서는 C3862 오류가 생성 됩니다.

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```