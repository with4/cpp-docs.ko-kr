---
title: _fseek_nolock, _fseeki64_nolock | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
dev_langs:
- C++
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fdc44fef5de0a24e35df30d3605d1b5e46c4a6b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock, _fseeki64_nolock

파일 포인터를 지정된 위치로 이동합니다.

## <a name="syntax"></a>구문

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*offset*<br/>
*origin*부터의 바이트 수입니다.

*origin*<br/>
초기 위치입니다.

## <a name="return-value"></a>반환 값

와 동일 [fseek](fseek-fseeki64.md) 및 [_fseeki64](fseek-fseeki64.md)각각.

## <a name="remarks"></a>설명

이러한 함수는 잠기지 않은 버전의 [fseek](fseek-fseeki64.md) 및 [_fseeki64](fseek-fseeki64.md)각각. 이러한 작업은 동일 [fseek](fseek-fseeki64.md) 및 [_fseeki64](fseek-fseeki64.md) 제외 하 고 다른 스레드에서 방해 로부터 보호 되지 않습니다. 이러한 함수는 다른 스레드를 잠그는 오버헤드를 유발하지 않으므로 속도가 더 빠를 수 있습니다. 단일 스레드 응용 프로그램과 같은 스레드로부터 안전한 컨텍스트 또는 이미 스레드 격리를 처리한 호출 범위에서만 이러한 함수를 사용합니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
