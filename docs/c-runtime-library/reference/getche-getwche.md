---
title: "_getche, _getwche | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getwche"
  - "_getche"
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
  - "getwche"
  - "_getche"
  - "_getwche"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getche 함수"
  - "_getwche 함수"
  - "문자, 콘솔에서 가져오기"
  - "콘솔, 읽기"
  - "getche 함수"
  - "getwche 함수"
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _getche, _getwche
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

에코와 함께 콘솔에서 문자를 가져옵니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
int _getche( void );  
wint_t _getwche( void );  
```  
  
## 반환 값  
 읽은 문자를 반환합니다.  반환되는 오류가 없습니다.  
  
## 설명  
 이 `_getche` 와 `_getwche` 함수는 의미 문자가 콘솔에 표시 되도록 화면 표시를 사용하여 콘솔에서 단일 문자를 읽습니다.  CTRL \+ C를 읽는 데 사용할 수 있는 함수가 없습니다.  화살표 키 또는 기능 키를 읽을 때, 각 함수; 두 번 호출 되어야 합니다.; 0 또는 0xE0를 첫 번째 호출에서 반환하고 실제 키 코드를 두 번째 호출에서 반환합니다.  
  
 이러한 함수는 호출 스레드를 잠그고, 그러므로 안전 스레드가 됩니다.  비잠금 버전은 다음 [\_getche\_nolock, \_getwche\_nolock](../../c-runtime-library/reference/getche-nolock-getwche-nolock.md)을 참조하십시오.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_getche`|`_getche`|`_getch`|`_getwche`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_getche`|\<conio.h\>|  
|`_getwche`|\<conio.h\> 또는 \<wchar.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
  
```  
// crt_getche.c  
// compile with: /c  
// This program reads characters from  
// the keyboard until it receives a 'Y' or 'y'.  
  
#include <conio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
  
   _cputs( "Type 'Y' when finished typing keys: " );  
   do  
   {  
      ch = _getche();  
      ch = toupper( ch );  
   } while( ch != 'Y' );  
  
   _putch( ch );  
   _putch( '\r' );    // Carriage return  
   _putch( '\n' );    // Line feed       
}  
```  
  
  **`abcdey`키 입력을 마쳤으면 'Y'를 입력: Y**   
## NET Framework 사용  
 해당 사항 없음.  표준 C 함수를 호출하려면 `PInvoke`를 사용합니다.  자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하십시오.  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cgets, \_cgetws](../../c-runtime-library/cgets-cgetws.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)