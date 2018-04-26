---
title: btowc | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- btowc
dev_langs:
- C++
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f6605184408b3a1548eeb8af469fc7df1a6407c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="btowc"></a>btowc

초기 시프트 상태에서 정수가 유효한 싱글바이트 문자를 나타내는지 여부를 확인합니다.

## <a name="syntax"></a>구문

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>매개 변수

*character*<br/>
테스트할 정수입니다.

## <a name="return-value"></a>반환 값

초기 시프트 상태에서 정수가 유효한 싱글바이트 문자를 나타내는 경우 문자의 와이드 문자 표현을 반환합니다. 초기 시프트 상태에서 정수가 EOF이거나 유효한 싱글바이트 문자가 아닌 경우 WEOF를 반환합니다. 현재가이 함수의 출력에 영향을 받는 **LC_TYPE** 로캘 합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**btowc**|\<stdio.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
