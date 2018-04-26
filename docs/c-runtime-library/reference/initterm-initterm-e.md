---
title: _initterm, _initterm_e | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _initterm_e
- _initterm
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 968e354662deb065aa373d3044f638dc6cf077c4
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

함수 포인터의 테이블을 실행하고 초기화하는 내부 메서드입니다.

첫 번째 포인터는 테이블의 시작 위치이고 두 번째 포인터는 끝 위치입니다.

## <a name="syntax"></a>구문

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>반환 값

초기화에 실패하면 0이 아닌 값을 반환하고 오류를 throw하고, 오류가 발생하지 않으면 0을 반환합니다.

## <a name="remarks"></a>설명

이러한 메서드는 C++ 프로그램 초기화 중 내부적으로만 호출됩니다. 프로그램에서 이러한 메서드를 호출하지 마십시오.

건너뛸 때 함수 항목의 테이블을 실행 하는 이러한 메서드를 **NULL** 항목 하 고 계속 합니다.

## <a name="see-also"></a>참고자료

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
