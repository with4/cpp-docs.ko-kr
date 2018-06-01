---
title: 컴파일러 경고 C4936 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0be4a565dd251da77174c401c23b8ed8bfc531b0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703941"
---
# <a name="compiler-warning-c4936"></a>컴파일러 경고 C4936

> /clr 또는 /clr:pure를 지정하여 컴파일한 경우에만 이 __declspec를 사용할 수 있습니다.

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

`__declspec` 한정자가 사용되었지만 해당 `__declspec` 한정자는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션 중 하나로 컴파일된 경우에만 유효합니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.

C4936은 항상 오류로 실행됩니다.  [warning](../../preprocessor/warning.md) pragma를 사용하여 C4936을 해제할 수 있습니다.

## <a name="example"></a>예

다음 샘플에서는 C4936을 생성합니다.

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```