---
title: "tmpfile_s | Microsoft Docs"
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
  - "tmpfile_s"
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
  - "tmpfile_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "임시 파일"
  - "tmpfile_s 함수"
  - "임시 파일, 만들기"
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

임시 파일을 만듭니다.  [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 보안 향상 기능이 포함된 [tmpfile](../../c-runtime-library/reference/tmpfile.md) 버전입니다.  
  
## 구문  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### 매개 변수  
 \[out\] `pFilePtr`  
 스트림을 가리키는 생성된 포인터의 주소를 저장하는 포인터의 주소입니다.  
  
## 반환 값  
 성공 시 0을 반환하고, 실패 시 오류 코드입니다.  
  
### 오류 조건  
  
|`pFilePtr`|**반환 값**|`pFilePtr`의 **내용**입니다.|  
|----------------|--------------|----------------------------|  
|`NULL`|`EINVAL`|변경 되지 않음|  
  
 위의 매개 변수 검증 오류가 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno`를 `EINVAL`로 설정하고 \-`EINVAL`을 반환합니다.  
  
## 설명  
 `tmpfile_s` 함수는 임시 파일을 생성하고 `pFilePtr` 인수의 스트림을 가리키는 포인터를 넣습니다.  루트 디렉터리에 임시 파일이 만들어집니다.  루트 디렉터리에 임시 파일을 만들려면 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)과 함께 [tmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) 또는 [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)를 사용합니다.  
  
 파일을 열 수 없는 경우, `tmpfile_s`는 `pFilePtr` 매개 변수에 `NULL`를 기록합니다.  현재 작업 디렉터리가 변경되지 않았다는 가정 하에 이 임시 파일은 파일이 닫힐 때, 프로그램이 정상적으로 종료될 때, 혹은 `_rmtmp`이 호출되었을 때 자동적으로 삭제됩니다.  임시 파일은 `w+b`\(이진 읽기\/쓰기\) 모드에서 열립니다.  
  
 만약 `tmpfile_s.`를 호출하여 `TMP_MAX_S`\(STDIO.H를 참조\)보다 더 시도하는 경우, 오류가 발생할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`tmpfile_s`|\<stdio.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 예제  
  
> [!NOTE]
>  이 예제에서는 Windows Vista를 실행하기 위한 관리자 권한이 필요합니다.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
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