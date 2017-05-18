---
title: "fgetpos | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c53e5742a518934ad0afcfaa06ad4e5905c484e3
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="fgetpos"></a>fgetpos
스트림의 파일 위치 표시기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 대상 스트림입니다.  
  
 `pos`  
 위치 표시기 저장소입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `fgetpos`가 0을 반환합니다. 오류가 발생하면 0이 아닌 값을 반환하고 `errno`를 STDIO.H에 정의된 다음 매니페스트 상수 `EBADF`(지정된 스트림이 유효한 파일 포인터가 아니거나 액세스할 수 없음을 의미) 또는 `EINVAL`(`stream` 값 또는 `pos` 값이 null 포인터인 경우 잘못되었음을 의미) 중 하나로 설정합니다. `stream` 또는 `pos`가 `NULL` 포인터인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  
  
## <a name="remarks"></a>설명  
 `fgetpos` 함수는 `stream` 인수 파일 위치 표시기의 현재 값을 가져오고 `pos`가 가리키는 개체에 저장합니다. `fsetpos` 함수는 나중에 `pos`에 저장된 정보를 사용하여 `fgetpos`가 호출되었던 위치에 대한 `stream` 인수의 포인터를 재설정합니다. `pos` 값은 내부 형식으로 저장되고 `fgetpos` 및 `fsetpos`에서만 사용됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetpostxt"></a>입력: crt_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### <a name="output-crtfgetpostxt"></a>출력 crt_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)
