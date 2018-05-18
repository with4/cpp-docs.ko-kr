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
ms.openlocfilehash: c3dd23069f389d0a02e10d26edb7ee4fd3c373cb
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-error-c2482"></a>컴파일러 오류 C2482

>'*식별자*': WinRT 관리 코드에 사용할 수 없습니다 't h' 데이터의 동적 초기화

## <a name="remarks"></a>설명

관리 되는 또는 WinRT 코드를 사용 하 여 선언 된 변수는 [__declspec (thread)](../../cpp/thread.md) 저장소 클래스 한정자 특성 또는 [thread_local](../../cpp/storage-classes-cpp.md#thread_local) 저장소 클래스 지정자를 식으로 초기화할 수 없습니다 실행 시 평가 필요로 하 합니다. 정적 식 초기화에 필요 `__declspec(thread)` 또는 `thread_local` 이러한 런타임 환경에서 데이터입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2482 관리 (**/clr**) 및 WinRT (**/ZW**) 코드:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

문제를 해결 하려면이 문제는 상수를 사용 하 여 스레드 로컬 저장소 초기화 **constexpr**, 또는 정적 식입니다. 스레드 관련 초기화를 개별적으로 수행 합니다.