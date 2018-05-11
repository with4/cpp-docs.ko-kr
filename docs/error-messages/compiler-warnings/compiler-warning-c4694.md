---
title: 컴파일러 경고 C4694 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4694
dev_langs:
- C++
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33852b76f23e007625f86969119a22ee81305187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4694"></a>컴파일러 경고 C4694

> '*클래스*': 봉인된 추상 클래스는 기본 클래스 '를 사용할 수 없습니다*base_class*'

추상 및 봉인 클래스가 참조 형식에서 상속할 수 없습니다. 추상 및 봉인 클래스는 기본 클래스 함수를 구현할 수도 없고 스스로를 기본 클래스로 사용할 수도 없습니다.

자세한 내용은 참조 [추상](../../windows/abstract-cpp-component-extensions.md), [봉인](../../windows/sealed-cpp-component-extensions.md), 및 [클래스 및 구조체](../../windows/classes-and-structs-cpp-component-extensions.md)합니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4694를 생성합니다.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```