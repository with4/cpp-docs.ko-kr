---
title: 컴파일러 오류 C3808 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3808
dev_langs:
- C++
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40668b8b2cc1a1f85b0ad4a7ef63d89956e922b3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705207"
---
# <a name="compiler-error-c3808"></a>컴파일러 오류 C3808

> '*형식*': ComImport 특성이 있는 클래스 멤버를 정의할 수 없습니다 '*멤버*'만 abstract 또는 dllimport 함수를 사용할 수

## <a name="remarks"></a>설명

파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute> 정의할 수 없습니다. *멤버*합니다.

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

## <a name="example"></a>예

다음 샘플에서는 C3808 오류가 발생 합니다.

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```