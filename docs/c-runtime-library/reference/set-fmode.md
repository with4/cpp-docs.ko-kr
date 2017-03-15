---
title: "_set_fmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_fmode"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_fmode"
  - "set_fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_fmode 함수"
  - "파일 변환[C++], 기본 모드"
  - "파일 변환[C++], 모드 설정"
  - "set_fmode 함수"
ms.assetid: f80eb9c7-733b-4652-a9bc-6b3790a35f12
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _set_fmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 I\/O 작업에 대한 기본 파일 변환 모드를 설정합니다.  
  
## 구문  
  
```  
errno_t _set_fmode(   
   int mode   
);  
```  
  
#### 매개 변수  
 \[in\] `mode`  
 원하는 파일 변환 모드: `_O_TEXT` 또는 `_O_BINARY`.  
  
## 반환 값  
 성공 시 0을 반환합니다, 실패 시 오류 코드를 반환합니다.  만일 `mode` 이 `_O_TEXT` 또는 `_O_BINARY` 또는 `_O_WTEXT` 이 아닌 경우, 잘못된 매개변수 처리기는 호출됩니다, 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 으로 설명됩니다.  만일  
  
## 설명  
 함수는 [\_fmode](../../c-runtime-library/fmode.md) 전역 변수를 설정합니다.  이러한 변수는 파일 I\/O 작업인 `_open` 와 `_pipe` 에 대한 기본 파일 좌표이동 모드를 지정합니다.  
  
 `_O_TEXT` 및 `_O_BINARY` 은 Fcntl.h 정의되어 있습니다.  `EINVAL` 은 Errno.h에 정의 됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_set_fmode`|\<stdlib.h\>|\<fcntl.h\>, \<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_set_fmode.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <fcntl.h>     /* for _O_TEXT and _O_BINARY */  
#include <errno.h>     /* for EINVAL */  
#include <sys\stat.h>  /* for _S_IWRITE */  
#include <share.h>     /* for _SH_DENYNO */  
  
int main()  
{  
   int mode, fd, ret;  
   errno_t err;  
   int buf[12] = { 65, 66, 67, 68, 69, 70, 71, 72, 73, 74,  
                   75, 76 };  
   char * filename = "fmode.out";  
  
   err = _get_fmode(&mode);  
   if (err == EINVAL)  
   {  
      printf( "Invalid parameter: mode\n");  
      return 1;  
   }  
   else  
      printf( "Default Mode is %s\n", mode == _O_TEXT ? "text" :  
              "binary");  
  
   err = _set_fmode(_O_BINARY);  
   if (err == EINVAL)  
   {  
      printf( "Invalid mode.\n");  
      return 1;  
   }  
  
   if ( _sopen_s(&fd, filename, _O_RDWR | _O_CREAT, _SH_DENYNO, _S_IWRITE | _S_IREAD) != 0 )  
   {  
      printf( "Error opening the file %s\n", filename);  
      return 1;  
   }  
  
   if (ret = _write(fd, buf, 12*sizeof(int)) < 12*sizeof(int))  
   {  
      printf( "Problem writing to the file %s.\n", filename);  
      printf( "Number of bytes written: %d\n", ret);  
   }  
  
   if (_close(fd) != 0)  
   {  
      printf("Error closing the file %s. Error code %d.\n",  
             filename, errno);  
   }  
  
   system("type fmode.out");  
}  
```  
  
  **기본 모드는 이진법입니다.**  
**A B C D E F G H I J K L**    
## 참고 항목  
 [\_fmode](../../c-runtime-library/fmode.md)   
 [\_get\_fmode](../../c-runtime-library/reference/get-fmode.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [텍스트 및 이진 모드 파일 I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)