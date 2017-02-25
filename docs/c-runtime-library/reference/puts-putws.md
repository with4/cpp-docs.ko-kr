---
title: "puts, _putws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putws"
  - "puts"
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
  - "_putts"
  - "_putws"
  - "puts"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putts 함수"
  - "_putws 함수"
  - "puts 함수"
  - "putts 함수"
  - "putws 함수"
  - "표준 출력, 쓰기"
  - "문자열[C++], 작성"
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# puts, _putws
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**표준**문자열을 씁니다.  
  
## 구문  
  
```  
  
      int puts(  
   const char *str   
);  
int _putws(  
   const wchar_t *str   
);  
```  
  
#### 매개 변수  
 `str`  
 출력 문자열  
  
## 반환 값  
 성공 하면 음수가 아닌 값을 반환 합니다.  `puts` 가 실패할 경우, `EOF`를 반환합니다; `_putws` 가 실패할 경우, **WEOF**를 반환합니다.  `str` 이 null 포인터인 경우, 설명된 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `errno` 를 `EINVAL` 로 설정하고 `EOF` 또는 **WEOF**을 반환합니다.  
  
 이러한 오류 코드 및 기타 오류 코드에 대한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
## 설명  
 `puts` 쓰기 작동 `str` 표준 출력 스트림에 **stdout**, 출력 스트림에 줄 바꿈 문자 \('\\n'\)를 사용 하 여 null 문자 \('\\0'\) 종료의 문자열을 대체 합니다.  
  
 `_putws` 는 와이드 문자 버전인 `puts`입니다.; 마치 동일한 스트림에서 ANSI 모드에서 열리는 경우입니다.  `puts` 는 현재 UNICODE 스트림에 대한 출력을 지원하지 않습니다.  
  
 Windows 2000에서와 나중에 **\_putwch** 현재 콘솔 로케일 설정을 사용 하 여 유니코드 문자를 씁니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_putts`|`puts`|`puts`|`_putws`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`puts`|\<stdio.h\>|  
|`_putws`|\<stdio.h\>|  
  
 콘솔은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램에서 지원되지 않습니다.  콘솔에 연결된 표준 스트림 핸들 `stdin`, `stdout` 및 `stderr`은 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램의 C 런타임 함수에서 사용되기 전에 리디렉션되어야 합니다.  추가 호환성 정보는 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_puts.c  
/* This program uses puts to write a string to stdout.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   puts( "Hello world from puts!" );  
}  
```  
  
## Output  
  
```  
Hello world from puts!  
```  
  
## 해당 .NET Framework 항목  
 [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)