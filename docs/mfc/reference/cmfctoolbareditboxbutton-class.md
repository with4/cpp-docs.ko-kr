---
title: "CMFCToolBarEditBoxButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "OnDrawOnCustomizeList"
  - "OnDraw"
  - "CMFCToolBarEditBoxButton::OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton.SetACCData"
  - "CMFCToolBarEditBoxButton::OnDraw"
  - "OnCalculateSize"
  - "SetACCData"
  - "CMFCToolBarEditBoxButton"
  - "CMFCToolBarEditBoxButton::SetACCData"
  - "CMFCToolBarEditBoxButton::Serialize"
  - "CMFCToolBarEditBoxButton.OnDraw"
  - "CMFCToolBarEditBoxButton.OnDrawOnCustomizeList"
  - "CMFCToolBarEditBoxButton::OnCalculateSize"
  - "Serialize"
  - "CMFCToolBarEditBoxButton.Serialize"
  - "CMFCToolBarEditBoxButton.OnCalculateSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarEditBoxButton class"
  - "OnCalculateSize method"
  - "OnDraw method"
  - "OnDrawOnCustomizeList method"
  - "Serialize method"
  - "SetACCData method"
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCToolBarEditBoxButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

편집 컨트롤을 포함 하는 도구 모음 단추 \([CEdit Class](../../mfc/reference/cedit-class.md)\).  
  
