---
title: "CRecentFileList Class | Microsoft Docs"
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
  - "CRecentFileList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecentFileList class"
  - "파일[C++], most recently used"
  - "MRU 파일"
ms.assetid: a77f0524-7584-4582-849a-7e97b76d186e
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecentFileList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가장 최근에 사용한 \(MRU\) 파일 목록에 지 원하는 컨트롤입니다.  
  
## 구문  
  
```  
class CRecentFileList  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRecentFileList::CRecentFileList](../Topic/CRecentFileList::CRecentFileList.md)|`CRecentFileList` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRecentFileList::Add](../Topic/CRecentFileList::Add.md)|최근에 사용한 파일 목록에 파일을 추가합니다.|  
|[CRecentFileList::GetDisplayName](../Topic/CRecentFileList::GetDisplayName.md)|메뉴에서 MRU 파일 이름 표시의 표시 이름을 제공합니다.|  
|[CRecentFileList::GetSize](../Topic/CRecentFileList::GetSize.md)|최근에 사용한 파일 목록에서 파일을 검색합니다.|  
|[CRecentFileList::ReadList](../Topic/CRecentFileList::ReadList.md)|레지스트리에서 MRU 파일 목록 또는.INI 파일입니다.|  
|[CRecentFileList::Remove](../Topic/CRecentFileList::Remove.md)|최근에 사용한 파일 목록에서 파일을 제거합니다.|  
|[CRecentFileList::UpdateMenu](../Topic/CRecentFileList::UpdateMenu.md)|메뉴 표시 최근에 사용한 파일 목록 업데이트합니다.|  
|[CRecentFileList::WriteList](../Topic/CRecentFileList::WriteList.md)|최근에 사용한 파일 목록 레지스트리에서 기록 또는.INI 파일입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CRecentFileList::operator](../Topic/CRecentFileList::operator.md)|반환 된 `CString` 개체에 지정 된 위치.|  
  
## 설명  
 파일 추가 또는 최근에 사용한 파일 목록에서 삭제할 수 있습니다, 파일 목록에서 읽을 수 또는 레지스트리에 기록 또는.INI 파일 및 최근에 사용한 파일 목록에 표시 되는 메뉴를 업데이트할 수 있습니다.  
  
 MRU 메뉴 항목에 대 한 자세한 내용은 참조 하십시오.  
  
-   기술 자료 문서 Q243751: 방법: MFC 응용 프로그램에서 MRU 메뉴 항목에 대 한 명령 처리기 추가  
  
## 상속 계층 구조  
 `CRecentFileList`  
  
## 요구 사항  
 **헤더:**  afxadv.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)