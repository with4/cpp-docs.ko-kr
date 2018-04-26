---
title: __uncaught_exception | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- __uncaught_exception
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __uncaught_exception
dev_langs:
- C++
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f39e83aee5ee8c8652c32f72b6923c6c0c38a4ba
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="uncaughtexception"></a>__uncaught_exception

하나 이상의 예외가 throw 되지 했지만 아직 처리 되지 않은 해당 하는지 여부를 나타냅니다 **catch** 블록는 [try / catch](../../cpp/try-throw-and-catch-statements-cpp.md) 문.

## <a name="syntax"></a>구문

```cpp
bool __uncaught_exception(
   );
```

## <a name="return-value"></a>반환 값

**true** 에서 시간에서 예외가 throw 되는 **시도** 일치 될 때까지 차단 **catch** 고, 그렇지 않으면 초기화 된 블록은 **false**합니다.

## <a name="remarks"></a>설명

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|__uncaught_exception|eh.h|

## <a name="see-also"></a>참고자료

[try, throw 및 catch 문(C++)](../../cpp/try-throw-and-catch-statements-cpp.md)<br/>
