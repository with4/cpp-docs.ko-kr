---
title: "_chsize_s | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
dev_langs:
- C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eb8292d70a77a5901c710349d6912e46cfda8f63
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="chsizes"></a>_chsize_s
파일 크기를 변경합니다. [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 기능이 향상된 [_chsize](../../c-runtime-library/reference/chsize.md) 버전입니다.  
  
## <a name="syntax"></a>구문  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 열려 있는 파일을 참조하는 파일 설명자입니다.  
  
 `size`  
 파일의 새 길이(바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 파일 크기가 제대로 변경되면 `_chsize_s`는 값 0을 반환합니다. 0이 아닌 반환 값은 오류를 나타냅니다. 반환 값은 각각, 지정된 파일이 액세스에 대해 잠긴 경우 `EACCES`, 지정된 파일이 읽기 전용이거나 설명자가 올바르지 않은 경우 `EBADF`, 장치에 남아 있는 공간이 없는 경우 `ENOSPC` 또는 크기가 0보다 작은 경우 `EINVAL`입니다. `errno`는 동일한 값으로 설정됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `_chsize_s` 함수는 `fd`와 연결된 파일을 `size`로 지정된 길이까지 확장하거나 자릅니다. 파일은 쓰기를 허용하는 모드로 열려 있어야 합니다. 파일이 확장되는 경우 Null 문자('\0')가 추가됩니다. 파일이 잘린 경우 짧아진 파일의 끝부터 파일의 원래 길이까지의 모든 데이터가 손실됩니다.  
  
 `_chsize_s`는 파일 크기로 64비트 정수를 사용하므로 4GB보다 큰 파일 크기를 처리할 수 있습니다. `_chsize`는 32비트 파일 크기로 제한됩니다.  
  
 이 함수는 해당 매개 변수의 유효성을 검사합니다. `fd`가 유효한 파일 설명자가 아니거나 크기가 0보다 작은 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|-------------|---------------------|---------------------|  
|`_chsize_s`|\<io.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
