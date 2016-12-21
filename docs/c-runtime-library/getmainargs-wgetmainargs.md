---
title: "__getmainargs, __wgetmainargs | Microsoft Docs"
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
  - "__wgetmainargs"
  - "__getmainargs"
apilocation: 
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __getmainargs, __wgetmainargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명령줄 분석을 호출하고 전달된 포인터를 통해 다시 `main()` 에 대한 인수를 복사합니다.  
  
## 구문  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### 매개 변수  
 `_Argc`  
 `argv` 를 따르는 인수의 수가 포함하는 정수입니다.  `argc` 매개 변수는 항상 1보다 크거나 같습니다.  
  
 `_Argv`  
 프로그램의 사용자가 입력한 명령줄 인수를 나타내는 null로 끝나는 문자열의 배열입니다.  규칙에 따라, `argv[0]` 는 프로그램을 호출하는 것을 명령합니다, argb\[1\]은 첫번째 명령줄 인수이고, argv\[argc\]는 항상 null 값입니다.   첫 번째 명령줄 인수는 항상 `argv[1]` 이고, 마지막은 `argv[argc – 1]` 입니다.  
  
 `_Env`  
 이는 사용자 환경에서 설정된 변수를 나타내는 문자열의 배열을 나타냅니다.  이 배열은 NULL 항목으로 종료됩니다.  
  
 `_DoWildCard`  
 정수는 명령줄 인수에서 와일드 카드를 확장하기 위해 1로 설정 하거나 0으로 설정 해도 됩니다.  
  
 `_StartInfo`  
 CRT DLL에 전달 될 수 있는 다른 정보입니다.  
  
## 반환 값  
 성공 하면 0, 실패하면 음수값.  
  
## 설명  
 와이드 문자가 아닌 플랫폼인 `__getmainargs` 와 와이트 문자 플랫폼인\(유니코드\) `__wgetmainargs` 를 사용합니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_getmainargs|internal.h|  
|\_\_wgetmainargs|internal.h|