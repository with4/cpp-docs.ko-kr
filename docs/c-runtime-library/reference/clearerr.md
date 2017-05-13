---
title: "clearerr | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- clearerr
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
- clearerr
dev_langs:
- C++
helpviewer_keywords:
- error indicator for streams
- resetting stream error indicator
- clearerr function
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
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
ms.openlocfilehash: 4f6f82645eba2fc2e1c78ba4dd88751943a62e76
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="clearerr"></a>clearerr
스트림에 대한 오류 표시기를 다시 설정합니다. 이 함수의 더 안전한 버전을 사용할 수 있습니다. [clearerr_s](../../c-runtime-library/reference/clearerr-s.md)를 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `clearerr` 함수는 `stream`에 대한 오류 표시기 및 파일 끝 표시기를 다시 설정합니다. 오류 표시기는 자동으로 취소되지 않습니다. 지정된 스트림에 대한 오류 표시기가 설정되면 `clearerr`, `fseek`, `fsetpos` 또는 `rewind`가 호출될 때까지 해당 스트림의 작업은 오류 값을 계속 반환합니다.  
  
 `stream`이 `NULL`인 경우 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속 실행하도록 허용된 경우 이 함수는 `errno`를 `EINVAL`로 설정하고 반환합니다. `errno` 및 오류 코드에 대한 자세한 내용은 [errno 상수](../../c-runtime-library/errno-constants.md)를 참조하세요.  
  
 이 함수의 더 안전한 버전을 사용할 수 있습니다. [clearerr_s](../../c-runtime-library/reference/clearerr-s.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`clearerr`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
```Output  
  
n  
  
```  
  
```Output  
  
      nWrite error: No error  
Will input cause an error? n  
No read error  
```  
  
## <a name="see-also"></a>참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)
