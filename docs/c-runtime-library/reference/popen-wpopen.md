---
title: "_popen, _wpopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_popen"
  - "_wpopen"
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
  - "tpopen"
  - "popen"
  - "wpopen"
  - "_popen"
  - "_wpopen"
  - "_tpopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_popen 함수"
  - "_tpopen 함수"
  - "_wpopen 함수"
  - "파이프, 만들기"
  - "popen 함수"
  - "tpopen 함수"
  - "wpopen 함수"
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _popen, _wpopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파이프를 생성하고 명령을 실행 합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
      FILE *_popen(  
const char *command,  
const char *mode   
);  
FILE *_wpopen(  
const wchar_t *command,  
const wchar_t *mode   
);  
```  
  
#### 매개 변수  
 *명령*  
 실행할 명령입니다.  
  
 *mode*  
 반환된 스트림의 모드입니다.  
  
## 반환 값  
 생성된 파이프의 한쪽 끝을 연결하는 스트림을 반환 합니다.  파이프의 다른 쪽 끝에는 생성된 명령이 표준 입력이나 표준 출력으로 연결 됩니다.  함수는 에러 상의 **NULL** 을 반환합니다.  잘못된 매개 변수의 오류의 경우, *command* 혹은 *mode* 가 null 포인터인 경우, 혹은 *mode* 가 잘못된 모드가 아닌 경우, `errno` 는 `EINVAL` 으로 설정합니다.  사용할 수 있는 모드에 대한 설명 부분을 참조 하십시오.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 이 `_popen` 함수는 지정된 *command* 문자열에 명령 프로세서의 복사본에 비동기적으로 실행하고 파이프를 생성합니다.  문자 문자열 *mode* 는 다음과 같이 요청된 액세스 형식을 지정 합니다.  
  
 **"r"**  
 호출 프로세스가 반환된 스트림을 사용하여 생성된 명령의 표준 출력을 읽을 수 있습니다.  
  
 **\/w**  
 호출 프로세스가 반환된 스트림을 사용하여 생성된 명령이 표준 입력에 쓸 수 있습니다.  
  
 **"b"**  
 이진 모드로 열려 있습니다.  
  
 **"t"**  
 텍스트 모드에서 엽니다.  
  
> [!NOTE]
>  윈도우 프로그램을 사용하는 경우, `_popen` 함수는 무한정 응답을 중지한 프로그램의 야기한 잘못된 파일 포인터를 반환합니다.  `_popen` 는 콘솔 응용 프로그램에서 제대로 작동합니다.  입력 및 출력을 리디렉션하는 Windows 응용 프로그램을 만들려면, [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] 에서 [리디렉션된 입력 및 출력 자식 프로세스를 만들기](http://msdn.microsoft.com/library/windows/desktop/ms682499) 를 보세요.  
  
 `_wpopen` 는 `_popen`의 와이드 문자 버전이며, `_wpopen` 의 *path* 인수는 와이드 문자 문자열입니다.  `_wpopen` 및 `_popen` 는 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_popen`|\<stdio.h\>|  
|`_wpopen`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## 샘플 출력  
 이 출력 .c 파일 이름 확장명을 사용하여 현재 디렉터리에 파일 하나만 있다고 가정 합니다.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## 해당 .NET Framework 항목  
 해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [프로세스 및 환경 제어](../../c-runtime-library/process-and-environment-control.md)   
 [\_pclose](../../c-runtime-library/reference/pclose.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)