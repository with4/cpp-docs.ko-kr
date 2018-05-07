---
title: 일반적인 Gopher 클라이언트 응용 프로그램의 단계를 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ebb97d7cb5cbf2e2ed9ac7ae5287b2261990f2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="steps-in-a-typical-gopher-client-application"></a>일반적인 Gopher 클라이언트 응용 프로그램의 단계
다음 표에서 일반적인 gopher 클라이언트 응용 프로그램에서 수행할 수는 단계를 보여 줍니다.  
  
|목표|수행할 작업|효과|  
|---------------|----------------------|-------------|  
|Gopher 세션을 시작 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|  
|Gopher 서버에 연결 합니다.|사용 하 여 [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)합니다.|반환 된 [CGopherConnection](../mfc/reference/cgopherconnection-class.md) 개체입니다.|  
|gopher에서 첫 번째 리소스 찾기|사용 하 여 [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)합니다.|첫 번째 파일을 찾습니다. 파일이 발견되지 않으면 FALSE를 반환합니다.|  
|다음 리소스는 gopher에서 찾기|사용 하 여 [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile)합니다.|다음 파일을 찾습니다. 파일을 찾을 수 없으면 FALSE를 반환합니다.|  
|로 찾은 파일을 열고 **FindFile** 또는 `FindNextFile` 읽기에 대 한 합니다.|사용 하 여 gopher 로케이터 가져옵니다 [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator)합니다. 사용 하 여 [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)합니다.|로케이터에 의해 지정 된 파일을 엽니다. `OpenFile` 반환 된 [CGopherFile](../mfc/reference/cgopherfile-class.md) 개체입니다.|  
|제공한 gopher 로케이터를 사용 하 여 파일을 엽니다.|사용 하 여 gopher 로케이터 만들기 [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)합니다. 사용 하 여 [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)합니다.|로케이터에 의해 지정 된 파일을 엽니다. `OpenFile` 반환 된 [CGopherFile](../mfc/reference/cgopherfile-class.md) 개체입니다.|  
|파일에서 읽습니다.|사용 하 여 [CGopherFile](../mfc/reference/cgopherfile-class.md)합니다.|지정 된 사용자가 제공 하는 버퍼를 사용 하 여 바이트 수를 읽습니다.|  
|예외 처리|사용 하 여 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|  
|Gopher 세션을 종료 합니다.|삭제 된 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스에 대 한 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
