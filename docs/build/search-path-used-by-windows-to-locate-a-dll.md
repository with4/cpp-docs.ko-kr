---
title: "Windows에서 DLL을 찾기 위해 사용 되는 경로 검색 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53350ed473226c86dd4fefa93cff376a371dedf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>Windows에서 DLL을 찾는 데 사용되는 검색 경로
암시적 및 명시적 링크의 경우, 먼저 검색 "알려진된 Dll", 예: Kernel32.dll 및 User32.dll 됩니다. 그런 다음 다음 순서에 따라 Dll을 검색 합니다.  
  
1.  현재 프로세스에 대 한 실행 모듈 위치한 디렉터리입니다.  
  
2.  현재 디렉터리입니다.  
  
3.  Windows 시스템 디렉터리입니다. **GetSystemDirectory** 함수는이 디렉터리의 경로 검색 합니다.  
  
4.  Windows 디렉터리입니다. **GetWindowsDirectory** 함수는이 디렉터리의 경로 검색 합니다.  
  
5.  PATH 환경 변수에 나열 된 디렉터리입니다.  
  
    > [!NOTE]
    >  LIBPATH 환경 변수 사용 되지 않습니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [암시적으로 DLL에 연결 하는 방법](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [명시적으로 DLL에 연결 하는 방법](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [사용할 연결 방법을 결정 합니다.](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)