---
title: 컴파일러 오류 C3268 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3268
dev_langs:
- C++
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eac0c4e7c25df466ecf1e7e28bccf9ee2a2e2953
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705259"
---
# <a name="compiler-error-c3268"></a>컴파일러 오류 C3268

> '*함수*': 제네릭 함수 또는 제네릭 클래스의 멤버-함수는 가변 매개 변수 목록을 사용할 수 없습니다

## <a name="remarks"></a>설명

**/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

참조 [제네릭](../../windows/generics-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.

## <a name="example"></a>예

다음 샘플에서는 C3268을 생성합니다.

```cpp
// C3268.cpp
// compile with: /clr:pure /c
generic <class ItemType>
void Test(ItemType item, ...) {}   // C3268
// try the following line instead
// void Test(ItemType item) {}

generic <class ItemType2>
ref struct MyStruct { void Test(...){} };   // C3268
// try the following line instead
// ref struct MyStruct { void Test2(){} };   // OK
```