---
title: "CHttpFile Class | Microsoft Docs"
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
  - "CHttpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpFile class"
  - "HTTP 파일"
  - "HTTP requests, requesting and reading files"
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHttpFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

HTTP 서버에서 파일을 읽고 요청 기능을 제공 합니다.  
  
## 구문  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHttpFile::CHttpFile](../Topic/CHttpFile::CHttpFile.md)|`CHttpFile` 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHttpFile::AddRequestHeaders](../Topic/CHttpFile::AddRequestHeaders.md)|HTTP 서버에 보내는 요청에 헤더를 추가 합니다.|  
|[CHttpFile::EndRequest](../Topic/CHttpFile::EndRequest.md)|HTTP 서버에 전송 된 요청 종료는  [SendRequestEx](../Topic/CHttpFile::SendRequestEx.md) 멤버 함수입니다.|  
|[CHttpFile::GetFileURL](../Topic/CHttpFile::GetFileURL.md)|지정 된 파일에 대 한 URL을 가져옵니다.|  
|[CHttpFile::GetObject](../Topic/CHttpFile::GetObject.md)|대상 개체를의 동사 요청에 HTTP 서버를 가져옵니다.|  
|[CHttpFile::GetVerb](../Topic/CHttpFile::GetVerb.md)|요청에 HTTP 서버에 사용 된 동사를 가져옵니다.|  
|[CHttpFile::QueryInfo](../Topic/CHttpFile::QueryInfo.md)|서버에서 HTTP 요청 또는 응답 헤더를 반환합니다.|  
|[CHttpFile::QueryInfoStatusCode](../Topic/CHttpFile::QueryInfoStatusCode.md)|HTTP 요청과 관련 된 상태 코드를 검색 및 제공 된에 배치 `dwStatusCode` 매개 변수.|  
|[CHttpFile::SendRequest](../Topic/CHttpFile::SendRequest.md)|HTTP 서버에 요청을 보냅니다.|  
|[CHttpFile::SendRequestEx](../Topic/CHttpFile::SendRequestEx.md)|서버를 사용 하는 HTTP 요청을  [쓰기](../Topic/CInternetFile::Write.md) 또는  [WriteString](../Topic/CInternetFile::WriteString.md) 메서드를 `CInternetFile`.|  
  
## 설명  
 인터넷 세션을 HTTP 서버에서 데이터를 읽는 경우의 인스턴스를 만들 `CHttpFile`.  
  
 방법에 대 한 자세한 내용은 `CHttpFile` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)