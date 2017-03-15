---
title: "wmain 사용 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "wWinMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "와이드 문자[C++], wmain 함수"
  - "wmain 함수"
  - "wWinMain 함수"
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# wmain 사용 지원
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 **wmain** 함수를 정의하고 와이드 문자 인수를 유니코드 응용 프로그램에 전달할 수 있습니다.  **main**과 유사한 형식을 사용하여 **wmain**에 정식 매개 변수를 선언합니다.  와이드 문자 인수 또는 와이드 문자 환경 포인터를 프로그램에 전달할 수 있습니다.  **wmain**에 대한 `argv` 및 `envp` 매개 변수는 `wchar_t*` 형식입니다.  예를 들면 다음과 같습니다.  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC 유니코드 응용 프로그램은 **wWinMain**을 진입점으로 사용합니다.  이 경우 `CWinApp::m_lpCmdLine`은 유니코드 문자열입니다.  [\/ENTRY](../build/reference/entry-entry-point-symbol.md) 링커 옵션을 사용하여 **wWinMainCRTStartup**을 설정합니다.  
  
 프로그램이 **main** 함수를 사용하면 프로그램을 시작할 때 런타임 라이브러리에 의해 멀티바이트 문자 환경이 만들어집니다.  이 환경의 와이드 문자 복사본은 필요한 경우\(예: `_wgetenv` 또는 `_wputenv` 함수를 호출하는 경우\)에만 만들어집니다.  `_wputenv`를 처음 호출할 때 또는 MBCS 환경이 이미 있는 경우에는 `_wgetenv`를 처음 호출할 때 해당 와이드 문자열 환경이 만들어집니다.  `_environ` 전역 변수의 와이드 문자 버전인 `_wenviron` 전역 변수가 해당 환경을 가리킵니다.  이 때 환경 복사본 두 개\(MBCS와 유니코드\)가 동시에 존재하며 프로그램의 수명 내내 런타임 시스템에 의해 유지됩니다.  
  
 마찬가지로 프로그램이 **wmain** 함수를 사용하면 프로그램이 시작될 때 와이드 문자 환경이 만들어지고 `_wenviron` 전역 변수가 해당 환경을 가리킵니다.  MBCS\(ASCII\) 환경은 `_putenv` 또는 `getenv`를 처음 호출할 때 만들어지고 `_environ` 전역 변수가 이 환경을 가리킵니다.  
  
## 참고 항목  
 [유니코드 지원](../text/support-for-unicode.md)   
 [유니코드 프로그래밍 요약](../text/unicode-programming-summary.md)   
 [WinMain Function](http://msdn.microsoft.com/library/windows/desktop/ms633559)