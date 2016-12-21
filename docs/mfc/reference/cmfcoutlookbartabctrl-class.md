---
title: "CMFCOutlookBarTabCtrl Class | Microsoft Docs"
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
  - "CMFCOutlookBarTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBarTabCtrl class"
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭 컨트롤의 시각적 모양이 있는  **탐색 창** Microsoft Outlook에서.  
  
## 구문  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|기본 생성자입니다.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md)|Outlook 표시줄에서 새 탭으로 Windows 컨트롤을 추가합니다.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|프레임 워크에서 호출 때 나타나는 입력란의 크기를 결정 하는 탭을 이름을 바꿉니다.  \(재정의 `CMFCBaseTabCtrl::CalcRectEdit`.\)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons.md)|프레임 워크에서 크기 조정 작업 중에 현재 표시 된 것 보다 적은 Outlook 표시줄 탭 페이지 단추를 표시할 수 있으면 확인 이라고 합니다.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowMorePageButtons.md)|프레임 워크에서 현재 나타나는 것 보다 더 많은 Outlook 표시줄 탭 페이지 단추를 표시할 수 있으면 확인 하는 크기 조정 작업 중 이라고 합니다.|  
|[CMFCOutlookBarTabCtrl::Create](../Topic/CMFCOutlookBarTabCtrl::Create.md)|Outlook 표시줄 탭 컨트롤을 만듭니다.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](../Topic/CMFCOutlookBarTabCtrl::EnableAnimation.md)|활성 탭 사이 전환할 때 발생 하는 애니메이션을 사용할 수 있는지 여부를 지정 합니다.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](../Topic/CMFCOutlookBarTabCtrl::EnableInPlaceEdit.md)|사용자가 Outlook 표시줄의 단추 탭의 텍스트 레이블을 수정할 수 있는지 여부를 지정 합니다.  \(재정의 [CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md).\)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](../Topic/CMFCOutlookBarTabCtrl::EnableScrollButtons.md)|단추 Outlook 표시줄 창에서 스크롤할 수 있도록 단추를 사용 하는 프레임 워크에서 호출 합니다.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|지정 된 지점을 포함 하는 창으로 식별 합니다.  \(재정의 [CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md).\)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](../Topic/CMFCOutlookBarTabCtrl::GetBorderSize.md)|Outlook의 탭 컨트롤의 테두리 크기를 반환합니다.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|크기 및 위치 탭 컨트롤의 탭 영역을 검색합니다.  \(재정의 [CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::GetVisiblePageButtons.md)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](../Topic/CMFCOutlookBarTabCtrl::IsAnimation.md)|활성 탭 사이 전환할 때 발생 하는 애니메이션을 사용할 수 있는지 여부를 결정 합니다.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](../Topic/CMFCOutlookBarTabCtrl::IsMode2003.md)|Microsoft Outlook 2003 에뮬레이션 모드로 Outlook 표시줄 탭 컨트롤 인지 확인 합니다.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|포인트 탭 영역 내부에 있는지 확인 합니다.  \(재정의 [CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md).\)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|탭 분리 가능한 지 확인 합니다.  \(재정의 [CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md).\)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|탭을 삽입 하거나 제거 하면 프레임 워크에서 호출 됩니다.  \(재정의 `CMFCBaseTabCtrl::OnChangeTabs`.\)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons.md)|표시 되는 탭 페이지 단추 수 줄이기 위해 프레임 워크에서 호출 됩니다.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowMorePageButtons.md)|볼 수 있는 탭 페이지 단추의 수를 늘리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](../Topic/CMFCOutlookBarTabCtrl::OnShowOptions.md)|표시는  **탐색 창 옵션** 대화.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|탭 컨트롤의 내부 레이아웃을 다시 계산합니다.  \(재정의 [CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md).\)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md)|현재 탭을 설정합니다.  \(재정의 [CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md).\)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](../Topic/CMFCOutlookBarTabCtrl::SetBorderSize.md)|Outlook의 탭 컨트롤의 테두리 크기를 설정합니다.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](../Topic/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign.md)|Outlook 표시줄에 있는 탭 단추 텍스트 레이블의 맞춤을 설정합니다.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md)|Outlook 2003 모드에서 Outlook 표시줄의 아래쪽에 표시 되는 아이콘에 포함 된 비트맵을 설정 \(참조 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)\).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::SetVisiblePageButtons.md)||  
  
## 설명  
 도킹 지원 Outlook 표시줄을 만들 수는 `CMFCOutlookBar` Outlook 표시줄 탭 컨트롤을 호스트 하는 개체입니다.  자세한 내용은 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)를 참조하십시오.  
  
## 예제  
 초기화 하는 다음 예제는 `CMFCOutlookBarTabCtrl` 개체 및 다양 한 메서드를 사용 하는 `CMFCOutlookBarTabCtrl` 클래스.  Outlook 표시줄 탭 페이지 단추의 텍스트 레이블에 현재 위치에서 편집 기능을 설정, 애니메이션 설정 단추 Outlook 표시줄 창에서 스크롤하여 Outlook 탭 컨트롤의 테두리 크기를 설정 하 고 Outlook 표시줄에 있는 탭 단추 레이블의 텍스트 맞춤을 설정할 수 있게 스크롤 핸들을 사용 하는 방법의 예제를 보여 줍니다.  이 코드 조각에 속해 있는  [Outlook 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/CPP/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/CPP/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxoutlookbartabctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)