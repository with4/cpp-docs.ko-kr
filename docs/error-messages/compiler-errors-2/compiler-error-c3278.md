---
title: 컴파일러 오류 C3278 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3278
dev_langs:
- C++
helpviewer_keywords:
- C3278
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b993aaaee0e50eacf47ce594b4c5efa47f83dd18
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705077"
---
# <a name="compiler-error-c3278"></a>컴파일러 오류 C3278

> 직접 호출 인터페이스 또는 순수 메서드 '*메서드*' 런타임 시 실패할 수

## <a name="remarks"></a>설명

인터페이스 메서드 또는 순수 메서드를 호출했지만 허용되지 않습니다.

## <a name="example"></a>예

다음 샘플에서는 C3278을 생성합니다.

```cpp
// C3278_2.cpp
// compile with: /clr
using namespace System;
interface class I
{
   void vmf();
};

public ref class C: public I
{
public:
   void vmf()
   {
      Console::WriteLine( "In C::vmf()" );
      I::vmf(); // C3278
   }

};

int main()
{
   C^ pC = gcnew C;
   pC->vmf();
}
```