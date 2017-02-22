---
title: "CInternetConnection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous connections"
  - "CInternetConnection class"
  - "Internet connections"
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CInternetConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 서버에 연결을 관리합니다.  
  
## 구문  
  
```  
class CInternetConnection : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInternetConnection::CInternetConnection](../Topic/CInternetConnection::CInternetConnection.md)|`CInternetConnection` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CInternetConnection::GetContext](../Topic/CInternetConnection::GetContext.md)|이 연결 개체에 대 한 컨텍스트 ID를 가져옵니다.|  
|[CInternetConnection::GetServerName](../Topic/CInternetConnection::GetServerName.md)|연결과 관련 된 서버 이름을 가져옵니다.|  
|[CInternetConnection::GetSession](../Topic/CInternetConnection::GetSession.md)|에 대 한 포인터를 가져옵니다는  [CInternetSession](../../mfc/reference/cinternetsession-class.md) 연결과 관련 된 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CInternetConnection::operator HINTERNET](../Topic/CInternetConnection::operator%20HINTERNET.md)|인터넷 세션에 대 한 핸들입니다.|  
  
## 설명  
 MFC 클래스는 기본 클래스인  [CFtpConnection](../../mfc/reference/cftpconnection-class.md),  [CHttpConnection](../../mfc/reference/chttpconnection-class.md), 및  [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  이러한 각 클래스 각각의 HTTP, FTP, gopher 서버와 통신에 대 한 추가 기능을 제공 합니다.  
  
 인터넷 서버와 직접 통신 하려면 있어야는  [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체와 `CInternetConnection` 개체입니다.  
  
 WinInet 클래스를 작업 방법에 대 한 자세한 내용은  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)