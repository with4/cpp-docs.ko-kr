---
title: "fseek, _fseeki64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
apitype: DLLExport
f1_keywords:
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
파일 포인터를 지정된 위치로 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `offset`  
 `origin`부터의 바이트 수입니다.  
  
 `origin`  
 초기 위치입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `fseek` 및 `_fseeki64`가 0을 반환합니다. 그렇지 않으면 0이 아닌 값을 반환합니다. 검색을 수행할 수 없는 장치에서는 반환 값이 정의되지 않습니다. `stream`이 null 포인터이거나 `origin`이 아래 설명된 허용된 값 중 하나가 아니면 `fseek` 및 `_fseeki64`는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 -1을 반환합니다.  
  
## <a name="remarks"></a>설명  
 `fseek` 및 `_fseeki64` 파일 포인터 (있는 경우)와 관련 된 이동 함수 `stream` 중인 새 위치에 `offset` 바이트 `origin`합니다. 스트림에 대한 다음 작업은 새 위치에서 수행됩니다. 업데이트를 위해 열린 스트림에 대한 다음 작업은 읽기 또는 쓰기일 수 있습니다. origin 인수는 STDIO.H에 정의된 다음 상수 중 하나여야 합니다.  
  
 `SEEK_CUR`  
 파일 포인터의 현재 위치  
  
 `SEEK_END`  
 파일 끝  
  
 `SEEK_SET`  
 파일 시작  
  
 `fseek` 및 `_fseeki64`를 사용하여 파일 내에서 포인터의 위치를 변경합니다. 포인터는 파일 끝을 지나서 배치될 수도 있습니다. `fseek`및 `_fseeki64` 파일 끝 표시기를 지우고 모든 사전의 결과가 무시 `ungetc` 에 대해 호출 `stream`합니다.  
  
 데이터를 추가하기 위해 파일이 열리면 현재 파일 위치는 다음 쓰기가 수행되는 위치가 아니라 마지막 I/O 작업에 의해 결정됩니다. 추가를 위해 열린 파일에서 I/O 작업이 아직 수행되지 않은 경우 파일 위치는 파일의 시작입니다.  
  
 텍스트 모드에서 열린 스트림의 `fseek` 및 `_fseeki64` 제한적으로 사용 캐리지 리턴-줄 바꿈 번역 될 수 있기 때문 `fseek` 및 `_fseeki64` 예기치 않은 결과를 생성 합니다. 유일한 `fseek` 및 `_fseeki64` 텍스트 모드에서 열린 스트림의에서 작동 하는 작업은:  
  
-   원점 값을 기준으로 한 0 오프셋을 사용하여 검색  
  
-   에 대 한 호출에서 반환 되는 오프셋된 값을 사용 하 여 파일의 시작 부분에서 찾기를 `ftell` 사용 하는 경우 `fseek` 또는 `_ftelli64` 사용 하는 경우 `_fseeki64`합니다.  
  
 또한 텍스트 모드에서 Ctrl+Z는 입력 시 파일 끝 문자로 해석됩니다. 읽기/쓰기를 위해 열린 파일에서 `fopen` 및 모든 관련 루틴은 파일 끝에 CTRL+Z가 있는지 확인하고 가능하면 이를 제거합니다. 이렇게 처리되는 이유는 `fseek` 및 `ftell`의 조합이나 `_fseeki64` 및 `_ftelli64`의 조합을 사용하여 CTRL+Z로 끝나는 파일 내에서 이동하면 `fseek` 또는 `_fseeki64`가 파일 끝 가까이에서 제대로 동작하지 않을 수 있기 때문입니다.  
  
 CRT가 BOM(바이트 순서 표시)으로 시작되는 파일을 열면 파일 포인터는 BOM 뒤(파일 실제 콘텐츠의 시작)에 배치됩니다. 파일의 시작에 대해 `fseek`를 수행해야 할 경우 `ftell`을 사용하여 최초 위치를 가져오고 위치 0이 아니라 최초 위치에 대해 `fseek`를 수행합니다.  
  
 이 함수는 실행 중에 다른 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
