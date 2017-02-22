---
title: "CGopherConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherConnection class"
  - "서버에 연결"
  - "서버에 연결, gopher servers"
  - "gopher 프로토콜"
  - "gopher server"
  - "Internet connections, gopher"
  - "Internet server, gopher"
  - "protocols, gopher"
  - "서버, 연결"
  - "서비스, gopher"
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGopherConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gopher 서버 인터넷 연결을 관리합니다.  
  
> [!NOTE]
>  클래스는 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 Windows XP 플랫폼에서 실행 되지 않지만 이전 플랫폼에서 작업을 계속할 수 있기 때문에 해당 멤버가 되지.  
  
## 구문  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CGopherConnection::CGopherConnection](../Topic/CGopherConnection::CGopherConnection.md)|`CGopherConnection` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)|생성 한  [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) gopher 서버에 파일을 찾을 수 있는 개체.|  
|[CGopherConnection::GetAttribute](../Topic/CGopherConnection::GetAttribute.md)|Gopher 개체에 대 한 특성 정보를 검색합니다.|  
|[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)|Gopher 파일을 엽니다.|  
  
## 설명  
 Gopher 서비스 MFC WinInet 클래스에서 인식 하는 세 인터넷 서비스 중 하나입니다.  
  
 클래스 `CGopherConnection` 생성자 및 gopher 서비스를 관리 하는 세 가지 추가 멤버 함수를 포함 합니다.  [OpenFile](../Topic/CGopherConnection::OpenFile.md),  [CreateLocator](../Topic/CGopherConnection::CreateLocator.md), 및  [GetAttribute](../Topic/CGopherConnection::GetAttribute.md).  
  
 Gopher 인터넷 서버와 통신 하려면 먼저 인스턴스를 만들어야 합니다  [CInternetSession](../../mfc/reference/cinternetsession-class.md), 다음 호출  [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md), 되는 `CGopherConnection` 개체에 대 한 포인터를 반환 하 고 있습니다.  절대로 만들는 `CGopherConnection` 직접 개체입니다.  
  
 방법에 대 한 자세한 내용은 `CGopherConnection` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  다른 두 가지 사용에 대 한 자세한 내용은 인터넷 서비스 지원에 대 한 FTP 및 HTTP 클래스를 참조 하십시오  [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및  [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Class](../../mfc/reference/cinternetsession-class.md)