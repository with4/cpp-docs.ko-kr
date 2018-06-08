---
title: 컴파일러 경고 C4959 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4959
dev_langs:
- C++
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2819664fa94ca777339156dc9a31da17b991c6da
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705166"
---
# <a name="compiler-warning-c4959"></a>컴파일러 경고 C4959

> 관리 되지 않는 구조체를 정의할 수 없습니다 '*형식*' /clr: safe에서 해당 멤버에 액세스 하면 비안정형 코드가 생성 되므로

## <a name="remarks"></a>설명

관리되지 않는 형식의 멤버에 액세스하면 확인할 수 없는 (peverify.exe) 이미지가 생성됩니다.

자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.

**/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.

## <a name="example"></a>예

다음 샘플에서는 C4959를 생성합니다.

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```