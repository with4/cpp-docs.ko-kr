---
title: "CMouseManager Class | Microsoft Docs"
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
  - "CMouseManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMouseManager class"
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMouseManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다른 명령으로 특정 연결할 수 있도록  [CView](../../mfc/reference/cview-class.md) 내 보기를 클릭할 때 개체.  
  
## 구문  
  
```  
class CMouseManager : public CObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMouseManager::AddView](../Topic/CMouseManager::AddView.md)|추가 된 `CView` 개체의  **사용자 지정** 대화 상자.  **사용자 지정** 명령을 사용 하 여 각 나열 된 보기를 두 번 클릭을 연결 하는 사용자가 대화 상자를 있습니다.|  
|[CMouseManager::GetViewDblClickCommand](../Topic/CMouseManager::GetViewDblClickCommand.md)|제공 된 뷰 내부를 클릭할 때 실행 될 명령을 반환 합니다.|  
|[CMouseManager::GetViewIconId](../Topic/CMouseManager::GetViewIconId.md)|제공 된 보기 ID와 관련 된 아이콘을 반환 합니다.|  
|[CMouseManager::GetViewIdByName](../Topic/CMouseManager::GetViewIdByName.md)|제공 된 뷰 이름으로 연결 된 뷰 ID를 반환 합니다.|  
|[CMouseManager::GetViewNames](../Topic/CMouseManager::GetViewNames.md)|모든 추가 뷰 이름 목록을 검색합니다.|  
|[CMouseManager::LoadState](../Topic/CMouseManager::LoadState.md)|로드는 `CMouseManager` Windows 레지스트리에서 상태.|  
|[CMouseManager::SaveState](../Topic/CMouseManager::SaveState.md)|기록에 `CMouseManager` Windows 레지스트리에 상태.|  
|[CMouseManager::SetCommandForDblClk](../Topic/CMouseManager::SetCommandForDblClk.md)|제공 된 명령 및 제공 된 보기를 연결합니다.|  
  
## 설명  
 `CMouseManager` 클래스의 컬렉션을 유지 관리 `CView` 개체입니다.  각 보기의 이름 및 ID 식별  이러한 보기에 나와 있는  **사용자 지정** 대화 상자.  사용자 뷰를 통해 관련 된 명령을 변경할 수 있는  **사용자 지정** 대화 상자.  해당 보기에서 두 번 클릭할 때 관련 된 명령이 실행 됩니다.  코딩 관점에서이 지원 하 여 처리 해야는 `WM_LBUTTONDBLCLK` 메시지와 호출의 [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md) 함수는 코드에서 `CView` 개체.  
  
 만들어야지 않습니다는 `CMouseManager` 수동으로 개체입니다.  응용 프로그램 프레임 워크에 의해 만들어지지 것입니다.  사용자 응용 프로그램이 있는 경우에 자동으로 소멸 됩니다.  마우스 관리자를 응용 프로그램에 대 한 포인터를 가져오려면 호출 [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMouseManager](../../mfc/reference/cmousemanager-class.md)  
  
## 요구 사항  
 **헤더:** afxmousemanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)