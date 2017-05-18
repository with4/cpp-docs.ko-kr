---
title: _read | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _read
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
- _read
dev_langs:
- C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6387edb05977f90fe9fb2419a1eccb47ac0b7b43
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="read"></a>_read
파일에서 데이터를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 열려 있는 파일을 참조하는 파일 설명자입니다.  
  
 *buffer*  
 데이터의 저장소 위치입니다.  
  
 *count*  
 최대 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 _**읽을** 작은 일 수 있는 읽은 바이트 수를 반환 보다 *count* 보다 적은 경우 *count* 파일에 남아 있는 바이트 또는 파일이 텍스트 모드로 열려 있으면이 경우 각 캐리지 리턴-줄 바꿈 (CR-LF) 쌍 단일 줄 바꿈 문자로 바뀝니다. 반환 값에서는 단일 줄 바꿈 문자만 계산됩니다. 이러한 바꾸기는 파일 포인터에 영향을 주지 않습니다.  
  
 함수는 파일의 끝에서 읽기를 시도하는 경우 0을 반환합니다. `fd`가 잘못되었거나, 파일이 읽기를 위해 열려 있지 않거나 잠겨 있으면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용한 경우 함수는 -1을 반환하고 `errno` 를 `EBADF`로 설정합니다.  
  
 *buffer*가 **NULL**인 경우 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 함수는 -1을 반환하고 `errno`는 `EINVAL`로 설정됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 The `_read` 함수는 `fd`와 연결된 파일에서 최대 *count*바이트를 *buffer*로 읽습니다. 읽기 작업은 지정된 파일과 연결된 파일 포인터의 현재 위치에서 시작됩니다. 읽기 작업 후 파일 포인터는 읽지 않은 다음 문자를 가리킵니다.  
  
 파일을 텍스트 모드에서 연 경우 `_read`가 파일 끝 표시기로 처리되는 CTRL+Z 문자를 발견하면 읽기는 종료됩니다. 파일 끝 표시기를 지우려면 [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md)를 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 소개에서 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="libraries"></a>라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## <a name="example"></a>예제  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtreadtxt"></a>입력: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## <a name="output"></a>출력  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>참고 항목  
 [하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_write](../../c-runtime-library/reference/write.md)
