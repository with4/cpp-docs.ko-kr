---
title: "Wmain 사용 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: wWinMain
dev_langs: C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 721915ca5ebbc75b17771dae0804e94aa360177c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-using-wmain"></a>wmain 사용 지원
Visual c + +에서는 정의할 수는 **wmain** 함수 및 유니코드 응용 프로그램에 와이드 문자 인수를 전달 합니다. 형식 매개 변수를 선언 하면 **wmain**, 비슷한 형식으로 사용 하 여 **주**합니다. 와이드 문자 인수 또는 와이드 문자 환경 포인터를 프로그램에 전달할 수 있습니다. **wmain**에 대한 `argv` 및 `envp` 매개 변수는 `wchar_t*` 형식입니다. 예:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  유니코드 MFC 응용 프로그램에서 사용 하 여 **wWinMain** 진입점으로 합니다. 이 경우 `CWinApp::m_lpCmdLine` 는 유니코드 문자열입니다. 로 설정 해야 **wWinMainCRTStartup** 와 [/ENTRY](../build/reference/entry-entry-point-symbol.md) 링커 옵션입니다.  
  
 프로그램이 **main** 함수를 사용하면 프로그램을 시작할 때 런타임 라이브러리에 의해 멀티바이트 문자 환경이 만들어집니다. 이 환경의 와이드 문자 복사본은 필요한 경우(예: `_wgetenv` 또는 `_wputenv` 함수를 호출하는 경우)에만 만들어집니다. 첫 번째 호출에서 `_wputenv`, 첫 번째 호출 또는 `_wgetenv` 에서 MBCS 환경이 이미 있는 경우 해당 와이드 문자 문자열 환경이 만들어집니다. 환경에 의해 가리킵니다는 `_wenviron` 전역 변수의 와이드 문자 버전의 `_environ` 전역 변수입니다. 이 시점에서 환경 (MBCS 및 유니코드)의 두 복사본이 동시에 존재 하 고 프로그램의 수명 내내 런타임 시스템에서 유지 됩니다.  
  
 마찬가지로 프로그램이 **wmain** 함수를 사용하면 프로그램이 시작될 때 와이드 문자 환경이 만들어지고 `_wenviron` 전역 변수가 해당 환경을 가리킵니다. 첫 번째 호출에서 MBCS (ASCII) 환경을 만드는 `_putenv` 또는 `getenv` 2를 가리키고 및는 `_environ` 전역 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니코드 지원](../text/support-for-unicode.md)   
 [유니코드 프로그래밍 요약](../text/unicode-programming-summary.md)   
 [WinMain 함수](http://msdn.microsoft.com/library/windows/desktop/ms633559)