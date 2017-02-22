---
title: "CShellManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CShellManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CShellManager class"
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CShellManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

식별자 목록 \(Pidl\)에 대 한 포인터를 작업할 수 있도록 여러 메서드를 구현 합니다.  
  
## 구문  
  
```  
class CShellManager : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CShellManager::CShellManager](../Topic/CShellManager::CShellManager.md)|`CShellManager` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CShellManager::BrowseForFolder](../Topic/CShellManager::BrowseForFolder.md)|셸 폴더를 선택할 수 있도록 대화 상자를 표시 합니다.|  
|[CShellManager::ConcatenateItem](../Topic/CShellManager::ConcatenateItem.md)|두 Pidl 연결합니다.|  
|[CShellManager::CopyItem](../Topic/CShellManager::CopyItem.md)|새 PIDL을 만들고 제공 된 PIDL에 복사 합니다.|  
|[CShellManager::CreateItem](../Topic/CShellManager::CreateItem.md)|지정 된 크기의 새 PIDL 만듭니다.|  
|[CShellManager::FreeItem](../Topic/CShellManager::FreeItem.md)|제공 된 PIDL 삭제합니다.|  
|[CShellManager::GetItemCount](../Topic/CShellManager::GetItemCount.md)|제공 된 PIDL 항목 개수를 반환합니다.|  
|[CShellManager::GetItemSize](../Topic/CShellManager::GetItemSize.md)|제공 된 PIDL의 크기를 반환합니다.|  
|[CShellManager::GetNextItem](../Topic/CShellManager::GetNextItem.md)|PIDL에서 다음 항목을 반환합니다.|  
|[CShellManager::GetParentItem](../Topic/CShellManager::GetParentItem.md)|제공 된 항목의 부모 항목을 검색합니다.|  
|[CShellManager::ItemFromPath](../Topic/CShellManager::ItemFromPath.md)|PIDL 제공 된 경로로 식별 되는 항목을 검색 합니다.|  
  
## 설명  
 메서드는 `CShellManager` Pidl 모든 처리 클래스.  PIDL는 셸 개체에 대 한 고유 식별자입니다.  
  
 만들어야지 않습니다는 `CShellManager` 수동으로 개체입니다.  응용 프로그램 프레임 워크에서 자동으로 작성 됩니다.  그러나 호출 해야 [CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md) 응용 프로그램 초기화 중입니다.  셸 관리자에 게 응용 프로그램에 대 한 포인터를 가져오려면 호출 [CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxshellmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)