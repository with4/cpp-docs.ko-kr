---
title: "유휴 루프 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, background processing
- PeekMessage method [MFC], elsewhere than message loop
- PeekMessage method [MFC]
- MFC, messages
- messages [MFC], loops
- OnIdle method [MFC]
- processing [MFC], background
- idle loop processing [MFC]
- idle processing [MFC]
- threading [MFC], alternatives to multithreading
- processing, during idle loop
- processing [MFC]
- background processing [MFC]
ms.assetid: 5c7c46c1-6107-4304-895f-480983bb1e44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: baabba60ffaf886b7a34acfbff5b923a4495fa1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="idle-loop-processing"></a>유휴 루프 처리
대부분의 응용 프로그램 "에서"배경입니다. 시간이 오래 걸리는 처리를 수행합니다. 경우에 따라 성능 고려 사항에 따라 이러한 작업에 다중 스레딩을 사용할. 스레드 관련 별도 개발 오버 헤드 하므로 MFC가 유휴 시간 작업 등의 간단한 작업에 대 한 권장 되지 않습니다는 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) 함수입니다. 이 문서는 유휴 프로세스에 중점을 둡니다. 다중 스레딩, 참조에 대 한 자세한 내용은 [다중 스레딩 항목](../parallel/multithreading-support-for-older-code-visual-cpp.md)합니다.  
  
 일부 유형의 백그라운드 작업을 처리 하는 동안 사용자가 응용 프로그램 상호 작용 하지는 간격에 따라 적절 하 게 수행 됩니다. Microsoft Windows 운영 체제에 대 한 개발 된 응용 프로그램, 응용 프로그램 유휴 시간 처리 하려면 시간이 많이 걸릴 여러 개의 작은 조각으로 분할 하 여 수행할 수 있습니다. 각 조각은 처리 한 후 응용 프로그램 생성을 사용 하 여 Windows 실행 제어는 [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) 루프입니다.  
  
 이 문서에서는 유휴 응용 프로그램에서 처리를 수행 하는 두 가지를 설명 합니다.  
  
-   사용 하 여 **PeekMessage** MFC의 기본 메시지 루프에 있습니다.  
  
-   포함 하는 다른 **PeekMessage** 응용 프로그램에서 다른 위치를 반복 합니다.  
  
##  <a name="_core_peekmessage_in_the_mfc_message_loop"></a>MFC 메시지 루프의 PeekMessage  
 MFC를 사용 하 여 개발 된 응용 프로그램에서는 기본 메시지 루프는 `CWinThread` 호출 하는 메시지 루프를 포함 하는 클래스는 [PeekMessage](http://msdn.microsoft.com/library/windows/desktop/ms644943) Win32 API입니다. 이 호출 또한 루프는 `OnIdle` 의 멤버 함수 `CWinThread` 메시지 사이입니다. 응용 프로그램 재정의 하 여 유휴 시간에 메시지를 처리할 수는 `OnIdle` 함수입니다.  
  
> [!NOTE]
>  **실행**, `OnIdle`, 다른 특정 멤버 함수는 이제 클래스의 멤버 및 `CWinThread` 아닌 클래스의 `CWinApp`합니다. `CWinApp`는 `CWinThread`에서 파생됩니다.  
  
 유휴 처리를 수행 하는 방법에 대 한 자세한 내용은 참조 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) 에 *MFC 참조*합니다.  
  
##  <a name="_core_peekmessage_elsewhere_in_your_application"></a>응용 프로그램의 다른 위치에서 PeekMessage  
 유휴 응용 프로그램에서 처리를 수행 하는 다른 방법은 함수 중 하나에 메시지 루프를 포함 하는 작업이 포함 됩니다. 이 메시지 루프는에서 발견 되는 MFC의 기본 메시지 루프와 매우 비슷합니다 [CWinThread::Run](../mfc/reference/cwinthread-class.md#run)합니다. 즉, MFC를 사용 하 여 개발한 응용 프로그램에서 루프는 다양 한 기본 메시지 루프와 동일한 기능을 수행 해야 합니다. 다음 코드 조각은 MFC 호환 되는 메시지 루프를 작성 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCDocView#8](../mfc/codesnippet/cpp/idle-loop-processing_1.cpp)]  
  
 이 코드는 함수에 포함 된 작업을 수행 하는 유휴 상태 처리가으로 반복 됩니다. 해당 루프 내에서 중첩된 된 루프 반복 해 서 호출 **PeekMessage**합니다. 루프를 호출 하는 호출 하는 0이 아닌 값을 반환 하는 경우으로 `CWinThread::PumpMessage` 일반 메시지 변환 및 디스패치를 수행 하려면. 하지만 `PumpMessage` 문서화 않습니다 ThrdCore.Cpp 파일 Visual c + + 설치의 \atlmfc\src\mfc 디렉터리에서 해당 소스 코드를 검사할 수 있습니다.  
  
 한 번 안쪽 루프 종료 외부 루프 처리를 수행 유휴 하나 이상의 호출을 통해 `OnIdle`합니다. MFC의 목적에서 첫 번째 호출이 됩니다. 에 대 한 추가 호출을 만들 수 있습니다 `OnIdle` 직접 백그라운드 작업을 수행할 수 있습니다.  
  
 유휴 처리를 수행 하는 방법에 대 한 자세한 내용은 참조 [OnIdle](../mfc/reference/cwinthread-class.md#onidle) MFC 라이브러리 참조에서.  
  
## <a name="see-also"></a>참고 항목  
 [일반 MFC 항목](../mfc/general-mfc-topics.md)

