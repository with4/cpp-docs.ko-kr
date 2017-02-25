---
title: "CGopherFileFind Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CGopherFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherFileFind class"
  - "파일 검색[C++]"
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CGopherFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gopher 서버 인터넷 파일 검색에서 지원입니다.  
  
> [!NOTE]
>  클래스는 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 Windows XP 플랫폼에서 실행 되지 않지만 이전 플랫폼에서 작업을 계속할 수 있기 때문에 해당 멤버가 되지.  
  
## 구문  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CGopherFileFind::CGopherFileFind](../Topic/CGopherFileFind::CGopherFileFind.md)|`CGopherFileFind` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CGopherFileFind::FindFile](../Topic/CGopherFileFind::FindFile.md)|Gopher 서버에 있는 파일을 찾습니다.|  
|[CGopherFileFind::FindNextFile](../Topic/CGopherFileFind::FindNextFile.md)|파일 검색에 대 한 이전 호출에서 계속  [FindFile](../Topic/CGopherFileFind::FindFile.md).|  
|[CGopherFileFind::GetCreationTime](../Topic/CGopherFileFind::GetCreationTime.md)|특정된 파일이 만들어진 시간을 가져옵니다.|  
|[CGopherFileFind::GetLastAccessTime](../Topic/CGopherFileFind::GetLastAccessTime.md)|지정 된 파일이 마지막으로 액세스 한 시간을 가져옵니다.|  
|[CGopherFileFind::GetLastWriteTime](../Topic/CGopherFileFind::GetLastWriteTime.md)|지정 된 파일에 마지막으로 쓴 시간을 가져옵니다.|  
|[CGopherFileFind::GetLength](../Topic/CGopherFileFind::GetLength.md)|찾은 파일을 바이트에서의 길이 가져옵니다.|  
|[CGopherFileFind::GetLocator](../Topic/CGopherFileFind::GetLocator.md)|가져오기는 `CGopherLocator` 개체입니다.|  
|[CGopherFileFind::GetScreenName](../Topic/CGopherFileFind::GetScreenName.md)|Gopher 스크린의 이름을 가져옵니다.|  
|[CGopherFileFind::IsDots](../Topic/CGopherFileFind::IsDots.md)|파일을 통해 반복 하는 동안 현재 디렉터리 및 부모 디렉터리 마커를 테스트 합니다.|  
  
## 설명  
 `CGopherFileFind`검색을 시작 하 고 파일을 찾은 파일의 URL을 반환 하는 멤버 함수가 포함 되어 있습니다.  
  
 인터넷 및 로컬 파일 검색 등 설계 다른 MFC 클래스  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 및  [CFileFind](../../mfc/reference/cfilefind-class.md).  과 함께 `CGopherFileFind`, 서버 프로토콜, 파일 형식 또는 위치 \(로컬 컴퓨터 또는 원격 서버입니다.\)에 관계 없이 특정 파일을 찾으려면 사용자는 원활한 메커니즘을 제공 하는 이러한 클래스 참고 없음 MFC 클래스를 검색 하 여 필요한 파일을 직접 조작 HTTP를 지원 하지 않기 때문에 HTTP 서버에서 검색 됩니다.  
  
> [!NOTE]
>  `CGopherFileFind`다음 기본 클래스 멤버 함수를 지원 하지 않습니다  [CFileFind](../../mfc/reference/cfilefind-class.md).  
  
-   [GetRoot](../Topic/CFileFind::GetRoot.md)  
  
-   [GetFileName](../Topic/CFileFind::GetFileName.md)  
  
-   [GetFilePath](../Topic/CFileFind::GetFilePath.md)  
  
-   [GetFileTitle](../Topic/CFileFind::GetFileTitle.md)  
  
-   [GetFileURL](../Topic/CFileFind::GetFileURL.md)  
  
 또한 사용 하는 경우 `CGopherFileFind`, `CFileFind` 멤버 함수  [IsDots](../Topic/CFileFind::IsDots.md) 항상  **거짓**.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CGopherFileFind` 및 기타 WinInet 클래스 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## 요구 사항  
 **헤더:**  afxinet.h  
  
## 참고 항목  
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind Class](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)