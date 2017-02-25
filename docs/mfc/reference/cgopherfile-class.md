---
title: "CGopherFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFile 클래스"
  - "gopher protocol files"
  - "인터넷, gopher"
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CGopherFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

찾기 및 gopher 서버에 파일을 읽을 수 있습니다.  
  
> [!NOTE]
>  클래스는 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 Windows XP 플랫폼에서 실행 되지 않지만 이전 플랫폼에서 작업을 계속할 수 있기 때문에 해당 멤버가 되지.  
  
## 구문  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CGopherFile::CGopherFile](../Topic/CGopherFile::CGopherFile.md)|`CGopherFile` 개체를 생성합니다.|  
  
## 설명  
 Gopher 서비스 사용자 인터페이스로 정보를 찾기 위한 주로 메뉴 기반 기능을이 서비스 때문에 gopher 파일에 데이터를 쓸 수 없습니다.  `CGopherFile` 멤버 함수  **쓰기**, `WriteString`, 및 `Flush` 에 구현 된 `CGopherFile`.  이러한 함수를 호출 하는 `CGopherFile` 개체를 반환 하며 읽기 전용의  [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 방법에 대 한 자세한 내용은 `CGopherFile` 다른 인터넷 MFC 클래스 사용 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator Class](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)