---
title: _close | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e49906a1ea0bf66400a6ac753c5d4041bc47217c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="close"></a>_close

파일을 닫습니다.

## <a name="syntax"></a>구문

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>매개 변수

*fd*<br/>
열려 있는 파일을 참조하는 파일 설명자입니다.

## <a name="return-value"></a>반환 값

**_close** 파일이 성공적으로 종료 된 경우 0을 반환 합니다. 반환 값-1의 오류를 나타냅니다.

## <a name="remarks"></a>설명

**_close** 함수에 연결 된 파일을 닫고 *fd*합니다.

파일 설명자와 기본 OS 파일 핸들을 닫습니다. 따라서 호출할 필요가 없습니다는 **CloseHandle** 파일을 원래 Win32 함수를 사용 하 여 연 경우 **CreateFile** 사용 하는 파일 설명자를 변환할 **_open_osfhandle**.

이 함수는 해당 매개 변수의 유효성을 검사합니다. 경우 *fd* 은 잘못 된 파일 설명자에 설명 된 대로 잘못 된 매개 변수 처리기가 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 함수 실행을 계속 허용 된,-1을 반환 하 고 **errno** 로 설정 된 **EBADF**합니다.

## <a name="requirements"></a>요구 사항

|루틴|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_open](open-wopen.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
