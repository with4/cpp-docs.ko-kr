---
title: 컴파일러 경고 (수준 4) C4061 | Microsoft Docs
ms.custom: ''
ms.date: 11/30/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4061
dev_langs:
- C++
helpviewer_keywords:
- C4061
ms.assetid: a99cf88e-7941-4519-8b1b-f6889d914b2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0086ea5e590c7183024bc4dcc93e2f2522f483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4061"></a>컴파일러 경고 (수준 4) C4061

> 열거자 '*식별자*열거형의 스위치' 에서'*열거형*'는 case 레이블에 의해 명시적으로 처리 되지 않습니다

연결 된 처리기에는 열거자를 `switch` 문.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

## <a name="example"></a>예제

다음 샘플에서는 C4061; 문제를 해결 하려면 누락 된 열거자에 대 한 사례를 추가 합니다.

```cpp
// C4061.cpp
// compile with: /W4
#pragma warning(default : 4061)

enum E { a, b, c };
void func ( E e )
{
   switch(e)
   {
      case a:
      case b:
      default:
         break;
   }   // C4061 c' not handled
}

int main()
{
}
```