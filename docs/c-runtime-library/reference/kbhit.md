---
title: "kbhit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_kbhit"
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
  - "kbhit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "kbhit 함수"
ms.assetid: e82a1cc9-bbec-4150-b678-a7e433220fe4
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _kbhit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

콘솔 키보드 입력을 검사합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하십시오.  
  
## 구문  
  
```  
  
int _kbhit( void );  
```  
  
## 반환 값  
 `_kbhit` 는 키를 눌렀을 경우 0이 아닌 값을 반환 합니다.  그렇지 않으면 0이 반환됩니다.  
  
## 설명  
 다음 `_kbhit` 함수는 콘솔 최근의 키 입력을 확인 합니다.  함수에서 0이 아닌 값을 반환하는 경우, 키 입력은 버퍼에서 대기 중입니다.  프로그램은 `_getch` 또는 `_getche` 를 호출하여 키를 가져올 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_kbhit`|\<conio.h\>|  
  
 호환성 정보에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_kbhit.c  
// compile with: /c  
/* This program loops until the user  
 * presses a key. If _kbhit returns nonzero, a  
 * keystroke is waiting in the buffer. The program  
 * can call _getch or _getche to get the keystroke.  
 */  
  
#include <conio.h>  
#include <stdio.h>  
  
int main( void )  
{  
   /* Display message until key is pressed. */  
   while( !_kbhit() )  
      _cputs( "Hit me!! " );  
  
   /* Use _getch to throw key away. */  
   printf( "\nKey struck was '%c'\n", _getch() );  
}  
```  
  
## 샘플 출력  
  
```  
Hit me!! Hit me!! Hit me!! Hit me!! Hit me!! Hit me!! Hit me!!  
Key struck was 'q'   
```  
  
## 참고 항목  
 [콘솔 및 포트 I\/O](../../c-runtime-library/console-and-port-i-o.md)