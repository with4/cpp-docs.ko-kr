---
title: "일반적인 인터넷 클라이언트 응용 프로그램의 단계를 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ce4f5b91ebd68f13510f887c65927dbe5f84133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-internet-client-application"></a>일반적인 인터넷 클라이언트 응용 프로그램의 단계
다음 표에서 일반적인 인터넷 클라이언트 응용 프로그램에서 수행할 수는 단계를 보여 줍니다.  
  
|목표|수행할 작업|효과|  
|---------------|----------------------|-------------|  
|인터넷 세션을 시작 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|  
|인터넷 쿼리 옵션 (시간 제한 또는 횟수, 예:)을 설정 합니다.|사용 하 여 [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)합니다.|작업에 실패 하면 FALSE를 반환 합니다.|  
|세션의 상태를 모니터링 하는 콜백 함수를 설정 합니다.|사용 하 여 [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)합니다.|설정에 대 한 콜백을 [cinternetsession:: Onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다. 재정의 `OnStatusCallback` 사용자 고유의 콜백 루틴을 만들려고 합니다.|  
|인터넷 서버, 인트라넷 서버 또는 로컬 파일에 연결 합니다.|사용 하 여 [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl)합니다.|URL을 구문 분석 하 고 지정된 된 서버에 연결을 엽니다. 반환 된 [CStdioFile](../mfc/reference/cstdiofile-class.md) (전달 하는 경우 `OpenURL` 로컬 파일 이름). 서버 또는 파일에서 검색 한 데이터 액세스 수 있는 개체입니다.|  
|파일에서 읽습니다.|사용 하 여 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read)합니다.|지정된 된 사용자가 제공 하는 버퍼를 사용 하 여 바이트 수를 읽습니다.|  
|예외 처리|사용 하 여 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|  
|인터넷 세션을 종료 합니다.|삭제 된 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스에 대 한 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
