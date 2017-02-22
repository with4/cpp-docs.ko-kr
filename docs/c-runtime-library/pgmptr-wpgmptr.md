---
title: "_pgmptr, _wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pgmptr"
  - "_pgmptr"
  - "wpgmptr"
  - "_wpgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pgmptr 함수"
  - "_wpgmptr 함수"
  - "pgmptr 함수"
  - "wpgmptr 함수"
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _pgmptr, _wpgmptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

실행 파일의 파일 경로입니다.  더 이상 사용되지 않습니다. [\_get\_pgmptr](../c-runtime-library/reference/get-pgmptr.md) 및 [\_get\_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md)를 사용합니다.  
  
## 구문  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## 설명  
 프로그램이 명령어 인터프리터 \(Cmd.exe\)에서 실행될 때, `_pgmptr`는 자동적으로 실행 파일의 전체 경로를 초기화합니다.  예를 들어, 만약 Hello.exe가 C:\\BIN에 존재하고 C:\\BIN가 패스에 존재한다면, `_pgmptr`가 C:\\BIN\\Hello.exe로 설정됩니다.  
  
```  
C> hello   
```  
  
 프로그램이 명령줄에서 실행되지 않는 경우, `_pgmptr`는 프로그램 이름\(파일 확장자를 제외한 파일의 기본 이름\) 또는 파일 이름, 상대 경로, 또는 전체 경로로 초기화될 수 있습니다.  
  
 `_wpgmptr`는 `wmain`를 사용하는 프로그램에 사용하기 위한 `_pgmptr`에 상응하는 와이드 문자입니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## 요구 사항  
  
|변수|필수 헤더|  
|--------|-----------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h\>|  
  
## 예제  
 다음 프로그램은 `_pgmptr`의 사용을 보여 줍니다.  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 `%Fs`를 `%S`로 변경하고 `main`를 `wmain`으로 변경하는 것을 통해 `_wpgmptr`를 이용할 수 있습니다.  
  
## 참고 항목  
 [전역 변수](../c-runtime-library/global-variables.md)