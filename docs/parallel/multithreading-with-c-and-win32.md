---
title: "C 및 Win32를 사용한 다중 스레딩 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30c7833a4df80669b6223f1fe6b1ccceed0257cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-with-c-and-win32"></a>C 및 Wind32를 사용한 다중 스레딩
Microsoft Visual c + +는 다중 스레드 응용 프로그램을 Microsoft Windows와 함께 만들기에 대 한 지원을 제공: Windows XP, Windows 2000, Windows NT, Windows Me, Windows 98입니다. 응용 프로그램에서 동시 키보드 및 마우스 입력 등의 여러 작업을 관리 하는 경우에 둘 이상의 스레드를 사용 하는 것이 좋습니다. 두 번째 스레드가 마우스 동작을 필터링 하는 동안 스레드를 하나씩 키보드 입력을 처리할 수 있습니다. 세 번째 스레드 마우스 및 키보드 스레드에서 데이터를 기반으로 화면 표시를 업데이트할 수 있습니다. 다른 스레드에서 같은 시간에 디스크 파일에 액세스 하거나 통신 포트에서 데이터를 가져올 수 있습니다.  
  
 Visual c + +는 다중 스레드를 가진 프로그램으로 두 가지가: Microsoft Foundation 클래스 (MFC) 라이브러리 또는 C 런타임 라이브러리와 Win32 API를 사용 합니다. MFC에 다중 스레드 응용 프로그램을 만드는 방법은 참조 [c + + 및 MFC 스레딩](../parallel/multithreading-with-cpp-and-mfc.md) C에서 다중 스레딩에 대 한 항목을 읽은 후  
  
 이 항목에서는 다중 스레드 프로그램 만들기를 지 원하는 Visual c + +에서 기능을 설명 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [어떤 다중 스레딩에 대 한는](../parallel/multithread-programs.md)  
  
-   [라이브러리 지원에 대 한 다중 스레딩](../parallel/library-support-for-multithreading.md)  
  
-   [Include 파일에서 다중 스레딩](../parallel/include-files-for-multithreading.md)  
  
-   [스레드 제어에 대 한 C 런타임 라이브러리 함수](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [C에서 샘플 다중 스레드 프로그램](../parallel/sample-multithread-c-program.md)  
  
-   [다중 스레드 Win32 프로그램 작성](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [컴파일 및 다중 스레드 프로그램 연결](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [다중 스레드 프로그램으로 문제 영역 방지](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [스레드 로컬 저장소 (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>참고 항목  
 [이전 코드를 위한 다중 스레드 지원(Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)