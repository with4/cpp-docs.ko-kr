---
title: "컴파일러 오류 C2482 | Microsoft Docs"
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4a5d081e7a19f09f10e40e3799f724f44b295fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2482"></a>컴파일러 오류 C2482

>'*식별자*': 사용할 수 없습니다 't h' 데이터의 동적 초기화

이 오류 메시지는 Visual Studio 2015 이상 버전에서 사용 되지 않습니다. 이전 버전에서 사용 하 여 선언 된 변수는 `thread` 특성을 런타임에 평가 해야 하는 식으로 초기화할 수 없습니다. 정적 식 초기화에 필요 `thread` 데이터입니다.

## <a name="example"></a>예

다음 샘플에서는 C2482이 하 버전 Visual Studio 2013에서 오류가 생성 됩니다.

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
