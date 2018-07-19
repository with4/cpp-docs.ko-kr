---
title: 컴파일러 경고 C4693 | Microsoft Docs
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4693
dev_langs:
- C++
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8230e60d65c80b4f839cc8a1c97ccc0c7b18086
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273883"
---
# <a name="compiler-warning-c4693"></a>컴파일러 경고 C4693

> 'class': 봉인 추상 클래스는 인스턴스 멤버 'Test'를 포함할 수 없습니다.

형식이 표시 되어 있으면 [봉인](../../windows/sealed-cpp-component-extensions.md) 및 [추상](../../windows/abstract-cpp-component-extensions.md), 정적 멤버를 하나만 사용할 수 있습니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4693을 생성합니다.

```cpp
// C4693.cpp
// compile with: /clr /c
public ref class Public_Ref_Class sealed abstract {
public:
   void Test() {}   // C4693
   static void Test2() {}   // OK
};
```