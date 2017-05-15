---
title: "_filelength, _filelengthi64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _filelengthi64
- _filelength
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
- _filelength
- _filelengthi64
- filelengthi64
dev_langs:
- C++
helpviewer_keywords:
- filelengthi64 function
- lengths, file
- filelength function
- _filelength function
- files [C++], length
- _filelengthi64 function
ms.assetid: 3ab83d5a-543c-4079-b9d9-0abfc7da0275
caps.latest.revision: 14
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a09dca7637c950988dbf9a0cda12f7e14b8cecee
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="filelength-filelengthi64"></a>_filelength, _filelengthi64
파일의 길이를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
long _filelength(   
   int fd   
);  
__int64 _filelengthi64(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 파일 설명자를 대상으로 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 `_filelength` 및 `_filelengthi64` 모두 `fd`와 연결된 대상 파일의 파일 길이(바이트)를 반환합니다. `fd`가 잘못된 파일 설명자인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 두 함수를 오류를 나타내는 설정-1l을 반환 실행 허용 된 경우 계속 하려면, `errno` 를 `EBADF`합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_filelength`|\<io.h>|  
|`_filelengthi64`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 [_chsize](../../c-runtime-library/reference/chsize.md)의 예제를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)   
 [_stat, _wstat 함수](../../c-runtime-library/reference/stat-functions.md)
