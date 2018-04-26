---
title: _findclose | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _findclose
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _findclose
- findclose
dev_langs:
- C++
helpviewer_keywords:
- _findclose function
- findclose function
ms.assetid: 9216c573-0878-444c-b5d7-cdaf16fb9163
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89c1f515bb072c649a93b77e49b500ea4636e423
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="findclose"></a>_findclose

지정된 검색 핸들을 닫고 연결된 리소스를 해제합니다.

## <a name="syntax"></a>구문

```C
int _findclose(
   intptr_t handle
);
```

### <a name="parameters"></a>매개 변수

*handle*<br/>
에 대 한 이전 호출에서 반환 된 검색 핸들 **_findfirst**합니다.

## <a name="return-value"></a>반환 값

성공 하면 **_findclose** 0을 반환 합니다. 그렇지 않으면-1을 반환 하 고 설정 **errno** 를 **ENOENT**, 나타내는 더 이상 일치 하는 파일을 찾을 수 없습니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_findclose**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[시스템 호출](../../c-runtime-library/system-calls.md)<br/>
[파일 이름 검색 함수](../../c-runtime-library/filename-search-functions.md)<br/>
