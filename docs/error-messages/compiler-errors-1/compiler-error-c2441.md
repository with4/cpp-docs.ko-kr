---
title: 컴파일러 오류 C2441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4224d9090f3ace43f61a10c599fafa78d21600
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705282"
---
# <a name="compiler-error-c2441"></a>컴파일러 오류 C2441

> '*변수*': __declspec (process)를 사용 하 여 선언 기호는 /clr에서 const 여야 합니다: pure 모드

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

변수는 기본적으로 응용 프로그램 도메인 별로 **/clr: pure**합니다. 변수 표시 `__declspec(process)` 에서 **/clr: pure** 한 응용 프로그램 도메인에서 수정 하 고 다른 읽을 경우 오류가 발생할 가능성이 높습니다.

변수 프로세스 마다 경우 컴파일러는 따라서 `const` 아래 **/clr: 순수**, 모든 응용 프로그램 도메인에만 읽을 만들기.

자세한 내용은 참조 [프로세스](../../cpp/process.md) 및 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.

## <a name="example"></a>예

다음 샘플에서는 C2441 오류가 발생 합니다.

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```