---
title: "CFtpConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFtpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpConnection class"
  - "FTP(파일 전송 프로토콜), 연결 설정"
  - "Internet connections, FTP"
  - "Internet services, FTP"
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CFtpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 서버에 FTP 연결을 관리 하 고 디렉터리 및 파일 서버에서 직접 조작할 수 있습니다.  
  
## 구문  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFtpConnection::CFtpConnection](../Topic/CFtpConnection::CFtpConnection.md)|`CFtpConnection` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFtpConnection::Command](../Topic/CFtpConnection::Command.md)|명령을 FTP 서버에 직접 보냅니다.|  
|[CFtpConnection::CreateDirectory](../Topic/CFtpConnection::CreateDirectory.md)|서버에서 디렉터리를 만듭니다.|  
|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md)|이 연결에 대 한 현재 디렉터리를 가져옵니다.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)|이 URL로이 연결에 대 한 현재 디렉터리를 가져옵니다.|  
|[CFtpConnection::GetFile](../Topic/CFtpConnection::GetFile.md)|연결 된 서버에서 파일을 가져옵니다.|  
|[CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)|연결 된 서버에 있는 파일을 엽니다.|  
|[CFtpConnection::PutFile](../Topic/CFtpConnection::PutFile.md)|서버에 파일을 배치합니다.|  
|[CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)|서버에서 파일을 제거합니다.|  
|[CFtpConnection::RemoveDirectory](../Topic/CFtpConnection::RemoveDirectory.md)|지정 된 디렉터리 서버에서 제거합니다.|  
|[CFtpConnection::Rename](../Topic/CFtpConnection::Rename.md)|서버에 있는 파일을 이름을 바꿉니다.|  
|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)|현재 FTP 디렉터리를 설정합니다.|  
  
## 설명  
 FTP은 WinInet MFC 클래스로 인식 세 인터넷 서비스 중 하나입니다.  
  
 인터넷 FTP 서버와 통신 하려면 먼저 인스턴스를 만들어야 합니다  [CInternetSession](../../mfc/reference/cinternetsession-class.md)를 만들어 다음에 `CFtpConnection` 개체.  절대로 만들는 `CFtpConnection` 개체를 직접. 대신 호출  [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), 되는 `CFtpConnection` 개체에 대 한 포인터를 반환 하 고 있습니다.  
  
 방법에 대 한 자세한 내용은 `CFtpConnection` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  서비스, HTTP 및 gopher, 클래스를 참조 하십시오. 지원 되는 다른 2와 통신 하는 방법에 대 한 자세한 내용은  [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및  [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## 예제  
 예에서 볼 수 있는  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 클래스 개요.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)