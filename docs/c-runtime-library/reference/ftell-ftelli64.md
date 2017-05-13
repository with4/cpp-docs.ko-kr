---
title: "ftell, _ftelli64 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
caps.latest.revision: 19
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
ms.openlocfilehash: 220b34e5bba7a4a6716d6ef18d6621b58d36ecc3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64
파일 포인터의 현재 위치를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stream`  
 대상 `FILE` 구조체입니다.  
  
## <a name="return-value"></a>반환 값  
 `ftell` 및 `_ftelli64`는 현재 파일 위치를 반환합니다. 반환한 값 `ftell` 및 `_ftelli64` 텍스트 모드를 사용 하면 캐리지 리턴-줄 바꿈 변환 하기 때문에 텍스트 모드에서 연 스트림에 대 한 실제 바이트 오프셋을 반영 하지 않을 수 있습니다. 사용 하 여 `ftell` 와 `fseek` 또는 `_ftelli64` 와 `_fseeki64` 파일 위치를 올바르게 돌아갑니다. 오류 시 `ftell` 및 `_ftelli64` 에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)합니다. 이러한 함수 반환-1l 및 집합을 계속 하려면 실행 허용 된 경우 `errno` ERRNO에 정의 하는 두 상수 중 하나입니다. 8. `EBADF` 상수는 `stream` 인수가 유효한 파일 포인터 값이 아니거나 열린 파일을 참조하지 않음을 의미합니다. `EINVAL`은 잘못된 `stream` 인수가 함수에 전달되었음을 의미합니다. 검색을 수행할 수 없는 장치(예: 터미널 및 프린터)이거나 `stream`이 열린 파일을 참조하지 않을 경우에는 반환 값이 정의 해제됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.  
  
## <a name="remarks"></a>설명  
 `ftell` 및 `_ftelli64` 와 연결 된 파일 포인터 (있는 경우)의 현재 위치를 검색 하는 함수 `stream`합니다. 위치는 스트림 시작을 기준으로 하는 오프셋으로 표현됩니다.  
  
 데이터를 추가하기 위해 파일이 열리면 현재 파일 위치는 다음 쓰기가 수행되는 위치가 아니라 마지막 I/O 작업에 의해 결정됩니다. 예를 들어 파일이 추가를 위해 열리고 마지막 작업이 읽기였다면 파일 위치는 다음 쓰기가 시작되는 위치가 아니라 다음 읽기 작업이 시작되는 지점입니다. 파일이 추가를 위해 열린 경우 파일 위치는 쓰기 작업 전에 파일의 끝으로 이동합니다. 추가를 위해 열린 파일에서 I/O 작업이 아직 수행되지 않은 경우 파일 위치는 파일의 시작입니다.  
  
 텍스트 모드에서 Ctrl+Z는 입력 시 파일 끝 문자로 해석됩니다. 읽기/쓰기를 위해 열린 파일에서 `fopen` 및 모든 관련 루틴은 파일 끝에 CTRL+Z가 있는지 확인하고 가능하면 이를 제거합니다. 이렇게 처리되는 이유는 `ftell` 및 `fseek`의 조합이나 `_ftelli64` 및 `_fseeki64`의 조합을 사용하여 CTRL+Z로 끝나는 파일 내에서 이동하면 `ftell` 또는 `_ftelli64`가 파일 끝 가까이에서 제대로 동작하지 않을 수 있기 때문입니다.  
  
 이 함수는 실행 중에 호출 스레드를 잠그므로 스레드로부터 안전합니다. 잠기지 않는 버전의 경우 `_ftell_nolock`을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h>|\<errno.h>|  
|`_ftelli64`|\<stdio.h>|\<errno.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예제  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>참고 항목  
 [스트림 I/O](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)
