---
title: "CContextMenuManager Class | Microsoft Docs"
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
  - "CContextMenuManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContextMenuManager class"
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CContextMenuManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CContextMenuManager` 바로 가기 메뉴를 상황에 맞는 메뉴 라고도 하는 개체를 관리 합니다.  
  
## 구문  
  
```  
class CContextMenuManager : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CContextMenuManager::CContextMenuManager](../Topic/CContextMenuManager::CContextMenuManager.md)|`CContextMenuManager` 개체를 생성합니다.|  
|`CContextMenuManager::~CContextMenuManager`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CContextMenuManager::AddMenu](../Topic/CContextMenuManager::AddMenu.md)|새 바로 가기 메뉴를 추가합니다.|  
|[CContextMenuManager::GetMenuById](../Topic/CContextMenuManager::GetMenuById.md)|제공 된 리소스 ID와 관련 된 메뉴의 핸들을 반환|  
|[CContextMenuManager::GetMenuByName](../Topic/CContextMenuManager::GetMenuByName.md)|제공 된 메뉴 이름에 맞는 메뉴에는 핸들을 반환 합니다.|  
|[CContextMenuManager::GetMenuNames](../Topic/CContextMenuManager::GetMenuNames.md)|메뉴 이름 목록을 반환합니다.|  
|[CContextMenuManager::LoadState](../Topic/CContextMenuManager::LoadState.md)|Windows 레지스트리에 저장 바로 가기 메뉴를 로드 합니다.|  
|[CContextMenuManager::ResetState](../Topic/CContextMenuManager::ResetState.md)|컨텍스트 메뉴 관리자에서 바로 가기 메뉴를 해제합니다.|  
|[CContextMenuManager::SaveState](../Topic/CContextMenuManager::SaveState.md)|바로 가기 메뉴는 Windows 레지스트리에 저장 됩니다.|  
|[CContextMenuManager::SetDontCloseActiveMenu](../Topic/CContextMenuManager::SetDontCloseActiveMenu.md)|컨트롤 여부는 `CContextMenuManager` 새 바로 가기 메뉴를 표시 하면 현재 바로 가기 메뉴를 닫습니다.|  
|[CContextMenuManager::ShowPopupMenu](../Topic/CContextMenuManager::ShowPopupMenu.md)|지정 된 바로 가기 메뉴를 표시합니다.|  
|[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md)|지정 된 바로 가기 메뉴를 표시합니다.  선택한 메뉴 명령의 인덱스를 반환합니다.|  
  
## 설명  
 `CContextMenuManager`바로 가기 메뉴를 관리 하 고 일관 된 모양이 있는지 확인 합니다.  
  
 만들어야지 않습니다는 `CContextMenuManager` 수동으로 개체입니다.  프레임 워크 응용 프로그램을 만듭니다를 `CContextMenuManager` 개체입니다.  그러나 호출 해야 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md) 응용 프로그램을 초기화 합니다.  컨텍스트 관리자를 초기화 한 후에 메서드 사용 [CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md) 응용 프로그램 컨텍스트 관리자에 대 한 포인터를 얻을 수 있습니다.  
  
 호출 하 여 런타임에 바로 가기 메뉴를 만들 수 있습니다 `AddMenu`.  첫 번째 받는 사용자 입력 없이 메뉴를 표시 하려면 호출 `ShowPopupMenu`.  `TrackPopupMenu`메뉴를 만들고 사용자 입력을 기다립니다 때 사용 됩니다.  `TrackPopupMenu`사용자를 선택 하지 않고 종료 하는 경우 선택한 명령 또는 0 인덱스를 반환 합니다.  
  
 `CContextMenuManager` 도 저장 하 고 Windows 레지스트리를 상태로 불러올 수 있습니다.  
  
## 예제  
 메뉴에 추가 하는 방법 다음 예제는 `CContextMenuManager` 개체 및 현재 팝업 메뉴를 닫는 방법 때의 `CContextMenuManager` 개체 새 팝업 메뉴를 표시 합니다.  이 코드 조각에 속하지는  [샘플 사용자 지정 페이지](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/CPP/ccontextmenumanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)  
  
## 요구 사항  
 **헤더:** afxcontextmenumanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)