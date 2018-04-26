---
title: _get_wpgmptr | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23ebeed5b6710a7c8032f75b8677b09f8f96c84a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="getwpgmptr"></a>_get_wpgmptr

현재 값을 가져옵니다는 **_wpgmptr** 전역 변수입니다.

## <a name="syntax"></a>구문

```C
errno_t _get_wpgmptr( 
   wchar_t **pValue 
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
현재 값으로 채울 문자열에 대 한 포인터는 **_wpgmptr** 변수입니다.

## <a name="return-value"></a>반환 값

성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. 경우 *pValue* 은 **NULL**에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이 함수를 설정 하는 경우 실행을 계속 허용 된, **errno** 를 **EINVAL** 반환 **EINVAL**합니다.

## <a name="remarks"></a>설명

호출 **_get_wpgmptr** 프로그램 넓은 진입점이 있으면 같은 **wmain()** 또는 **wWinMain()** 합니다. **_wpgmptr** 전역 변수를 와이드 문자열로 프로세스와 관련 된 실행 파일의 전체 경로 포함 합니다. 자세한 내용은 [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[_get_pgmptr](get-pgmptr.md)<br/>
