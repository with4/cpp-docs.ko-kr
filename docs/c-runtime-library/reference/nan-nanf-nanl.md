---
title: nan, nanf, nanl | Microsoft Docs
ms.custom: ''
ms.date: 94/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- nanf
- nan
- nanl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- nan
- nanl
- nanf
dev_langs:
- C++
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 204d59d88c97d9b0fa161fda6f64f31267c73fd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401453"
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl

Quiet NaN 값을 반환합니다.

## <a name="syntax"></a>구문

```C
double nan( const char* input );
float nanf( const char* input );
long double nanl( const char* input );
```

### <a name="parameters"></a>매개 변수

*input*<br/>
문자열 값입니다.

## <a name="return-value"></a>반환 값

**nan** 함수는 quiet NaN 값을 반환 합니다.

## <a name="remarks"></a>설명

**nan** 함수는 quiet (비 신호) NaN에 해당 하는 부동 소수점 값을 반환 합니다. *입력* 값은 무시 됩니다. 출력에 NaN이 나타나는 방법에 대한 자세한 내용은 [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)를 참조하세요.

## <a name="requirements"></a>요구 사항

|함수|C 헤더|C++ 헤더|
|--------------|--------------|------------------|
|**nan**, **nanf**, **nanl**|\<math.h>|\<cmath> 또는 \<math.h>|

## <a name="see-also"></a>참고자료

[부동 소수점 지원](../../c-runtime-library/floating-point-support.md)<br/>
[_finite, _finitef](finite-finitef.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
