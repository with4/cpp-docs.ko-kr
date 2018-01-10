---
title: "응용 프로그램 및 스레드 지원 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.support
dev_langs: C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e443c2393d9d3a8a0f61df6adddb2c83e7672723
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="application-and-thread-support-classes"></a>응용 프로그램 및 스레드 지원 클래스
각 응용 프로그램은 하나의 응용 프로그램 개체입니다. 이 개체는 실행 중인 프로그램의 다른 개체를 조정 하 고에서 파생 된 `CWinApp`합니다.  
  
 Microsoft Foundation 클래스 (MFC) 라이브러리는 다중 스레드 응용 프로그램 내에서 실행을 지원합니다. 모든 응용 프로그램 하나 이상의 스레드가; 있어야 합니다. 사용 되는 스레드 프로그램 `CWinApp` 개체는이 기본 스레드입니다.  
  
 `CWinThread`일부 운영 체제의 스레딩 기능을 캡슐화합니다. 여러 스레드를 보다 쉽게 사용 되도록 MFC 동기화를 Win32 동기화 개체를 c + + 인터페이스를 제공 하는 개체 클래스도 제공 합니다.  
  
## <a name="application-and-thread-classes"></a>응용 프로그램 및 스레드 클래스  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 초기화, 실행 및 응용 프로그램을 종료 하는 코드를 캡슐화 합니다. 이 클래스에서 응용 프로그램 개체를 파생 합니다.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 모든 스레드에 대 한 기본 클래스입니다. 를 직접 사용 하거나에서 클래스를 파생 `CWinThread` 스레드 사용자 인터페이스 기능을 수행 하는 경우. `CWinApp`는 `CWinThread`에서 파생됩니다.  
  
## <a name="synchronization-object-classes"></a>동기화 개체 클래스  
 [CSyncObject](../mfc/reference/csyncobject-class.md)  
 동기화 개체 클래스의 기본 클래스입니다.  
  
 [아니오](../mfc/reference/ccriticalsection-class.md)  
 개체에 액세스 하는 단일 프로세스에서 스레드를 하나만 허용 하는 동기화 클래스입니다.  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 1-지정된 된 최대 수의 동시 액세스는 개체를 허용 하는 동기화 클래스  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 임의 개수의 개체에 액세스 하는 프로세스 내에서 하나의 스레드를 허용 하는 동기화 클래스  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 이벤트가 발생 하는 경우 응용 프로그램을 알리는 동기화 클래스입니다.  
  
 [경우 CSingleLock](../mfc/reference/csinglelock-class.md)  
 하나의 동기화 개체에 대 한 잠금 스레드로부터 안전한 클래스의 멤버 함수에 사용 합니다.  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 동기화 개체의 배열에서 하나 이상의 동기화 개체에 대 한 잠금 스레드로부터 안전한 클래스의 멤버 함수에 사용 합니다.  
  
## <a name="related-classes"></a>관련된 클래스  
 [CCommandLineInfo](../mfc/reference/ccommandlineinfo-class.md)  
 프로그램 시작 된 명령줄 구문 분석 합니다.  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 대기 커서를 화면에 배치합니다. 시간이 오래 걸리는 작업 중에 사용 합니다.  
  
 [CDockState](../mfc/reference/cdockstate-class.md)  
 도킹 컨트롤 막대에 대 한 상태 데이터의 영구 저장소를 처리 합니다.  
  
 [CRecentFileList](../mfc/reference/crecentfilelist-class.md)  
 가장 최근에 사용한 (MRU) 파일 목록 유지 관리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

