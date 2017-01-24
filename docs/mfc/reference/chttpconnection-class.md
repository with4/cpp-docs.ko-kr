---
title: "CHttpConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHttpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpConnection class"
  - "서버에 연결"
  - "서버에 연결, HTTP 서버"
  - "연결[C++], HTTP"
  - "HTTP 연결"
  - "HTTP 서버, 연결"
  - "Internet connections, HTTP"
  - "Internet protocols"
  - "Internet protocols, HTTP"
  - "Internet server, HTTP"
  - "protocols, HTTP"
  - "서버, 연결"
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHttpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

HTTP 서버에 연결을 관리합니다.  
  
## 구문  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHttpConnection::CHttpConnection](../Topic/CHttpConnection::CHttpConnection.md)|`CHttpConnection` 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)|HTTP 요청을 엽니다.|  
  
## 설명  
 HTTP은 WinInet MFC 클래스에 의해 구현 된 세 인터넷 서버 프로토콜 중 하나입니다.  
  
 클래스 `CHttpConnection` 생성자 및 멤버 함수를 포함  [OpenRequest](../Topic/CHttpConnection::OpenRequest.md), 해당 서버는 HTTP 프로토콜에 연결을 관리 합니다.  
  
 HTTP 서버와 통신 하려면 먼저 인스턴스를 만들어야 합니다  [CInternetSession](../../mfc/reference/cinternetsession-class.md)를 만들어 다음에  [CHttpConnection](#_mfc_chttpconnection) 개체.  절대로 만들는 `CHttpConnection` 개체를 직접. 대신 호출  [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), 되는 `CHttpConnection` 개체에 대 한 포인터를 반환 하 고 있습니다.  
  
 방법에 대 한 자세한 내용은 `CHttpConnection` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  두 가지를 사용 하 여 서버에 연결 하는 방법에 대 한 자세한 내용은 인터넷 프로토콜, gopher 및 FTP 지원에 대 한 클래스를 참조 하십시오.  [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 및  [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)