---
title: "_creat, _wcreat | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_creat"
  - "_wcreat"
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
  - "wcreat"
  - "_wcreat"
  - "_creat"
  - "tcreat"
  - "_tcreat"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wcreat 함수"
  - "_wcreat 함수"
  - "파일[C++], 만들기"
  - "_creat 함수"
  - "tcreat 함수"
  - "creat 함수"
  - "_tcreat 함수"
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _creat, _wcreat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

새 파일을 만듭니다.  `_creat`및 `_wcreat` 는 사용 되지 않습니다. 대신[\_sopen\_s, \_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) 를 사용하십시오.  
  
## 구문  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### 매개 변수  
 `filename`  
 파일의 새 이름입니다.  
  
 `pmode`  
 권한 설정  
  
## 반환 값  
 이러한 함수는 성공 하면 생성된 파일에 대해 파일 설명자를 반환합니다.  그렇지 않으면 함수는\-1을 반환하고 다음 표에 나와 있는 것처럼 `errno` 를 설정합니다.  
  
|`errno` 설정|설명|  
|----------------|--------|  
|`EACCES`|`filename` 는 기존 읽기 전용 파일을 지정 하거나 파일 대신 디렉터리를 지정 합니다.|  
|`EMFILE`|사용가능한 자세한 파일 설명자가 없습니다.|  
|`ENOENT`|지정된 파일을 찾을 수 없습니다.|  
  
 `filename` 이 NULL 이면, 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 것 처럼 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_creat` 함수는 새 파일을 만들거나 또는 열고 기존 것을 자릅니다.  `_wcreat`는 `_creat`의 와이드 문자 버전이며, `_wcreat`의 `filename` 인수는 와이드 문자 문자열입니다.  `_wcreat` 및 `_creat` 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 `filename` 가 지정한 파일이 존재하지 않는 경우, 새로운 파일은 주어진 권한 설정으로 생성되고 쓰기용으로 열립니다.  파일이 이미 존재 하고 해당 권한 설정이 쓰기를 허용하는 경우, `_creat` 는 이전 컨텐츠를 제거하여 파일의 길이를 0으로 줄이고 쓰기용으로 엽니다.  `pmode` 권한 설정은 새로운 파일에만 적용 됩니다.  새 파일을 처음으로 닫힌 후 지정 된 사용 권한 설정을 받습니다.  정수 표현 `pmode` 은 하나 또는 둘 이상의 SYS\\Stat.h 에 정의된 매니페스트 상수`_S_IWRITE` 및 `_S_IREAD` 를 가집니다.  두 상수가 주어지면, 그들은 비트 `OR` 연산자와 결합됩니다.  **&#124;**\).  `pmode` 매개 변수는 다음 값 중 하나로 설정됩니다.  
  
|값|정의|  
|-------|--------|  
|`_S_IWRITE`|쓰기에 사용할 수 있습니다.|  
|`_S_IREAD`|읽기에 사용할 수 있습니다.|  
|`_S_IREAD &#124; _S_IWRITE`|읽기 및 쓰기에 사용할 수 있습니다.|  
  
 쓰기 권한이 없는 경우, 읽기 전용 파일입니다.  모든 파일을 읽을 수 있으면 항상 쓰기 전용 권한을 부여 하는 것이 불가능 합니다.  `_S_IWRITE` 및 `_S_IREAD``| _S_IWRITE` 모드는 동일합니다.  `_creat` 를 사용하여 열린 파일은 `_SH_DENYNO` 를 사용하여 항상 호환성 모드에서 열립니다. \([\_sopen](../../c-runtime-library/reference/sopen-wsopen.md) 를 참조하십시오\)  
  
 `_creat` 는 권한을 설정하기 전에 `pmode` 에 현재 파일 권한 마스크를 적용합니다. \( [\_umask](../../c-runtime-library/reference/umask.md) 를 참조하십시오.\)  `_creat` 는 이전 라이브러리와의 호환성을 위해 제공 됩니다.  `oflag` 매개 변수에서 `_O_CREAT` 및 `_O_TRUNC` 를 사용한 `_open`에 대한 호출은 `_creat` 와 동일하며 새로운 코드에 대해 선호됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_creat`|\<io.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wcreat`|\<io.h\> or \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
  **생성된 된 데이터 파일입니다.**   
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)