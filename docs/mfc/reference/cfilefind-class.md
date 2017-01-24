---
title: "CFileFind Class | Microsoft Docs"
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
  - "CFileFind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileFind class"
  - "파일[C++], 찾기"
  - "Internet files [C++], 찾기"
  - "local files"
  - "local files, 검색"
  - "URLs [C++], 검색"
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileFind Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

로컬 파일 검색을 수행 하는 기본 클래스입니다  [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및  [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), 인터넷 파일 검색을 수행 합니다.  
  
## 구문  
  
```  
class CFileFind : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFileFind::CFileFind](../Topic/CFileFind::CFileFind.md)|`CFileFind` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFileFind::Close](../Topic/CFileFind::Close.md)|검색 요청을 닫습니다.|  
|[CFileFind::FindFile](../Topic/CFileFind::FindFile.md)|지정 된 파일 이름에 대 한 디렉터리를 검색합니다.|  
|[CFileFind::FindNextFile](../Topic/CFileFind::FindNextFile.md)|파일 검색에 대 한 이전 호출에서 계속  [FindFile](../Topic/CFileFind::FindFile.md).|  
|[CFileFind::GetCreationTime](../Topic/CFileFind::GetCreationTime.md)|파일이 만들어진 시간을 가져옵니다.|  
|[CFileFind::GetFileName](../Topic/CFileFind::GetFileName.md)|찾은 파일의 확장명을 포함 하 여 이름을 가져옵니다.|  
|[CFileFind::GetFilePath](../Topic/CFileFind::GetFilePath.md)|찾은 파일의 전체 경로 가져옵니다.|  
|[CFileFind::GetFileTitle](../Topic/CFileFind::GetFileTitle.md)|찾은 파일의 제목을 가져옵니다.  제목을 확장명이 포함 되지 않습니다.|  
|[CFileFind::GetFileURL](../Topic/CFileFind::GetFileURL.md)|찾은 파일의 파일 경로 포함 하는 URL을 가져옵니다.|  
|[CFileFind::GetLastAccessTime](../Topic/CFileFind::GetLastAccessTime.md)|파일이 마지막으로 액세스 한 시간을 가져옵니다.|  
|[CFileFind::GetLastWriteTime](../Topic/CFileFind::GetLastWriteTime.md)|파일이 마지막으로 변경 및 저장 된 시간을 가져옵니다.|  
|[CFileFind::GetLength](../Topic/CFileFind::GetLength.md)|찾은 파일을 바이트에서의 길이 가져옵니다.|  
|[CFileFind::GetRoot](../Topic/CFileFind::GetRoot.md)|찾은 파일의 루트 디렉터리를 가져옵니다.|  
|[CFileFind::IsArchived](../Topic/CFileFind::IsArchived.md)|찾은 파일을 보관 하는 경우를 결정 합니다.|  
|[CFileFind::IsCompressed](../Topic/CFileFind::IsCompressed.md)|찾은 파일 압축 여부를 결정 합니다.|  
|[CFileFind::IsDirectory](../Topic/CFileFind::IsDirectory.md)|찾은 파일 디렉터리 인지 여부를 확인 합니다.|  
|[CFileFind::IsDots](../Topic/CFileFind::IsDots.md)|찾은 파일의 이름을 이름 인지 여부를 결정 "."또는".."을 나타내는 실제 디렉터리입니다.|  
|[CFileFind::IsHidden](../Topic/CFileFind::IsHidden.md)|찾은 파일을 숨길지 여부를 결정 합니다.|  
|[CFileFind::IsNormal](../Topic/CFileFind::IsNormal.md)|찾은 파일 정상 인지 여부 \(즉, 다른 특성이 없습니다\).|  
|[CFileFind::IsReadOnly](../Topic/CFileFind::IsReadOnly.md)|찾은 파일 읽기 전용인 지 여부를 결정 합니다.|  
|[CFileFind::IsSystem](../Topic/CFileFind::IsSystem.md)|찾은 파일 시스템 파일 인지 여부를 확인 합니다.|  
|[CFileFind::IsTemporary](../Topic/CFileFind::IsTemporary.md)|찾은 파일 임시 인지 여부를 확인 합니다.|  
|[CFileFind::MatchesMask](../Topic/CFileFind::MatchesMask.md)|원하는 파일 특성의 파일을 찾을 수를 나타냅니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFileFind::CloseContext](../Topic/CFileFind::CloseContext.md)|현재 검색 핸들에 의해 지정 된 파일을 닫습니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CFileFind::m\_pTM](../Topic/CFileFind::m_pTM.md)|포인터는 `CAtlTransactionManager` 개체입니다.|  
  
## 설명  
 `CFileFind`검색을 시작 하 고 파일을 찾은 제목, 이름 또는 파일 경로 반환 하는 멤버 함수가 포함 되어 있습니다.  인터넷 검색, 멤버 함수에 대 한  [GetFileURL](../Topic/CFileFind::GetFileURL.md) 파일의 URL을 반환 합니다.  
  
 `CFileFind`두 MFC 클래스에 대 한 기본 클래스 형식을 특정 서버를 검색 하도록 설계 되었습니다: `CGopherFileFind` gopher 서버 특히 작동 및 `CFtpFileFind` FTP 서버에 특히 적합 합니다.  함께, 이러한 세 가지 클래스 파일 서버 프로토콜, 파일 형식 또는 위치에 관계 없이 로컬 컴퓨터 또는 원격 서버에 클라이언트에 대 한 원활한 메커니즘을 제공 합니다.  
  
 다음 코드는 각 파일의 이름을 인쇄 하는 현재 디렉터리의 모든 파일을 열거 됩니다.  
  
 [!code-cpp[NVC_MFCFiles#31](../../mfc/codesnippet/CPP/cfilefind-class_1.cpp)]  
  
 이 코드 예제를 간단히 하기 위해 표준 C\+\+ 라이브러리를 사용 `cout` 클래스입니다.  `cout` 줄 호출로 바꿀 수 `CListBox::AddString`, 예를 들어, 그래픽 사용자 인터페이스를 가진 프로그램에서입니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFileFind` 및 기타 WinInet 클래스 문서를 참고 하십시오.  [WinInet 인터넷 프로그래밍](../../mfc/win32-internet-extensions-wininet.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind Class](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Class](../../mfc/reference/chttpfile-class.md)