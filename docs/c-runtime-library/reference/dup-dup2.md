---
title: "_dup, _dup2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dup"
  - "_dup2"
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
  - "_dup2"
  - "_dup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_dup 함수"
  - "_dup2 함수"
  - "dup 함수"
  - "dup2 함수"
  - "파일 핸들[C++], 중복"
  - "파일 핸들[C++], 다시 할당"
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _dup, _dup2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

열려 있는 파일 \(`_dup`\) 에 대한 두 번째 파일 설명자를 만들거나 파일 설명자 \(`_dup2`\) 를 다시 할당합니다.  
  
## 구문  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### 매개 변수  
 `fd`, `fd1`  
 열려 있는 파일을 나타내는 파일 설명자입니다.  
  
 `fd2`  
 모든 파일 설명자입니다.  
  
## 반환 값  
 `_dup` 는 새 파일 설명자를 반환합니다.  `_dup2` 성공을 나타내는 0을 반환 합니다.  만약 에러가 발생하면 각 함수는 \-1을 반환하고, 파일 설명자가 유효하면 `errno` 를 `EBADF` 로 설정하고 더 이상 파일 설명자를 사용 할 수 없는 경우에는 `EMFILE` 로 설정합니다.  잘못된 파일 설명자의 경우, 함수는 또한 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 잘못된 매개 변수 핸들러를 호출합니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `_dup` 와 `_dup2` 함수는 두번째 파일 설명자를 현재 열려 있는 파일과 연결합니다.  이러함 함수는 `stdout`와 같은 미리 정의된 파일 설명자와 다른 파일을 연결할 수 있습니다.  파일 설명자 중 하나를 사용하여 파일 작업을 수행할 수 있습니다.  파일에 허용된 엑세스 형식은 새 설명자의 생성에 영향을 받지 않습니다.  `_dup` 은 지정된 파일에 대해 다음으로 사용가능한 파일 설명자를 반환합니다.  `_dup2` 는 강제적으로 `fd2` 에게 `fd1` 와 같은 동일한 파일을 참조 하도록 합니다.  만약 `fd2` 가 호출이 발생 했을때 열려있는 파일과 연결되어 있다면, 해당 파일은 닫힙니다.  
  
 `_dup` 와 `_dup2` 둘다 매개 변수로 파일 생성자를 받습니다.  이러한 함수 중 하나에 스트림 `(FILE *)` 을 전달하려면, [\_fileno](../../c-runtime-library/reference/fileno.md) 을 사용하십시오.   `fileno` 루틴은 지정된 스트림과 연결된 파일 설명자를 반환합니다.  다음 예제에서는 `stderr` \(Stdio.h에서 `FILE` `*` 로 정의된\) 을 파일 생성자와 연결하는 방법을 보여줍니다.  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_dup`|\<io.h\>|  
|`_dup2`|\<io.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
  **This goes to stdout first**  
**This goes to stdout**  
**The file 'data' contains:**  
**This goes to file 'data'**   
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)