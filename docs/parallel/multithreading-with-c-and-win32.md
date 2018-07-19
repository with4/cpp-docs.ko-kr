---
title: C 및 Win32를 사용한 다중 스레딩 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 993bee92c9dacc831a8bbc8fc000ec982025a399
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687545"
---
# <a name="multithreading-with-c-and-win32"></a>C 및 Wind32를 사용한 다중 스레딩
Microsoft Visual c + +는 다중 스레드 응용 프로그램을 만들기에 대 한 지원을 제공 합니다. 응용 프로그램 사용자 인터페이스가 응답 하지 못하도록 하는 부담이 큰 작업을 수행 해야 하는 경우에 둘 이상의 스레드를 사용 하는 것이 좋습니다.  
  
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