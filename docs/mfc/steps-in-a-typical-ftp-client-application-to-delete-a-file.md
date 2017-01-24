---
title: "일반적인 FTP 클라이언트 응용 프로그램에서 파일을 삭제하는 단계 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FTP(파일 전송 프로토콜), 클라이언트 응용 프로그램"
  - "인터넷 응용 프로그램, FTP 클라이언트 응용 프로그램"
  - "인터넷 클라이언트 응용 프로그램, FTP delete"
  - "WinInet 클래스, FTP"
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 일반적인 FTP 클라이언트 응용 프로그램에서 파일을 삭제하는 단계
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 표에서 파일을 삭제하는 일반적인 FTP 클라이언트 응용 프로그램에서 수행할 수 있는 단계를 보여줍니다.  
  
|목표|수행할 작업|효과|  
|--------|------------|--------|  
|FTP 세션을 시작합니다.|[CInternetSession](../mfc/reference/cinternetsession-class.md) 개체를 만듭니다.|WinInet을 초기화하고 서버에 연결합니다.|  
|FTP 서버에 연결.|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)을 사용합니다.|[CFtpConnection](../mfc/reference/cftpconnection-class.md) 개체를 반환합니다.|  
|FTP 서버의 올바른 디렉터리에 있는지 확인합니다.|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md) 또는  [CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)를 사용합니다.|이름 또는 선택한 멤버 함수에 따라 서버에 연결할 현재 디렉터리의 URL을 반환합니다.|  
|서버의 새로운 FTP 디렉터리로 이동합니다.|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)을 사용합니다.|서버에 연결할 현재 디렉터리를 변경합니다.|  
|FTP 디렉터리에서 첫째 파일을 찾습니다.|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)을 사용합니다.|첫 번째 파일을 찾습니다.  파일이 발견 되지 않으면 FALSE를 반환합니다.|  
|FTP 디렉터리에서 다음 파일을 찾습니다.|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)을 사용합니다.|다음 파일을 찾습니다.  파일을 찾을 수 없으면 FALSE를 반환합니다.|  
|**FindFile** 또는  `FindNextFile` 으로 찾은 파일을 삭제합니다.|**FindFile** 또는  `FindNextFile` 에 의해 반환된 파일 이름을 사용하여, [CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)을 사용합니다.|서버의 읽기 또는 쓰기용 파일을 삭제합니다.|  
|예외 처리|[CInternetException](../mfc/reference/cinternetexception-class.md) 클래스를 사용합니다.|모든 일반적인 인터넷 예외 형식을 처리합니다.|  
|FTP 세션을 종료합니다.|[CInternetSession](../mfc/reference/cinternetsession-class.md) 개체를 종료합니다.|자동으로 열려있는 파일 핸들 및 연결을 정리합니다.|  
  
## 참고 항목  
 [Win32 인터넷 확장\(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스의 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)