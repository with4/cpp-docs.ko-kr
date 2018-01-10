---
title: _write | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _write
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
f1_keywords: _write
dev_langs: C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2169415576f29f6d64d8f597da61fa65a8f7bf2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="write"></a>_write
파일에 데이터를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
int _write(  
   int fd,  
   const void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fd`  
 데이터를 쓸 파일의 파일 설명자입니다.  
  
 `buffer`  
 쓸 데이터입니다.  
  
 `count`  
 바이트 수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 `_write`는 실제로 쓴 바이트 수를 반환합니다. 디스크에 남아 있는 실제 공간이 함수가 디스크에 쓰려는 버퍼 크기보다 작으면 `_write`에 실패하고 버퍼의 어떤 내용도 디스크로 플러시하지 않습니다. 반환 값-1의 오류를 나타냅니다. 잘못된 매개 변수가 전달되면 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 계속해서 실행하도록 허용한 경우 함수는 -1을 반환하고 `errno`는 다음 3개 값 중 하나로 설정됩니다. `EBADF`는 파일 설명자가 잘못되었거나 파일이 쓸 수 있도록 열리지 않았음을 나타내고, `ENOSPC`는 장치에 작업을 실행하는 데 충분한 공간이 없음을 나타내고, `EINVAL`은 `buffer`가 null 포인터이거나 `count`의 홀수 바이트가 유니코드 모드에서 파일에 쓰도록 전달되었음을 나타냅니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
 텍스트 모드에서의 파일을 열면 각 줄 바꿈 문자는 캐리지 리턴-줄 바꿈 쌍 출력에서으로 바뀝니다. 바뀌더라도 반환 값에는 영향을 미치지 않습니다.  
  
 파일이 유니코드 변환 모드에서 열리는 경우(예: `_O_WTEXT`, `_O_U16TEXT`, `_O_U8TEXT`가 포함된 모드 매개 변수와 `_open` 또는 `_sopen`을 사용하여 `fd`를 연 경우, `ccs=UNICODE`, `ccs=UTF-16LE`, `ccs=UTF-8`이 포함된 모드 매개 변수와 `fopen`을 사용하여 연 경우나 `_setmode`를 사용하여 모드를 유니코드 변환 모드로 변경한 경우) `buffer`는 **UTF-16** 데이터가 포함된 `wchar_t`의 배열에 대한 포인터로 해석됩니다. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.  
  
## <a name="remarks"></a>설명  
 `_write` 함수는 `count`에서 `buffer`와 연결된 파일로 `fd` 바이트를 씁니다. 쓰기 작업은 지정된 파일과 연결된 파일 포인터(있는 경우)의 현재 위치에서 시작됩니다. 추가의 목적으로 파일을 연 경우 쓰기 작업은 파일의 현재 끝에서 시작됩니다. 쓰기 작업 후 파일 포인터는 실제로 쓴 바이트 수만큼 증가됩니다.  
  
 텍스트 모드에서 연 파일에 쓰는 경우 `_write`는 Ctrl+Z 문자를 논리적 파일 끝(EOF)으로 처리합니다. 장치에 쓰는 경우 `_write`는 버퍼의 Ctrl+Z 문자를 출력 종결자로 처리합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|루틴에서 반환된 값|필수 헤더|  
|-------------|---------------------|  
|`_write`|\<io.h>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## <a name="example"></a>예  
  
```  
// crt__write.c  
//   
// This program opens a file for output and uses _write to write  
// some bytes to the file.  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <errno.h>  
#include <share.h>  
  
char buffer[] = "This is a test of '_write' function";  
  
int main( void )  
{  
   int         fileHandle = 0;  
   unsigned    bytesWritten = 0;  
  
   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,  
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )  
      return -1;  
  
   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )  
   {  
      switch(errno)  
      {  
         case EBADF:  
            perror("Bad file descriptor!");  
            break;  
         case ENOSPC:  
            perror("No space left on device!");  
            break;  
         case EINVAL:  
            perror("Invalid parameter: buffer was NULL!");  
            break;  
         default:  
            // An unrelated error occured   
            perror("Unexpected error!");  
      }  
   }  
   else  
   {  
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );  
   }  
   _close( fileHandle );  
}  
```  
  
```Output  
Wrote 36 bytes to file.  
```  
  
## <a name="see-also"></a>참고 항목  
 [하위 수준 I/O](../../c-runtime-library/low-level-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)