---
title: "fread | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fread
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
- fread
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d01c3362c94b0c644cb53aec6e45ce83b98dbf07
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fread"></a>fread
스트림에서 데이터를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buffer`  
 데이터의 저장소 위치입니다.  
  
 `size`  
 항목 크기(바이트)입니다.  
  
 `count`  
 읽힐 항목의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `fread` 일 수 있는 반환 실제로 읽어 온 전체 항목 수, 미만 `count` 오류가 발생 한 경우 또는 파일의 끝에 도달 하기 전에 발견 되 면 `count`합니다. 읽기 오류와 파일 끝 조건을 구분하려면 `feof` 또는 `ferror` 함수를 사용하세요. `size` 또는 `count`가 0이면 `fread`는 0을 반환하고 버퍼 콘텐츠가 변경되지 않습니다. `stream` 또는 `buffer`가 null 포인터인 경우 `fread`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이 함수는 `errno`를 `EINVAL` 로 설정하고 0을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `fread` 함수는 `stream`에서 입력 `size`바이트 중 최대 `count`개 항목을 읽고 `buffer`에 저장합니다. `stream`(한 개가 있는 경우)과 연결된 파일 포인터는 실제로 읽은 바이트 수만큼 증분됩니다. 지정 된 스트림으로 텍스트 모드로 열리면, 캐리지 리턴-줄 바꿈 쌍 단일 줄 바꿈 문자로 대체 됩니다. 이렇게 바뀌더라도 파일 포인터 또는 반환 값에는 영향을 미치지 않습니다. 오류가 발생할 경우 파일 포인터 위치는 비활성화 상태입니다. 부분적으로 읽은 항목의 값은 확인할 수 없습니다.  
  
 이 함수는 다른 스레드를 잠급니다. 잠기지 않은 버전이 필요하면 `_fread_nolock`을 사용하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fread`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
```Output  
Wrote 25 items  
Number of items read = 25  
Contents of buffer = zyxwvutsrqponmlkjihgfedcb  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)