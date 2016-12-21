---
title: "fgets, fgetws | Microsoft Docs"
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
  - "fgets"
  - "fgetws"
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
  - "_fgetts"
  - "fgetws"
  - "fgets"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fgetts 함수"
  - "fgets 함수"
  - "fgetts 함수"
  - "fgetws 함수"
  - "스트림, 문자열 가져오기"
  - "스트림, 읽기"
ms.assetid: ad549bb5-df98-4ccd-a53f-95114e60c4fc
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fgets, fgetws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스트림에서 문자열을 가져옵니다.  
  
## 구문  
  
```  
char *fgets(   
   char *str,  
   int n,  
   FILE *stream   
);  
wchar_t *fgetws(   
   wchar_t *str,  
   int n,  
   FILE *stream   
);  
```  
  
#### 매개 변수  
 `str`  
 출력을 위한 저장소 위치  
  
 `n`  
 읽을 문자의 최대 수입니다.  
  
 `stream`  
 `FILE` 구조체에 대한 포인터입니다.  
  
## 반환 값  
 이러한 각 함수를 `str` 를 반환합니다.  `NULL` 은 파일의 끝 조건이나 오류를 가리키기 위해 반환됩니다.  오류 발생여부를 확인하기 위해 `feof` 또는 `ferror` 을 사용합니다.  만일 `str` 또는 `stream` 이 null 포인터이거나 `n` 이 0과 같거나 더 적은 경우, 이함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된대로 잘못된 매개변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `NULL`을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `fgets` 함수는 입력 `stream` 매개변수로부터 문자열을 읽고 `str` 에 이것을 저장합니다.  `fgets` 는 첫번째 줄 바뀜 문자를 포함하는 현재 스트림의 위치로부터 문자들 또는 스트림의 끝이나 `n` \- 1와 동등하게 읽혀지는 문자의 숫자까지를 읽습니다.  `str` 에 저장된 결과는 null 문자를 사용하여 추가됩니다.  읽는 경우, 줄바뀜 문자는 문자열에 포함됩니다.  
  
 `fgetws` 는 `fgets` 의 와이드 문자 버전입니다.  
  
 `fgetws` 는 와이드 문자 인수 `str` 를 텍스트나 이진 모드로 `stream` 가 열리는지 여부에 따라 와이드 문자열이나 멀티바이트 문자열로써 읽습니다.  텍스트 및 유니코드 이진 모드와 멀티 바이트 스트림 I\/O 사용에 대 한 자세한 내용은 [텍스트 및 이진 모드 파일 I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [텍스트 및 이진 모드에서 유니코드 스트림 I\/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_fgetts`|`fgets`|`fgets`|`fgetws`|  
  
## 요구 사항  
  
|Function|필수 헤더|  
|--------------|-----------|  
|`fgets`|\<stdio.h\>|  
|`fgetws`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
```  
// crt_fgets.c  
// This program uses fgets to display  
// a line from a file on the screen.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[100];  
  
   if( fopen_s( &stream, "crt_fgets.txt", "r" ) == 0 )  
   {  
      if( fgets( line, 100, stream ) == NULL)  
         printf( "fgets error\n" );  
      else  
         printf( "%s", line);  
      fclose( stream );  
   }  
}  
```  
  
## Input: crt\_fgets.txt  
  
```  
Line one.  
Line two.  
```  
  
### Output  
  
```  
Line one.  
```  
  
## 해당 .NET Framework 항목  
  
-   [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx).  
  
-   [System::IO::TextReader::ReadBlock](https://msdn.microsoft.com/en-us/library/system.io.textreader.readblock.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)