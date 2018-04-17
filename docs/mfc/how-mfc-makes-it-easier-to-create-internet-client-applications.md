---
title: 어떻게 MFC를 사용 하면 인터넷 클라이언트 응용 프로그램을 만드는 쉽게 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6270cdd3e64d24f1c2000acb9e8466f8c85edba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC를 사용하여 인터넷 클라이언트 응용 프로그램을 손쉽게 만드는 방법
Microsoft Foundation 클래스는 MFC 프로그래머를 위한 친숙 한 컨텍스트를 제공 하는 방식으로 Win32 인터넷 확장 (WinInet) 함수를 캡슐화 합니다. MFC는 세 가지 인터넷 파일 클래스를 제공 ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), 및 [CGopherFile](../mfc/reference/cgopherfile-class.md))에서 파생 된 [CStdioFile](../mfc/reference/cstdiofile-class.md) 클래스 . 뿐만 아니라 방법을 쉽게 검색 하 고 인터넷 데이터 조작을 사용한 프로그래머에 게 익숙한 `CStdioFile` 일관 되 고 투명 하 게의 로컬 파일 및 인터넷 파일 로컬 파일에 있지만이 클래스와 함께 처리할 수 있습니다.  
  
 MFC WinInet 클래스와 동일한 기능을 제공 `CStdioFile` 인터넷을 통해 전송 되는 데이터에 대 한 합니다. 이러한 클래스를 사용 하면 HTTP, FTP 및 gopher에 대 한 인터넷 프로토콜을 추상화 하는 상위 수준 응용 프로그램 프로그래밍 인터페이스, 인터넷 인식 응용 프로그램에 대 한 빠르고 간단한 경로 제공 합니다. 예를 들어 낮은 수준에서 여러 단계가 필요 여전히 FTP 서버에 연결 하지만 MFC 개발자는 하기만 하면를 한 번 호출 되도록 `CInternetSession::GetFTPConnection` 해당 연결을 만듭니다.  
  
 또한 MFC WinInet 클래스는 다음과 같은 이점을 제공합니다.  
  
-   버퍼링 된 I/O  
  
-   데이터에 대 한 형식이 안전한 처리  
  
-   다양 한 기능에 대 한 기본 매개 변수  
  
-   일반적인 인터넷 오류의 예외 처리  
  
-   열려 있는 핸들 및 연결의 자동 정리  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [WinInet을 사용하여 인터넷 클라이언트 응용 프로그램을 손쉽게 만드는 방법](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

