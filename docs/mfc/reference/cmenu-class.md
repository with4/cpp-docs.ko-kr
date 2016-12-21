---
title: "CMenu Class | Microsoft Docs"
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
  - "CMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenu class"
  - "HMENU"
  - "메뉴, 기본 클래스"
  - "메뉴, class"
  - "메뉴, 만들기"
  - "메뉴, 관리"
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows의 집약적 `HMENU`.  
  
## 구문  
  
```  
class CMenu : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMenu::CMenu](../Topic/CMenu::CMenu.md)|`CMenu` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)|이 메뉴의 끝에 새 항목을 추가합니다.|  
|[CMenu::Attach](../Topic/CMenu::Attach.md)|Windows 메뉴 핸들을 첨부 한 `CMenu` 개체입니다.|  
|[CMenu::CheckMenuItem](../Topic/CMenu::CheckMenuItem.md)|옆에 확인 표시가 배치 하거나 메뉴 항목 팝업 메뉴에서 확인 표시를 제거 합니다.|  
|[CMenu::CheckMenuRadioItem](../Topic/CMenu::CheckMenuRadioItem.md)|라디오 단추 메뉴 항목 옆에 두고 라디오 단추 그룹에서 다른 메뉴 항목을 모두 제거 합니다.|  
|[CMenu::CreateMenu](../Topic/CMenu::CreateMenu.md)|빈 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::CreatePopupMenu](../Topic/CMenu::CreatePopupMenu.md)|빈 팝업 메뉴를 만들고 연결 하는 `CMenu` 개체입니다.|  
|[CMenu::DeleteMenu](../Topic/CMenu::DeleteMenu.md)|메뉴에서 지정 된 항목을 삭제합니다.  메뉴 항목에 연결 된 팝업 메뉴가 있는 경우 팝업 메뉴에 대 한 핸들을 소멸 하 고 사용 하 여 메모리를 해제 합니다.|  
|[CMenu::DeleteTempMap](../Topic/CMenu::DeleteTempMap.md)|모든 임시 삭제 `CMenu` 만든 개체는 `FromHandle` 멤버 함수입니다.|  
|[CMenu::DestroyMenu](../Topic/CMenu::DestroyMenu.md)|연결 메뉴를 소멸은 `CMenu` 개체 및 메뉴를 차지 하는 메모리를 해제 합니다.|  
|[CMenu::Detach](../Topic/CMenu::Detach.md)|Windows 메뉴 핸들에서 분리 된 `CMenu` 개체 및 핸들을 반환 합니다.|  
|[CMenu::DrawItem](../Topic/CMenu::DrawItem.md)|소유자가 그린 메뉴 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.|  
|[CMenu::EnableMenuItem](../Topic/CMenu::EnableMenuItem.md)|활성화, 비활성화, 또는 어둡게 \(회색\)의 메뉴 항목입니다.|  
|[CMenu::FromHandle](../Topic/CMenu::FromHandle.md)|반환에 대 한 포인터는 `CMenu` Windows 메뉴 핸들을 지정 하는 개체입니다.|  
|[CMenu::GetDefaultItem](../Topic/CMenu::GetDefaultItem.md)|지정 된 메뉴의 기본 메뉴 항목을 결정합니다.|  
|[CMenu::GetMenuContextHelpId](../Topic/CMenu::GetMenuContextHelpId.md)|메뉴와 연결 된 도움말 컨텍스트 ID를 검색 합니다.|  
|[CMenu::GetMenuInfo](../Topic/CMenu::GetMenuInfo.md)|특정 메뉴에 대 한 정보를 검색합니다.|  
|[CMenu::GetMenuItemCount](../Topic/CMenu::GetMenuItemCount.md)|팝업 또는 최상위 메뉴 항목의 수를 결정합니다.|  
|[CMenu::GetMenuItemID](../Topic/CMenu::GetMenuItemID.md)|지정 된 위치에 있는 메뉴 항목의 메뉴 항목 식별자를 가져옵니다.|  
|[CMenu::GetMenuItemInfo](../Topic/CMenu::GetMenuItemInfo.md)|메뉴 항목에 대 한 정보를 검색합니다.|  
|[CMenu::GetMenuState](../Topic/CMenu::GetMenuState.md)|팝업 메뉴에서 지정 된 메뉴 항목 또는 항목의 상태를 반환합니다.|  
|[CMenu::GetMenuString](../Topic/CMenu::GetMenuString.md)|레이블이 지정 된 메뉴 항목을 검색합니다.|  
|[CMenu::GetSafeHmenu](../Topic/CMenu::GetSafeHmenu.md)|반환 된 `m_hMenu` 이 래핑 `CMenu` 개체.|  
|[CMenu::GetSubMenu](../Topic/CMenu::GetSubMenu.md)|팝업 메뉴에 대 한 포인터를 검색합니다.|  
|[CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)|메뉴를 이동 하는 다른 항목의 지정 된 위치에 새 메뉴 항목을 삽입 합니다.|  
|[CMenu::InsertMenuItem](../Topic/CMenu::InsertMenuItem.md)|메뉴의 지정 된 위치에 새 메뉴 항목을 삽입합니다.|  
|[CMenu::LoadMenu](../Topic/CMenu::LoadMenu.md)|메뉴 리소스를 실행 파일에서 로드 되 고 추가 하는 `CMenu` 개체입니다.|  
|[CMenu::LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)|메뉴는 메뉴 템플릿에서 메모리에 로드를 연결 하 고 있는 `CMenu` 개체입니다.|  
|[CMenu::MeasureItem](../Topic/CMenu::MeasureItem.md)|소유자가 그린 메뉴를 만들면 메뉴 크기를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)|기존 메뉴 항목의 지정 된 위치를 변경합니다.|  
|[CMenu::RemoveMenu](../Topic/CMenu::RemoveMenu.md)|지정 된 메뉴에서 메뉴 항목에는 연결 된 팝업 메뉴를 삭제합니다.|  
|[CMenu::SetDefaultItem](../Topic/CMenu::SetDefaultItem.md)|지정 된 메뉴의 기본 메뉴 항목을 설정합니다.|  
|[CMenu::SetMenuContextHelpId](../Topic/CMenu::SetMenuContextHelpId.md)|메뉴에 연결 될 도움말 컨텍스트 ID를 설정 합니다.|  
|[CMenu::SetMenuInfo](../Topic/CMenu::SetMenuInfo.md)|특정 메뉴에서 정보를 설정합니다.|  
|[CMenu::SetMenuItemBitmaps](../Topic/CMenu::SetMenuItemBitmaps.md)|지정 된 확인 표시 비트맵 메뉴 항목과 연결합니다.|  
|[CMenu::SetMenuItemInfo](../Topic/CMenu::SetMenuItemInfo.md)|메뉴 항목에 대 한 정보를 변경합니다.|  
|[CMenu::TrackPopupMenu](../Topic/CMenu::TrackPopupMenu.md)|부동 팝업 메뉴에 지정 된 위치에 표시 하 고 팝업 메뉴에서 선택 항목을 추적 합니다.|  
|[CMenu::TrackPopupMenuEx](../Topic/CMenu::TrackPopupMenuEx.md)|부동 팝업 메뉴에 지정 된 위치에 표시 하 고 팝업 메뉴에서 선택 항목을 추적 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CMenu::operator HMENU](../Topic/CMenu::operator%20HMENU.md)|메뉴 개체의 핸들을 검색합니다.|  
|[CMenu::operator \!\=](../Topic/CMenu::operator%20!=.md)|두 메뉴 개체가 같은지 여부를 결정 합니다.|  
|[CMenu::operator \=\=](../Topic/CMenu::operator%20==.md)|두 메뉴 개체가 같은지 여부를 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMenu::m\_hMenu](../Topic/CMenu::m_hMenu.md)|핸들 연결 Windows 메뉴에 지정 된 `CMenu` 개체.|  
  
## 설명  
 만들기, 추적, 업데이트 및 삭제 메뉴에 대 한 멤버 함수를 제공 합니다.  
  
 만들기는 `CMenu` 개체에 로컬 스택 프레임에 다음 호출 `CMenu`의 필요에 따라 새 메뉴를 조작 하는 멤버 함수입니다.  그런 다음 호출  [CWnd::SetMenu](../Topic/CWnd::SetMenu.md) 메뉴 창에 설정 하려면 뒤 즉시 호출 하는 `CMenu` 개체의  [분리](../Topic/CMenu::Detach.md) 멤버 함수.  `CWnd::SetMenu` 멤버 함수 창의 메뉴에 새 메뉴 설정 메뉴 변경 내용을 반영 하도록 다시 그릴 수 있도록 창 및도 창에 메뉴의 소유권을 전달 합니다.  호출을  **분리** 분리는 `HMENU` 에서 `CMenu` 개체 수 때 로컬 `CMenu` 변수 범위를 벗어나면 전달의 `CMenu` 개체의 소멸자가 더 이상 소유 하는 메뉴를 파괴 하려고 시도 하지.  창이 소멸 되 면 메뉴 자체는 자동으로 소멸 됩니다.  
  
 사용할 수는  [LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md) 멤버 함수는 메뉴 템플릿에서 메모리에 리소스를 호출 하 여 만든 메뉴 만드는  [LoadMenu](../Topic/CMenu::LoadMenu.md) 보다 쉽게 유지 및 메뉴 리소스 생성 및 메뉴 편집기에서 수정할 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC 샘플 CTRLTEST](../../top/visual-cpp-samples.md)   
 [MFC DYNAMENU 샘플](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)