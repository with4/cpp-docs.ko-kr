---
title: "LoadLibrary 및 AfxLoadLibrary | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LoadLibrary
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7de79303e414691df7b069b55b82b2ba39f6ea1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="loadlibrary-and-afxloadlibrary"></a>LoadLibrary 및 AfxLoadLibrary
호출 처리 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) (또는 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary))를 명시적으로 DLL에 연결 합니다. 명시적 링크에 다른 함수와 함께 사용할 수 있는 DLL에 대 한 핸들을 반환를 호출 하는 프로세스의 주소 공간에 지정된 된 DLL을 매핑하고 함수가 성공 하면-예를 들어 `GetProcAddress` 및 `FreeLibrary`합니다.  
  
 `LoadLibrary`암시적 링크에 사용 되는 동일한 검색 시퀀스를 사용 하 여 DLL을 찾으려고 시도 합니다. 시스템 DLL을 찾을 수 없는 경우 또는 진입점 함수가 FALSE를 반환 하는 경우 `LoadLibrary` NULL을 반환 합니다. 경우에 대 한 호출 `LoadLibrary` DLL 모듈을 호출 하는 프로세스의 주소 공간에 이미 매핑된 지정 함수는 모듈의 참조 횟수 DLL과 증가의 핸들을 반환 합니다.  
  
 운영 체제 호출 하는 스레드의 컨텍스트에 있는 함수를 호출 DLL 진입점 함수가 있으면 `LoadLibrary`합니다. 이전 호출으로 인해 프로세스에 DLL가 이미 연결 하는 경우에 진입점 함수가 호출 되지 않습니다 `LoadLibrary` 에 대 한 호출이 해당 변수가 있는 `FreeLibrary` 함수입니다.  
  
 MFC 확장 Dll을 로드 하는 MFC 응용 프로그램을 사용 하는 권장 `AfxLoadLibrary` 대신 `LoadLibrary`합니다. `AfxLoadLibrary`호출 하기 전에 스레드 동기화를 처리 `LoadLibrary`합니다. 인터페이스 (함수 프로토타입)를 `AfxLoadLibrary` 동일 `LoadLibrary`합니다.  
  
 Windows에서 DLL을 로드할 수 없는 경우 프로세스 오류 로부터 복구 연결할 수 있습니다. 예를 들어 프로세스 오류의 사용자에 게 알리는 및 DLL에 다른 경로 지정 하려면 사용자에 게 수 없습니다.  
  
> [!IMPORTANT]
>  Windows NT 4, Windows 2000 또는 SP1) (이전의 Windows XP에서 실행 되도록 코드 인 경우에 모든 Dll의 전체 경로 지정 해야 합니다. 이러한 운영 체제 파일을 로드할 때 현재 디렉터리를 먼저 검색 합니다. 파일의 경로 지정 하지 않으면 원하지 않는 파일을 로드할 수 있습니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [암시적으로 DLL에 연결 하는 방법](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [사용할 연결 방법을 결정 합니다.](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [Windows에서 DLL을 찾기 위해 사용 되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual c + +의 Dll](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../mfc/reference/application-information-and-management.md#afxloadlibrary)