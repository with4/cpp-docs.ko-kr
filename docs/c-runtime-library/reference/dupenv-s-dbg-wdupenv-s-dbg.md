---
title: "_dupenv_s_dbg, _wdupenv_s_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_tdupenv_s_dbg"
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tdupenv_s_dbg 함수"
  - "dupenv_s_dbg 함수"
  - "_wdupenv_s_dbg 함수"
  - "환경 변수"
  - "tdupenv_s_dbg 함수"
  - "wdupenv_s_dbg 함수"
  - "_dupenv_s_dbg 함수"
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _dupenv_s_dbg, _wdupenv_s_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

현재 환경에서 값을 가져옵니다.  [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)으로 메모리를 할당하는 [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md) 버전은 메모리를 할당하는  추가 디버깅 정보를 제공합니다.  
  
## 구문  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### 매개 변수  
 `buffer`  
 변수의 값을 저장하는 버퍼입니다.  
  
 `numberOfElements`  
 이 `buffer`의 크기.  
  
 `varname`  
 환경 변수명  
  
 `blockType`  
 메모리 블록의 형식을 요청합니다.  `_CLIENT_BLOCK`  또는  `_NORMAL_BLOCK` .  
  
 `filename`  
 소스 파일의 이름에 대한 포인터 또는  `NULL` .  
  
 `linenumber`  
 소스 파일의 줄 번호 또는  `NULL` .  
  
## 반환 값  
 성공 시 0이고, 실패 시 오류 코드입니다.  
  
 이 `buffer` 혹은 `varname` 은 `NULL` 인 경우, 잘못된 매개 변수 처리기는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 로 설명되어 호출되고, 이러한 함수는 매개 변수를 유효하게 합니다.  계속해서 실행하도록 허용된 경우, 이 함수는 `errno` 를 `EINVAL` 로 설정하고 `EINVAL`을 반환합니다.  
  
 이러한 함수는 충분한 메모리를 할당할 수 없는 경우, 이들은 `buffer` 을 `NULL` 으로 설정하고 `numberOfElements` 을 0으로, `ENOMEM` 을 반환합니다.  
  
## 설명  
 `_dupenv_s_dbg`  및  `_wdupenv_s_dbg`  함수는  `_dupenv_s`  및  `_wdupenv_s`  와 동일합니다.  `_DEBUG` 가 정의되었을 때, 이러한 함수는  [malloc](../../c-runtime-library/reference/malloc.md), [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)의 디버그 버전을 사용하여 환경 변수 값에 대 한 메모리를 할당합니다.   `_malloc_dbg` 의 디버깅 기능에 대한 내용은 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)를 참조하십시오.  
  
 대부분의 경우에서 이러한 함수를 명시적으로 호출할 필요가 없습니다.  대신,  `_CRTDBG_MAP_ALLOC`  플래그를 정의할 수 있습니다.   `_CRTDBG_MAP_ALLOC` 가 정의되었을 때,  `_dupenv_s` 을 호출하고,  `_wdupenv_s` 는  `blockType` 을  `_NORMAL_BLOCK` 로 설정하여  `_dupenv_s_dbg`  및  `_wdupenv_s_dbg`  각각에 다시 맵핑됩니다.  따라서,  `_CLIENT_BLOCK` 같이 힙 블록으로 표시 하지 않는 이상 이러한 함수를 명시적으로 호출할 필요가 없습니다 .  블록 형식에 대한 자세한 내용은 [디버그 힙의 블록 형식](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)을 참조 하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_dupenv_s_dbg`|\<crtdbg.h\>|  
|`_wdupenv_s_dbg`|\<crtdbg.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## 샘플 출력  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## 해당 .NET Framework 항목  
 [System.Environment::GetEnvironmentVariables](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [환경 상수](../../c-runtime-library/environmental-constants.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)