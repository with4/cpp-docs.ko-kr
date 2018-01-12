---
title: "feof | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: feof
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
f1_keywords: feof
dev_langs: C++
helpviewer_keywords:
- end of file, testing for
- feof function
ms.assetid: 09081eee-7c4b-4189-861f-2fad95d3ec6d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef20a9653263a87e0818450b1d6d0b1241f91b8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="feof"></a>feof
스트림의 파일 끝을 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int feof(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `feof` 함수는 읽기 작업이 파일의 끝 부분을 지나서 읽으려고 한 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. 스트림 포인터가 `NULL`인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용된 경우 `errno`가 `EINVAL`로 설정되고 `feof`에서 0을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `feof` 루틴(함수와 매크로 모두로 구현됨)은 `stream`의 끝을 지났는지 여부를 확인합니다. 파일의 끝을 지난 경우 읽기 작업은 스트림이 닫힐 때까지 또는 `rewind`, `fsetpos`, `fseek` 또는 `clearerr`가 이에 대해 호출될 때까지 파일 표시기의 끝을 반환합니다.  
  
 예를 들어 파일이 10바이트를 포함하고 사용자가 파일에서 10바이트를 읽는 경우 `feof`는 파일 포인터가 파일의 끝에 있는 경우에도 사용자가 끝을 넘어 읽으려고 시도하지 않았으므로 0을 반환합니다. 11번째 바이트를 읽으려고 시도한 후에만 `feof`에서 0이 아닌 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`feof`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_feof.c  
// This program uses feof to indicate when  
// it reaches the end of the file CRT_FEOF.TXT. It also  
// checks for errors with ferror.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int  count, total = 0;  
   char buffer[100];  
   FILE *stream;  
  
   fopen_s( &stream, "crt_feof.txt", "r" );  
   if( stream == NULL )  
      exit( 1 );  
  
   // Cycle until end of file reached:  
   while( !feof( stream ) )  
   {  
      // Attempt to read in 100 bytes:  
      count = fread( buffer, sizeof( char ), 100, stream );  
      if( ferror( stream ) )      {  
         perror( "Read error" );  
         break;  
      }  
  
      // Total up actual bytes read  
      total += count;  
   }  
   printf( "Number of bytes read = %d\n", total );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfeoftxt"></a>입력: crt_feof.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>출력  
  
```  
Number of bytes read = 19  
```  
  
## <a name="see-also"></a>참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)