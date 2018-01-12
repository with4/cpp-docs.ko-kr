---
title: toascii, __toascii | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: __toascii
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
- __toascii
- toascii
- ctype/toascii
- ctype/__toascii
dev_langs: C++
helpviewer_keywords:
- toascii function
- string conversion, to ASCII characters
- __toascii function
- ASCII characters, converting to
ms.assetid: a07c0608-b0e2-4da2-a20c-7b64d6a9b77c
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25e11878772b4c8f7afb07f7297ca80a2a5a0130
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="toascii-toascii"></a>toascii, __toascii

잘라내기를 통해 문자를 7비트 ASCII로 변환합니다.

## <a name="syntax"></a>구문

```C
int __toascii(
   int c
);
#define toascii __toascii
```

### <a name="parameters"></a>매개 변수

*c*  
변환할 문자입니다.

## <a name="return-value"></a>반환 값

`__toascii`값으로 변환 *c* 7 비트 ascii 범위 및 결과 반환 합니다. 오류를 나타내기 위해 예약된 반환 값은 없습니다.

## <a name="remarks"></a>설명

`__toascii` 루틴은 하위 순서의 7비트를 잘라내는 방법으로 지정된 문자를 ASCII 문자로 변환합니다. 다른 변환은 적용되지 않습니다.

전처리기 매크로 _CTYPE_DISABLE_MACROS가 정의되지 않은 경우 `__toascii` 루틴은 매크로로 정의됩니다. 이전 버전과 호환성을 위해 `toascii` 매크로로 정의 된 경우에만 [&#95; &#95; STDC &#95; #95 ](../../preprocessor/predefined-macros.md) 이 정의 되지 않았거나; 0으로 정의 하지 않으면 정의 되지 않습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`toascii`, `__toascii`|C: \<ctype.h><br /><br /> C++: \<cctype> 또는 \<ctype.h>|

`toascii` 매크로는 POSIX 확장이고 `__toascii`는 POSIX 확장의 Microsoft 관련 구현입니다. 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.

## <a name="see-also"></a>참고 항목

[데이터 변환](../../c-runtime-library/data-conversion.md)   
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)   
[to 함수](../../c-runtime-library/to-functions.md)