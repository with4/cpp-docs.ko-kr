---
title: setbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- setbuf
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
- setbuf
dev_langs:
- C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
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
ms.openlocfilehash: 2fee25a696156136b7ef61402282a5e22ae31d05
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="setbuf"></a>setbuf
스트림 버퍼링을 제어합니다. 이 함수는 사용되지 않습니다. 대신 [setvbuf](../../c-runtime-library/reference/setvbuf.md)를 사용하세요.  
  
## <a name="syntax"></a>구문  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `buffer`  
 사용자가 할당한 버퍼입니다.  
  
## <a name="remarks"></a>설명  
 `setbuf` 함수는 `stream`에 대한 버퍼링을 제어합니다. `stream` 인수는 읽거나 쓰지 않은 열려 있는 파일을 참조해야 합니다. `buffer` 인수가 `NULL`인 경우 스트림은 버퍼링되지 않습니다. 그렇지 않은 경우 버퍼는 길이가 `BUFSIZ`인 문자 배열을 가리켜야 합니다. 여기서 `BUFSIZ`는 STDIO.H에 정의된 대로 버퍼 크기입니다. 지정된 스트림에 대한 기본 시스템 할당 버퍼 대신 사용자 지정 버퍼가 I/O 버퍼링에 사용됩니다. `stderr` 스트림은 기본적으로 버퍼링되지 않습니다. 그러나 `setbuf`를 사용하여 버퍼를 `stderr`에 할당할 수 있습니다.  
  
 `setbuf`는 새 코드에 대한 기본 설정 루틴인 [setvbuf](../../c-runtime-library/reference/setvbuf.md)로 바뀌었습니다. `setbuf`는 기존 코드와의 호환성을 위해 유지됩니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
stream1 set to user-defined buffer at: 0012FCDC  
stream2 buffering disabled  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
