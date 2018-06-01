---
title: 컴파일러 오류 C3768 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6b7a2d1617591609f75b2b07f1a94983ee22f4
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704960"
---
# <a name="compiler-error-c3768"></a>컴파일러 오류 C3768

> 순수 관리 코드에서는 가상 vararg 함수의 주소를 가져올 수 없습니다.

## <a name="remarks"></a>설명

**/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

로 컴파일할 때 **/clr: pure**를 가상의 주소를 가져올 수 없습니다 `vararg` 함수입니다.

## <a name="example"></a>예

다음 샘플에서는 C3768 오류가 생성 됩니다.

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```