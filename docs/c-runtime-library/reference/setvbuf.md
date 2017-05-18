---
title: setvbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setvbuf
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
- setvbuf
dev_langs:
- C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
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
ms.openlocfilehash: 3955a2e5c2f0371c804f1b5a7374540ca8720339
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="setvbuf"></a>setvbuf
스트림 버퍼링 및 버퍼 크기를 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `buffer`  
 사용자가 할당한 버퍼입니다.  
  
 `mode`  
 버퍼링 모드입니다.  
  
 `size`  
 버퍼 크기(바이트)입니다. 허용 가능한 범위는 2 <= `size` <= INT_MAX (2147483647)입니다. 내부적으로 `size`에 대해 제공되는 값은 가장 가까운 2의 배수로 내려집니다.  
  
## <a name="return-value"></a>반환 값  
 정상적으로 실행되는 경우 0을 반환합니다.  
  
 `stream`이 `NULL`이거나 `mode` 또는 `size`가 유효한 변경 범위 내에 없으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 이 함수는 -1을 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 `setvbuf` 함수를 사용하면 프로그램이 `stream`에 대한 버퍼링 및 버퍼 크기를 모두 제어할 수 있습니다. `stream`은 열린 이후 I/O 작업이 수행되지 않은 열린 파일을 참조해야 합니다. `buffer`에서 가리키는 배열은 버퍼로 사용됩니다. 단, 배열이 `NULL`인 경우 `setvbuf`는 길이가 `size`/2 * 2바이트인 자동으로 할당된 버퍼를 사용합니다.  
  
 모드는 `_IOFBF`, `_IOLBF` 또는 `_IONBF`여야 합니다. `mode`가 `_IOFBF` 또는 `_IOLBF`이면 `size`가 버퍼의 크기로 사용됩니다. `mode`가 `_IONBF`이면 스트림은 버퍼링 해제되며 `size` 및 `buffer`는 무시됩니다. `mode`의 값과 해당 의미는 다음과 같습니다.  
  
 `_IOFBF`  
 전체 버퍼링입니다. 즉, `buffer`를 버퍼로 사용하고 `size`를 버퍼의 크기로 사용합니다. `buffer`가 `NULL`이면 `size`바이트 길이의 자동으로 할당된 버퍼가 사용됩니다.  
  
 `_IOLBF`  
 이 값을 사용하는 경우 라인 버퍼링이 제공되는 시스템도 있습니다. 그러나 Win32의 동작은 `_IOFBF` - 전체 버퍼링과 동일합니다.  
  
 `_IONBF`  
 `buffer` 또는 `size`에 관계없이 버퍼가 사용되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)
