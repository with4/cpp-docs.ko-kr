---
title: _putch, _putwch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _putwch
- _putch
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _putch
- putwch
- _putwch
dev_langs:
- C++
helpviewer_keywords:
- _putch function
- characters, writing
- putwch function
- _putwch function
- putch function
- console, writing characters to
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2c1810207b9af2cfccbd0bf9502952ad96fb9465
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="putch-putwch"></a>_putch, _putwch

콘솔에 문자를 씁니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _putch(
int c
);
wint_t _putwch(
   wchar_t c
);
```

### <a name="parameters"></a>매개 변수

*c*<br/>
출력할 문자입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되면 *c*를 반환합니다. 경우 **_putch** 실패 하면 반환 **EOF**경우 **_putwch** 실패 하면 반환 **WEOF**합니다.

## <a name="remarks"></a>설명

이러한 함수는 문자를 쓸 *c* 콘솔에 버퍼링 하지 않고 직접 합니다. Windows NT에서 **_putwch**는 현재 콘솔 로캘 설정을 사용하여 유니코드 문자를 씁니다.

**_nolock** 접미사가 있는 버전은 다른 스레드에 의한 간섭에서 보호되지 않는 점을 제외하면 동일합니다. 자세한 내용은 참조 **_putch_nolock**, **_putwch_nolock**합니다.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_puttch**|**_putch**|**_putch**|**_putwch**|

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|
|-------------|---------------------|
|**_putch**|\<conio.h>|
|**_putwch**|\<conio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="example"></a>예제

[_getch](getch-getwch.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[콘솔 및 포트 I/O](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
