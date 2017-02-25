---
title: "CInternetSession Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetSession class"
  - "Internet sessions"
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CInternetSession Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

및 단일 또는 여러 동시 인터넷 세션 초기화 만들고, 필요한 경우 프록시 서버 연결에 설명 합니다.  
  
## 구문  
  
```  
class CInternetSession : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInternetSession::CInternetSession](../Topic/CInternetSession::CInternetSession.md)|`CInternetSession` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CInternetSession::Close](../Topic/CInternetSession::Close.md)|인터넷 세션이 종료 되 면 인터넷 연결을 닫습니다.|  
|[CInternetSession::EnableStatusCallback](../Topic/CInternetSession::EnableStatusCallback.md)|상태 콜백 루틴을 설정합니다.|  
|[CInternetSession::GetContext](../Topic/CInternetSession::GetContext.md)|인터넷 세션이 종료 되 면 인터넷 연결을 닫습니다.|  
|[CInternetSession::GetCookie](../Topic/CInternetSession::GetCookie.md)|쿠키는 지정 된 URL과 모든 부모에 대 한 Url을 반환합니다.|  
|[CInternetSession::GetCookieLength](../Topic/CInternetSession::GetCookieLength.md)|버퍼에 저장 하는 쿠키의 길이 지정 하는 변수를 검색 합니다.|  
|[CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md)|서버와 FTP 세션을 엽니다.  사용자가 로그온 합니다.|  
|[CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md)|Gopher 서버에 대 한 연결을 열려고 시도 하는 응용 프로그램을 엽니다.|  
|[CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md)|HTTP 서버에 연결 하려고 하는 응용 프로그램을 엽니다.|  
|[CInternetSession::OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md)|상태 콜백이 활성화 된 경우 작업의 상태를 업데이트 합니다.|  
|[CInternetSession::OpenURL](../Topic/CInternetSession::OpenURL.md)|구문 분석 하 고 URL을 엽니다.|  
|[CInternetSession::SetCookie](../Topic/CInternetSession::SetCookie.md)|지정 된 URL에 대 한 쿠키를 설정합니다.|  
|[CInternetSession::SetOption](../Topic/CInternetSession::SetOption.md)|인터넷 세션에 대 한 옵션을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CInternetSession::operator HINTERNET](../Topic/CInternetSession::operator%20HINTERNET.md)|현재 인터넷 세션에 대 한 핸들입니다.|  
  
## 설명  
 인터넷 연결 응용 프로그램 기간 동안 유지 해야 하는 경우 만들 수 있습니다는 `CInternetSession` 멤버는 클래스의  [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 인터넷 세션을 설정 하면 호출할 수 있는  [OpenURL](../Topic/CInternetSession::OpenURL.md).  `CInternetSession`다음 URL에 대 한 전역 함수를 호출 하 여 분석  [AfxParseURL](../Topic/AfxParseURL.md).  프로토콜 형식에 관계 없이 `CInternetSession` URL을 해석 하 고이 관리 합니다.  "File:\/\/" URL 리소스를 식별 하는 로컬 파일에 대 한 요청을 처리할 수 있는.  `OpenURL`에 대 한 포인터를 반환 합니다는  [CStdioFile](../../mfc/reference/cstdiofile-class.md) 전달 이름을 하는 경우 개체는 로컬 파일입니다.  
  
 사용 하 여 인터넷 서버 URL을 열 경우 `OpenURL`, 사이트에서 정보를 읽을 수 있습니다.  서버에 있는 파일 \(예: HTTP, FTP, 또는 gopher\)에 특정 서비스 작업을 수행 하려는 경우 해당 서버에 적절 한 연결을 설정 해야 합니다.  특정 한 종류의 특정 서비스에 직접 연결을 열려면 다음 멤버 함수 중 하나를 사용 하십시오.  
  
-   [GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md) gopher 서비스에 연결할 수 있습니다.  
  
-   [GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md) HTTP 서비스에 연결할 수 있습니다.  
  
-   [GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md) 는 FTP 서비스에 연결할 수 있습니다.  
  
 [SetOption](../Topic/CInternetSession::SetOption.md) 세션 시간 제한 값, 재시도 횟수 등의 쿼리 옵션을 설정할 수 있습니다.  
  
 `CInternetSession`멤버 함수  [SetCookie](../Topic/CInternetSession::SetCookie.md),  [GetCookie](../Topic/CInternetSession::GetCookie.md), 및  [GetCookieLength](../Topic/CInternetSession::GetCookieLength.md) Win32 쿠키 데이터베이스를 서버와 스크립트 유지 클라이언트 워크스테이션에 대 한 상태 정보를 관리 하는 방법을 제공 합니다.  
  
 기본적인 인터넷 프로그래밍 작업에 대 한 자세한 내용은  [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md).  MFC WinInet 클래스를 사용 하는 방법에 대 한 일반적인 정보는 문서를 참조 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
>  `CInternetSession`throw 되는  [AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md) 지원 되지 않는 서비스 형식에 대 한.  서비스 다음 형식만 지원 됩니다: FTP, HTTP, gopher, 및 파일.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)