## 구문  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](../Topic/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton.md)|`CMFCToolBarEditBoxButton` 개체를 생성합니다.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](../Topic/CMFCToolBarEditBoxButton::CanBeStretched.md)|사용자 중 사용자 지정 단추를 늘릴 수 있는지 여부를 지정 합니다.  \(재정의 [CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md).\)|  
|[CMFCToolBarEditBoxButton::CopyFrom](../Topic/CMFCToolBarEditBoxButton::CopyFrom.md)|현재 단추를 다른 도구 모음 단추의 속성을 복사합니다.  \(재정의 [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](../Topic/CMFCToolBarEditBoxButton::CreateEdit.md)|새 편집 컨트롤에서 단추를 만듭니다.|  
|`CMFCToolBarEditBoxButton::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCToolBarEditBoxButton::GetByCmd](../Topic/CMFCToolBarEditBoxButton::GetByCmd.md)|첫 번째 검색 `CMFCToolBarEditBoxButton` 지정 된 명령 ID가 응용 프로그램 개체|  
|[CMFCToolBarEditBoxButton::GetContentsAll](../Topic/CMFCToolBarEditBoxButton::GetContentsAll.md)|지정 된 명령 id가 있는 첫 번째 편집 상자 도구 모음 컨트롤의 텍스트를 검색 합니다.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](../Topic/CMFCToolBarEditBoxButton::GetContextMenuID.md)|단추와 연결 된 바로 가기 메뉴의 리소스 ID를 검색 합니다.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](../Topic/CMFCToolBarEditBoxButton::GetEditBorder.md)|편집 상자 단추 부분 편집의 경계 사각형을 검색합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](../Topic/CMFCToolBarEditBoxButton::GetEditBox.md)|단추에 포함 된 편집 컨트롤에 대 한 포인터를 반환 합니다.|  
|[CMFCToolBarEditBoxButton::GetHwnd](../Topic/CMFCToolBarEditBoxButton::GetHwnd.md)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다.  \(재정의 [CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md).\)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](../Topic/CMFCToolBarEditBoxButton::GetInvalidateRect.md)|영역을 그려야 단추의 클라이언트 영역을 검색 합니다.  \(재정의 [CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md).\)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](../Topic/CMFCToolBarEditBoxButton::HaveHotBorder.md)|단추를 클릭할 때 단추 테두리가 표시 되는지 여부를 결정 합니다.  \(재정의 [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](../Topic/CMFCToolBarEditBoxButton::IsFlatMode.md)|편집 상자 단추 플랫 스타일 있는지 여부를 결정 합니다.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](../Topic/CMFCToolBarEditBoxButton::NotifyCommand.md)|단추를 처리 하는지 여부를 지정 하는  [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지.  \(재정의 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md).\)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](../Topic/CMFCToolBarEditBoxButton::OnAddToCustomizePage.md)|단추를 추가 하면 프레임 워크에서 호출을  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md).\)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|지정 된 디바이스 컨텍스트 및 도킹 상태 단추의 크기를 계산 하는 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](../Topic/CMFCToolBarEditBoxButton::OnChangeParentWnd.md)|새 도구 모음에 단추를 삽입 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarEditBoxButton::OnClick](../Topic/CMFCToolBarEditBoxButton::OnClick.md)|마우스 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](../Topic/CMFCToolBarEditBoxButton::OnCtlColor.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_CTLCOLOR` 메시지.  \(재정의 [CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md).\)|  
|`CMFCToolBarEditBoxButton::OnDraw`|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리려면 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|단추를 그리려면 프레임 워크에 의해 호출의  **명령** 창에  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](../Topic/CMFCToolBarEditBoxButton::OnGlobalFontsChanged.md)|전체 글꼴을 변경할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md).\)|  
|[CMFCToolBarEditBoxButton::OnMove](../Topic/CMFCToolBarEditBoxButton::OnMove.md)|상위 도구 모음을 이동 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md).\)|  
|[CMFCToolBarEditBoxButton::OnShow](../Topic/CMFCToolBarEditBoxButton::OnShow.md)|단추 될 때 프레임 워크에서 보이거나 보이지 않는 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md).\)|  
|[CMFCToolBarEditBoxButton::OnSize](../Topic/CMFCToolBarEditBoxButton::OnSize.md)|프레임 워크에서 상위 도구 모음 크기 변경 위치 및이 변경 하면 크기를 변경 하려면 단추를 때 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md).\)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](../Topic/CMFCToolBarEditBoxButton::OnUpdateToolTip.md)|상위 도구 모음 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md).\)|  
|`CMFCToolBarEditBoxButton::Serialize`|이 개체는 보관 파일에서 읽거나 아카이브 수를 씁니다.  \(재정의 [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|`CMFCToolBarEditBoxButton::SetACCData`|제공 된 채웁니다 `CAccessibilityData` 내게 필요한 옵션 도구 모음 단추에서 데이터로 개체입니다.  \(재정의 [CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md).\)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](../Topic/CMFCToolBarEditBoxButton::SetContents.md)|단추 편집 컨트롤에 텍스트를 설정합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](../Topic/CMFCToolBarEditBoxButton::SetContentsAll.md)|에 지정 된 명령 ID가 해당 단추를 편집 컨트롤에 텍스트를 설정 하는 편집 컨트롤 단추를 찾습니다.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](../Topic/CMFCToolBarEditBoxButton::SetContextMenuID.md)|단추와 연결 된 바로 가기 메뉴의 리소스 ID를 지정 합니다.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](../Topic/CMFCToolBarEditBoxButton::SetFlatMode.md)|응용 프로그램에서의 평면 스타일 모양을 편집 상자 단추를 지정합니다.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](../Topic/CMFCToolBarEditBoxButton::SetStyle.md)|단추 스타일을 지정합니다.  \(재정의 [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).\)|  
  
## 설명  
 편집 상자 단추를 도구 모음에 추가 하려면 다음과이 같이 하십시오.  
  
 1.  부모 리소스 도구 모음 단추에 대 한 더미 리소스 ID를 예약 합니다.  
  
 2.  `CMFCToolBarEditBoxButton` 개체를 생성합니다.  
  
 3.  처리 된 메시지 처리기에서는 `AFX_WM_RESETTOOLBAR` 메시지, 새 콤보 상자 단추를 사용 하 여 더미 단추를 대체 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
 자세한 내용은 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCToolBarEditBoxButton` 클래스입니다.  예제 사용자 수 중 사용자 지정 단추를 늘이기, 단추를 클릭할 때 단추 테두리가 표시 되도록 지정, 텍스트 상자 컨트롤에 텍스트를 설정, 응용 프로그램에서 편집 상자 단추의 평면 스타일 모양을 지정과 도구 모음 편집 상자 컨트롤의 스타일을 지정 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/CPP/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbareditboxbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)