---
title: "fseek, _fseeki64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fseeki64"
  - "fseek"
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
  - "fseek"
  - "_fseeki64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fseeki64 함수"
  - "파일 포인터[C++]"
  - "파일 포인터[C++], 이동"
  - "fseek 함수"
  - "fseeki64 함수"
  - "파일 찾기 포인터"
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# fseek, _fseeki64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정된 된 위치에 파일 포인터를 이동합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
 `offset`  
 `origin` 에서의 바이트의 수  
  
 `origin`  
 초기 위치입니다.  
  
## 반환 값  
 성공적인 `fseek` 와 `_fseeki64` 는 0을 반환합니다.  그렇지 않으면 0이 아닌 값을 반환 합니다.  장치 검색을 할 수 없는 것에 대하여, 반환 값은 정의되지 않습니다.  만일 `stream` 가 null 포인터인 경우, 또는 만일 `origin` 이 아래 허용 되는 값 중 하나가 아닌 경우, `fseek` 및 `_fseeki64` 는 잘못된 매개변수 처리기를 호출합니다. 이는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명되어 있습니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL` 로 설정하고 \-1을 반환합니다.  
  
## 설명  
 이 `fseek` 와 `_fseeki64` 함수는 파일 포인터를 이동시킵니다. \(만일 모든\) 이 파일 포인터는 `stream` 과 연관되어 있습니다. 이는 새로운 위치인 `offset` 바이트인 `origin`로 부터입니다. 다음 작업은 스트림에서 새 위치에 이루어집니다.  스트림에 업데이트에 대한 열기, 읽기 또는 쓰기 다음 작업을 할 수 있습니다.  원점 인수는 STDIO.H에 정의된 다음 상수들 중 하나여야 합니다.  
  
 `SEEK_CUR`  
 파일 포인터의 현재 위치.  
  
 `SEEK_END`  
 파일의 끝입니다.  
  
 `SEEK_SET`  
 파일의 시작 부분.  
  
 파일에서 포인터를 어디든지 위치변경 하기 위해 `fseek` 와 `_fseeki64` 를 사용할 수 있습니다.  포인터가 파일의 끝을 넘어도 배치할 수 있습니다.  `fseek` 및 `_fseeki64`는 파일 끝 표시기를 명백히 하고, `stream` 에 대한 모든 사전의 `ungetc` 호출 영향을 무효화힙니다.  
  
 데이터 추가에 대해 파일을 열때, 현재 파일 위치는 다음 쓰기가 발생할 때가 아닌 마지막 I\/O 작업으로 결정됩니다.  파일이 추가용으로 열리기 전에 I\/O 작업이 없는 경우, 파일 위치는 파일의 시작이 됩니다.  
  
 텍스트 모드에서 연 스트림에 대한 `fseek` 및 `_fseeki64`는 사용이 제한되어 왔습니다, 왜냐하면 캐리지\-라인피드 좌표이동은 `fseek` 를 야기시키고 `_fseeki64`를 예기치 않은 결과가 발생할 수 있는 것을 야기시킬 수 있습니다.  텍스트 모드에서 열수있는 스트림을 작업하는것을 보장하는 유일한 `fseek` 와 `_fseeki64` 작업은 존재합니다.  
  
-   원본 값을 기준으로 0의 오프셋을 검색 합니다.  
  
-   오프셋 값으로 파일의 시작을 찾는 것은 `ftell` 에 대한 호출을 반환합니다. `fseek`또는 `_ftelli64`을 사용할 경우,`_fseeki64`을 사용할 경우입니다.  
  
 또한, 텍스트 모드에서, CTRL \+ Z는 입력에서의 파일의 마지막 특성으로 해석됩니다.  파일이 읽기\/쓰기 용으로 열린 경우, `fopen` 와 관련된 루틴은 파일의 끝에서 CTRL\+Z 에 대해 확인하고 가능하면 제거합니다.  완료됬습니다. 이는 `fseek` 와 `ftell` 또는`_fseeki64` 및 `_ftelli64` 의 결합을 사용하기 때문입니다. CTRL\+Z로 끝나는 파일을 이동시키기는 것은 `fseek` 또는 `_fseeki64` 가 적절하지 않은 파일의 끝에서 작업하는 것을 야기시킵니다.  
  
 CRT가 바이트 순서 마크\(BOM\)으로 시작하는 파일을 열 경우, 파일 포인터는 BOM 후\(즉, 파일의 실제 내용이 시작될 때,\)에 위치됩니다.  만일 `fseek`를 파일이 시작할 때 가질 경우, `ftell` 를 처음 위치를 얻기 위해 이용하고, 위치가 0이라기보다 `fseek` 일 경우를 사용합니다.  
  
 실행중에 이러한 함수는 다른 스레드를 잠그고 그러므로 스레드로부터 안전하게 됩니다.  비잠금 버전을 위해 [\_fseek\_nolock, \_fseeki64\_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)을 참조하세요.  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fseek`|\<stdio.h\>|  
|`_fseeki64`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
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
  
  **파일 포인터는 첫 줄의 중간에 설정 됩니다.**  
**'Fseek.out' 파일입니다.**   
## 해당 .NET Framework 항목  
  
-   [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
-   [System::IO::FileStream::Seek](https://msdn.microsoft.com/en-us/library/system.io.filestream.seek.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, \_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [\_lseek, \_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)