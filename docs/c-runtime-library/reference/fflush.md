---
title: "fflush | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23d90b61862736fc97c18343fe82f8ccf3aa42b5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="fflush"></a>fflush
스트림을 플러시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 버퍼가 성공적으로 플러시된 경우 `fflush`는 0을 반환합니다. 지정된 스트림에 버퍼가 없거나 해당 스트림이 읽기 전용으로 열린 경우에도 값 0이 반환됩니다. `EOF`의 반환 값은 오류를 나타냅니다.  
  
> [!NOTE]
>  `fflush`가 `EOF`를 반환한다면 쓰기 오류로 인해 데이터가 손실되었을 수 있습니다. 오류 처리기를 설정할 경우 `setvbuf` 함수를 사용하여 버퍼링을 끄거나 스트림 I/O 함수 대신 `_open`, `_close`, `_write` 등의 하위 수준 I/O 루틴을 사용하는 것이 가장 안전합니다.  
  
## <a name="remarks"></a>설명  
 `fflush` 함수는 스트림 `stream`을 플러시합니다. 스트림이 쓰기 모드에서 열렸거나 업데이트 모드에서 열리고 마지막 작업이 쓰기였던 경우 스트림 버퍼의 콘텐츠가 기본 파일 또는 장치에 기록되고 버퍼가 삭제됩니다. 스트림이 읽기 모드에서 열렸거나 스트림에 버퍼가 없는 경우 `fflush`에 대한 호출이 영향을 미치지 않고 모든 버퍼가 유지됩니다. `fflush` 호출은 스트림에 대한 이전 `ungetc` 호출의 결과를 부정합니다. 스트림은 호출 후에 열려 있습니다.  
  
 `stream`이 `NULL`이면 해당 동작은 각 열린 스트림에 대한 `fflush` 호출과 같습니다. 쓰기 모드로 열린 모든 스트림과 마지막 작업이 쓰기인 업데이트 모드로 열린 모든 스트림이 플러시됩니다. 이 호출은 다른 스트림에 영향을 미치지 않습니다.  
  
 버퍼는 보통 운영 체제에서 유지 관리됩니다. 운영 체제에서는 버퍼가 가득 찼을 때, 스트림이 닫혀 있을 때, 스트림을 닫지 않고 프로그램이 정상적으로 종료될 때 등 디스크에 데이터를 자동으로 쓰는 최적의 시간을 결정합니다. 런타임 라이브러리의 디스크에 커밋 기능을 사용하면 중요한 데이터가 운영 체제 버퍼 대신 디스크에 직접 기록되어 있는지 확인할 수 있습니다. 기존 프로그램을 다시 작성하지 않고 프로그램의 개체 파일을 COMMODE.OBJ에 연결하여 이 기능을 사용할 수 있습니다. 결과 실행 파일에서 `_flushall`을 호출하면 모든 버퍼의 내용이 디스크에 쓰여집니다. `_flushall` 및 `fflush`만 COMMODE.OBJ의 영향을 받습니다.  
  
 디스크에 커밋 기능을 제어하는 방법에 대한 자세한 내용은 [스트림 I/O](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) 및 [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)을 참조하세요.  
  
 이 함수는 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 `_fflush_nolock`을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fflush`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## <a name="example"></a>예  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
```Output  
  
      This is a test  
This is a test  
  
```  
  
```Output  
  
      This is a test  
This is a testEnter a sentence of four words with scanf: This is a test  
This  
is  
a  
test  
Enter the same sentence with gets: This is a test  
This is a test  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)