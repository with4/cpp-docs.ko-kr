---
title: fsetpos | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fsetpos
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fsetpos
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ceacacbe029488995c47e305682b56751347591
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="fsetpos"></a>fsetpos

스트림 위치 표시기를 설정합니다.

## <a name="syntax"></a>구문

```C
int fsetpos(
   FILE *stream,
   const fpos_t *pos
);
```

### <a name="parameters"></a>매개 변수

*스트림*<br/>
**FILE** 구조체에 대한 포인터입니다.

*pos*<br/>
위치 표시기 저장소입니다.

## <a name="return-value"></a>반환 값

성공 하면 **fsetpos** 0을 반환 합니다. 함수가 실패, 0이 아닌 값을 반환 합니다 설정 **errno** 다음 중 하나에 매니페스트 상수 (ERRNO에 정의 합니다. H): **EBADF**, 즉, 파일에 액세스할 수 없는 또는 개체는 *스트림* 사용가 가리키는 올바른 파일 구조를 또는 **EINVAL**, 즉, 잘못 된 값에 대 한 *스트림* 또는 *pos* 전달 되었습니다. 잘못된 매개 변수가 전달되면 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.

## <a name="remarks"></a>설명

**fsetpos** 함수에 대 한 파일 위치 표시기 설정 *스트림* 의 값에 *pos*, 이전 호출에서 얻을 수 있는 **fgetpos**에 대해 *스트림*합니다. 함수 파일 끝 표시기를 지우고 취소의 영향이 [ungetc](ungetc-ungetwc.md) 에 *스트림*합니다. 호출한 후 **fsetpos**에 다음 동작 *스트림* 수 중 입력 또는 출력 수 있습니다.

## <a name="requirements"></a>요구 사항

|함수|필수 헤더|
|--------------|---------------------|
|**fsetpos**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fgetpos](fgetpos.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
