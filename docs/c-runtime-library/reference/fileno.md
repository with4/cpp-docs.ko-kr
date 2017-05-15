---
title: "_fileno | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fileno
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
- _fileno
dev_langs:
- C++
helpviewer_keywords:
- file handles [C++], getting from streams
- fileno function
- _fileno function
- streams, getting file handles
ms.assetid: 86474174-2f17-4100-bcc4-352dd976c7b5
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: e5a2f9c68eef3698886afd2ed48690d8b4fffd53
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="fileno"></a>_fileno
스트림에 연결된 파일 설명자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _fileno(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `_fileno`는 파일 설명자를 반환합니다. 반환되는 오류가 없습니다. `stream`이 열린 파일을 지정하지 않을 경우 결과가 정의 해제됩니다. 스트림이 `NULL`인 경우 `_fileno`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 이 함수는 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
> [!NOTE]
>  `stdout` 또는 `stderr`가 출력 스트림과 연결되지 않은 경우(예: 콘솔 창이 없는 Windows 응용 프로그램에서) 반환된 파일 설명자는 -2입니다. 이전 버전에서 반환된 파일 설명자는 -1이었습니다. 이렇게 변경되어 응용 프로그램이 이 조건을 오류와 구분할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `_fileno` 루틴은 지정된 스트림과 현재 `stream`과 연결된 파일 설명자를 반환합니다. 이 루틴은 함수 및 매크로로 구현됩니다. 구현 선택에 대한 자세한 내용은 [함수와 매크로 중 선택](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`_fileno`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fileno.c  
// This program uses _fileno to obtain  
// the file descriptor for some standard C streams.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   printf( "The file descriptor for stdin is %d\n", _fileno( stdin ) );  
   printf( "The file descriptor for stdout is %d\n", _fileno( stdout ) );  
   printf( "The file descriptor for stderr is %d\n", _fileno( stderr ) );  
}  
```  
  
```Output  
The file descriptor for stdin is 0  
The file descriptor for stdout is 1  
The file descriptor for stderr is 2  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [_filelength, _filelengthi64](../../c-runtime-library/reference/filelength-filelengthi64.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)
