---
title: "CFtpFileFind Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFtpFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpFileFind class"
  - "파일 검색[C++]"
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CFtpFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 파일 검색의 FTP 서버 지원입니다.  
  
## 구문  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFtpFileFind::CFtpFileFind](../Topic/CFtpFileFind::CFtpFileFind.md)|`CFtpFileFind` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFtpFileFind::FindFile](../Topic/CFtpFileFind::FindFile.md)|FTP 서버에 있는 파일을 찾습니다.|  
|[CFtpFileFind::FindNextFile](../Topic/CFtpFileFind::FindNextFile.md)|파일 검색에 대 한 이전 호출에서 계속  [FindFile](../Topic/CFtpFileFind::FindFile.md).|  
|[CFtpFileFind::GetFileURL](../Topic/CFtpFileFind::GetFileURL.md)|찾은 파일의 경로 포함 하는 URL을 가져옵니다.|  
  
## 설명  
 `CFtpFileFind`검색을 시작 하 고 파일을 찾은 URL 또는 다른 파일에 대 한 설명 정보를 반환 하는 멤버 함수가 포함 되어 있습니다.  
  
 인터넷 및 로컬 파일 검색 등 설계 다른 MFC 클래스  [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및  [CFileFind](../../mfc/reference/cfilefind-class.md).  과 함께 `CFtpFileFind`, 이러한 클래스는 특정 파일 서버에 관계 없이 프로토콜 또는 파일 형식 \(로컬 컴퓨터 또는 원격 서버\)에 클라이언트에 대 한 원활한 메커니즘이 있습니다.  참고 MFC 클래스가 없습니다. 검색에 필요한 파일을 직접 조작 HTTP를 지원 하지 않기 때문에 HTTP 서버에서 검색 됩니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFtpFileFind` 및 기타 WinInet 클래스 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 예제  
 다음 코드는 FTP 서버의 현재 디렉토리의 모든 파일을 열거 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/CPP/cftpfilefind-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)