---
title: "tmpfile | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tmpfile"
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
  - "tmpfile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "임시 파일"
  - "tmpfile 함수"
  - "임시 파일, 만들기"
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임시 파일을 만듭니다.  더 안전한 버전을 사용할 수 있기 때문에 이 함수는 더 이상 사용되지 않습니다. [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)를 참조하십시오.  
  
## 구문  
  
```  
FILE *tmpfile( void );  
```  
  
## 반환 값  
 성공 하면, `tmpfile` 은 스트림 포인터를 반환합니다.  그렇지 않으면, `NULL` 포인터를 반환합니다.  
  
## 설명  
 `tmpfile` 함수는 임시파일을 만들고 해당 스트림에 대한 포인터를 반환합니다.  루트 디렉터리에 임시 파일이 만들어집니다.  루트 디렉터리에 임시 파일을 만들려면 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)과 함께 [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) 또는 [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)를 사용합니다.  
  
 파일을 열 수 없는 경우, `tmpfile` 은 `NULL` 포인터를 반환합니다.  현재 작업 디렉터리가 변경되지 않았다는 가정 하에 이 임시 파일은 파일이 닫힐 때, 프로그램이 정상적으로 종료될 때, 혹은 `_rmtmp`이 호출되었을 때 자동적으로 삭제됩니다.  임시 파일은 `w+b`\(이진 읽기\/쓰기\) 모드에서 열립니다.  
  
 만약 `tmpfile` 을 사용하여 TMP\_MAX\(STDIO.H를 참고\) 보다 많은 호출을 시도한다면, 오류가 발생할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`tmpfile`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
> [!NOTE]
>  이 예제에서는 Windows Vista를 실행하기 위한 관리자 권한이 필요합니다.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
  **Temporary file 1 was created**  
**Temporary file 2 was created**  
**Temporary file 3 was created**  
**3 temporary files deleted**   
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [\_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)