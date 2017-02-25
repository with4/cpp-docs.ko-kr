---
title: "malloc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "malloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "malloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "malloc 함수"
  - "메모리 할당"
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 블록을 할당합니다.  
  
## 구문  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### 매개 변수  
 `size`  
 할당할 바이트입니다.  
  
## 반환 값  
 `malloc`은 할당 된 공간에 대한 void 포인터 반환하거나 사용 가능한 메모리가 부족한 경우에는 `NULL` 포인터를 반환합니다.  `void`가 아닌 형식에 포인터를 반환하려면 반환 값에 대한 형식 캐스트를 사용합니다.  반환 값이 가리키는 저장소 공간은 기본 맞춤보다 적거나 같은 맞춤 요구 사항이 있는 개체 형식의 저장소에 대해 적절히 맞춤됩니다. \(Visual C\+\+에서 기본 맞춤은 `double` 또는 8바이트에 필요한 맞춤입니다.  64비트 플랫폼을 대상으로 하는 코드에서 16바이트입니다.\) 큰 맞춤 요구 사항이 있는 개체에 저장소를 할당하려면 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)을 사용합니다\(예: SSE 형식 [\_\_m128](../../cpp/m128.md) 및 `__m256` 그리고 `__declspec(align(``n``))`을 사용하여 선언된 형식. 여기서 `n`은 8보다 큼\).  `size`이 0인 경우 `malloc`는 힙에서 길이가 0인 항목을 할당하고 유효한 포인터를 해당 항목에 반환합니다.  요청된 메모리 양이 적더라도 `malloc`에서 반드시 반환을 확인합니다.  
  
## 설명  
 `malloc` 함수는 최소한 메모리 블록을 `size` 바이트 할당합니다.  블록은 맞춤 및 유지 관리 정보에 필요한 공간으로 인해 `size` 바이트보다 클 수 있습니다.  
  
 `malloc`는 메모리 할당이 실패하거나 요청한 메모리 크기가 `_HEAP_MAXREQ`를 초과하는 경우 `errno`는 `ENOMEM`로 설정됩니다.  이 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 `_environ`，　`envp`，　`argv` 변수에　대한　저장소를　할당하려면　시작코드에　`malloc`를　사용합니다．  다음 함수와 와이드 문자 상응부도 `malloc`을 호출합니다.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[\_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[\_exec 함수](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[\_popen](../../c-runtime-library/reference/popen-wpopen.md)|[\_spawn 함수](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[\_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[\_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[시스템](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[\_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[\_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[\_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[\_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[가져오기](../../c-runtime-library/gets-getws.md)|[\_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 C\+\+ [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) 함수는 `malloc`에 대한 새 처리기를 설정합니다.  새 처리기 모드는 실패 시 `malloc`이 [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출하는지 여부를 나타냅니다.  기본적으로 `malloc`은 메모리 할당에 실패한 경우 새 처리기 루틴을 호출하지 않습니다.  `malloc`이 메모리 할당에 실패하면 `malloc`이 새 처리기 루틴을 `new` 연산자가 같은 이유로 실패할 때와 동일한 방식으로 호출할 수 있도록 기본 동작을 재정의할 수 있습니다.  기본값을 재정의하려면 다음을 호출합니다.  
  
```cpp  
_set_new_mode(1)  
```  
  
 초기 프로그램 또는 NEWMODE.OBJ에 대한 링크\([링크 옵션](../../c-runtime-library/link-options.md) 참조\).  
  
 응용 프로그램이 C 런타임 라이브러리의 디버그 버전에 연결되면 `malloc`은 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)가 됩니다.  디버깅 프로세스 동안 힙을 관리하는 방법에 대한 자세한 내용은 [CRT 디버그 힙 정보](../Topic/CRT%20Debug%20Heap%20Details.md)를 참조하십시오.  
  
 `malloc`는 `__declspec(noalias)` 및 `__declspec(restrict)`로 표시됩니다. 즉, 함수가 전역 변수를 수정하지 않고 반환된 포인터가 별칭이 지정되지 않도록 보증합니다.  자세한 내용은 [noalias](../../cpp/noalias.md) 및 [restrict](../../cpp/restrict.md)를 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`malloc`|\<stdlib.h\> 및 \<malloc.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```c  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
  **경로 이름에 할당된 메모리 공간**  
**메모리 해제**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)을 참조하십시오.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)