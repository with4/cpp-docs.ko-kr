---
title: "fclose, _fcloseall | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
dev_langs:
- C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9399aa2848ff3f5179b711674fa524ef7543fc0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall
스트림을 닫거나(`fclose`) 모든 열린 스트림을 닫습니다(`_fcloseall`).  
  
## <a name="syntax"></a>구문  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 스트림이 성공적으로 닫히면 `fclose`는 0을 반환합니다. `_fcloseall`은 닫힌 총 스트림 수를 반환합니다. 두 함수 모두 `EOF`를 반환하여 오류를 표시합니다.  
  
## <a name="remarks"></a>설명  
 `fclose` 함수는 `stream`을 닫습니다. `stream`가 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 `fclose`는 `errno`를 `EINVAL`로 설정하고 `EOF`를 반환합니다. 이 함수를 호출하기 전에 항상 `stream` 포인터를 확인하는 것이 좋습니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
 `_fcloseall` 함수는 `stdin`, `stdout`, `stderr`(MS-DOS의 경우 `_stdaux` 및 `_stdprn`)을 제외하고 모든 열린 스트림을 닫습니다. 또한 `tmpfile`을 통해 만들어진 모든 임시 파일을 닫고 삭제합니다. 두 함수에서 모두 스트림과 연결된 모든 버퍼가 플러시된 후 닫힙니다. 시스템 할당 버퍼는 스트림이 닫힐 때 해제됩니다. `setbuf` 및 `setvbuf`를 사용하여 사용자가 할당한 버퍼는 자동으로 해제되지 않습니다.  
  
 **참고:** 이러한 함수를 사용하여 스트림을 닫으면 기본 파일 설명자와 OS 파일 핸들(또는 소켓)이 닫히고 스트림도 닫힙니다. 따라서 파일이 원래 파일 핸들이나 파일 설명자로 열렸고 `fclose`를 통해 닫힌 경우에는 파일 설명자를 닫기 위해 `_close`를 호출하지 마세요. 또한 파일 핸들을 닫기 위해 Win32 함수 `CloseHandle`을 호출하지 마세요.  
  
 `fclose` 및 `_fcloseall`에는 다른 스레드의 간섭을 방지하기 위한 코드가 포함됩니다. `fclose`의 잠기지 않은 버전은 `_fclose_nolock`를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fclose`|\<stdio.h>|  
|`_fcloseall`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)