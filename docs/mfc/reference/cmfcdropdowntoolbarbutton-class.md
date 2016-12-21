---
title: "CMFCDropDownToolbarButton Class | Microsoft Docs"
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
  - "CMFCDropDownToolbarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolbarButton class"
  - "OnCancelMode method"
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolbarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

유형을 클릭 하면 일반 단추 처럼 동작 하는 도구 모음 단추  그러나 드롭다운 도구 모음 열립니다 \([CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) 클릭 하 고 도구 모음 단추를 누르고 경우.  
  
## 구문  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)|`CMFCDropDownToolbarButton` 개체를 생성합니다.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCDropDownToolbarButton::CopyFrom](../Topic/CMFCDropDownToolbarButton::CopyFrom.md)|현재 단추를 다른 도구 모음 단추의 속성을 복사합니다.  \(재정의 [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCDropDownToolbarButton::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](../Topic/CMFCDropDownToolbarButton::DropDownToolbar.md)|드롭다운 도구 모음을 엽니다.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](../Topic/CMFCDropDownToolbarButton::ExportToMenuButton.md)|텍스트 도구 모음 단추에서는 메뉴에 복사 합니다.  \(재정의 [CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md).\)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](../Topic/CMFCDropDownToolbarButton::GetDropDownToolBar.md)|드롭다운 도구 모음 단추와 관련 된 검색 합니다.|  
|`CMFCDropDownToolbarButton::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCDropDownToolbarButton::IsDropDown](../Topic/CMFCDropDownToolbarButton::IsDropDown.md)|도구 모음 드롭다운이 현재 열려 있는지 여부를 결정 합니다.|  
|[CMFCDropDownToolbarButton::IsExtraSize](../Topic/CMFCDropDownToolbarButton::IsExtraSize.md)|단추는 확장된 된 테두리가 표시 될 수 있는지를 결정 합니다.  \(재정의 [CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md).\)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](../Topic/CMFCDropDownToolbarButton::OnCalculateSize.md)|지정 된 디바이스 컨텍스트 및 도킹 상태 단추의 크기를 계산 하는 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|처리 하는 프레임 워크에서 호출을  [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) 메시지.  \(재정의 `CMCToolBarButton::OnCancelMode`.\)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](../Topic/CMFCDropDownToolbarButton::OnChangeParentWnd.md)|새 도구 모음에 단추를 삽입 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCDropDownToolbarButton::OnClick](../Topic/CMFCDropDownToolbarButton::OnClick.md)|마우스 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCDropDownToolbarButton::OnClickUp](../Topic/CMFCDropDownToolbarButton::OnClickUp.md)|마우스 단추를 놓을 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md).\)|  
|[CMFCDropDownToolbarButton::OnContextHelp](../Topic/CMFCDropDownToolbarButton::OnContextHelp.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_HELPHITTEST` 메시지.  \(재정의 [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md).\)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](../Topic/CMFCDropDownToolbarButton::OnCustomizeMenu.md)|응용 프로그램 상위 도구 모음에 바로 가기 메뉴를 표시할 때 제공 된 메뉴를 수정 합니다.  \(재정의 [CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md).\)|  
|[CMFCDropDownToolbarButton::OnDraw](../Topic/CMFCDropDownToolbarButton::OnDraw.md)|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리려면 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](../Topic/CMFCDropDownToolbarButton::OnDrawOnCustomizeList.md)|단추를 그리려면 프레임 워크에 의해 호출의  **명령** 창에  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCDropDownToolbarButton::Serialize](../Topic/CMFCDropDownToolbarButton::Serialize.md)|이 개체는 보관 파일에서 읽거나 아카이브 수를 씁니다.  \(재정의 [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](../Topic/CMFCDropDownToolbarButton::SetDefaultCommand.md)|단추를 클릭할 때 프레임 워크를 사용 하 여 기본 명령을 설정 합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCDropDownToolbarButton::m\_uiShowBarDelay](../Topic/CMFCDropDownToolbarButton::m_uiShowBarDelay.md)|드롭다운 도구 모음에 표시 되는 사용자가 마우스 단추를 누르고 있어야 하는 시간을 지정 합니다.|  
  
## 설명  
 A `CMFCDropDownToolBarButton` 단추 오른쪽 아래 모서리에 작은 화살표가는 일반 단추는 다릅니다.  사용자 도구 모음에서 드롭다운 단추를 선택 하면 프레임 워크는 최상위 도구 모음 단추 \(오른쪽 아래 모서리에 작은 화살표가 있는 단추\)에 해당 아이콘이 표시 됩니다.  
  
 드롭다운 도구 모음을 구현 하는 방법에 대 한 자세한 내용은 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 `CMFCDropDownToolBarButton` 개체를 내보낼 수는 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) 개체 및 팝업 메뉴와 메뉴 단추를 표시 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## 요구 사항  
 **헤더:**  afxdropdowntoolbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)