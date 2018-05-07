---
title: 컴파일러 오류 C2482 | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c4725dd357854db504272e5b8b9d88641b143d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2482"></a>컴파일러 오류 C2482

>'*식별자*': 사용할 수 없습니다 't h' 데이터의 동적 초기화

이 오류 메시지는 Visual Studio 2015 이상 버전에서 사용 되지 않습니다. 이전 버전에서 사용 하 여 선언 된 변수는 `thread` 특성을 런타임에 평가 해야 하는 식으로 초기화할 수 없습니다. 정적 식 초기화에 필요 `thread` 데이터입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2482이 하 버전 Visual Studio 2013에서 오류가 생성 됩니다.

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
