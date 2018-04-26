---
title: _get_terminate | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_terminate
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
- get_terminate
- _get_terminate
- __get_terminate
dev_langs:
- C++
helpviewer_keywords:
- __get_terminate function
- get_terminate function
- _get_terminate function
ms.assetid: c8f168c4-0ad5-4832-a522-dd1ef383c208
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f63b082baf46fadb95a3513c3616116b6aed785d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="getterminate"></a>_get_terminate

호출할 종료 루틴 반환 **종료**합니다.

## <a name="syntax"></a>구문

```C
terminate_function _get_terminate( void );
```

## <a name="return-value"></a>반환 값

[set_terminate](set-terminate-crt.md)로 등록된 함수에 대한 포인터를 반환합니다. 함수가 설정되지 않은 경우 반환 값은 기본 동작을 복원하는 데 사용되며 이 값은 NULL일 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_get_terminate**|\<eh.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[예외 처리 루틴](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
