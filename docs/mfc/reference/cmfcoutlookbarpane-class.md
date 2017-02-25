---
title: "CMFCOutlookBarPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCOutlookBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanBeRestored method"
  - "CMFCOutlookBarPane class"
  - "Dock method"
  - "IsChangeState method"
  - "OnBeforeFloat method"
  - "RestoreOriginalstate method"
  - "SmartUpdate method"
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCOutlookBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 컨트롤에서 파생 된 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) 는 Outlook 표시줄에 삽입할 수 있습니다 \([CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)\).  Outlook 표시줄 창에 큰 단추를 열을 포함 되어 있습니다.  창 보다 클 경우 사용자가 단추 목록을 위아래로 스크롤할 수 있습니다.  사용자가 Outlook 표시줄 창에서 Outlook 표시줄에서 분리 되 면 부동 소수점 수 또는 주 프레임 창에 도킹 합니다.  
  
## 구문  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|기본 생성자입니다.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCOutlookBarPane::AddButton](../Topic/CMFCOutlookBarPane::AddButton.md)|Outlook 표시줄 창에 단추를 추가합니다.|  
|[CMFCOutlookBarPane::CanBeAttached](../Topic/CMFCOutlookBarPane::CanBeAttached.md)|창 다른 창 또는 프레임 창에 도킹 될 수 있는지 여부를 결정 합니다.  \(재정의 [CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md).\)|  
|`CMFCOutlookBarPane::CanBeRestored`|시스템 도구 모음을 원래 상태로 사용자 지정 후 복원할 수 여부를 결정 합니다.  \(재정의 [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCOutlookBarPane::ClearAll](../Topic/CMFCOutlookBarPane::ClearAll.md)|Outlook 표시줄 창에서 이미지를 사용 하는 리소스를 해제 합니다.|  
|[CMFCOutlookBarPane::Create](../Topic/CMFCOutlookBarPane::Create.md)|Outlook 표시줄 창을 만듭니다.|  
|`CMFCOutlookBarPane::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCOutlookBarPane::Dock`|Outlook 표시줄 창에 도킹 하려면 프레임 워크에서 호출 됩니다. \(재정의 `CPane::Dock`.\)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](../Topic/CMFCOutlookBarPane::EnablePageScrollMode.md)|Outlook 표시줄 창에서 스크롤 화살표 단추 또는 페이지 단추 목록 이동 여부를 지정 합니다.|  
|[CMFCOutlookBarPane::GetRegularColor](../Topic/CMFCOutlookBarPane::GetRegularColor.md)|Outlook 표시줄 창 \(선택 되지 않은\) 텍스트 색을 반환합니다.|  
|`CMFCOutlookBarPane::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](../Topic/CMFCOutlookBarPane::IsBackgroundTexture.md)|Outlook 표시줄 창에 로드 되는 배경 이미지 인지 여부를 확인 합니다.|  
|`CMFCOutlookBarPane::IsChangeState`|부동 창이 도킹 될 수 있는지 여부를 결정 합니다.  \(재정의 `CPane::IsChangeState`.\)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](../Topic/CMFCOutlookBarPane::IsDrawShadedHighlight.md)|단추를 강조 표시 하 고 배경 이미지를 표시 하는 경우 단추 테두리가 회색 인지 확인 합니다.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|창에 대 한 float 될 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CMFCOutlookBarPane::RemoveButton](../Topic/CMFCOutlookBarPane::RemoveButton.md)|지정 된 명령 ID가 있는 단추를 제거 합니다.|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|도구 모음을 원래 상태로 복원합니다.  \(재정의 [CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md).\)|  
|[CMFCOutlookBarPane::SetBackColor](../Topic/CMFCOutlookBarPane::SetBackColor.md)|배경 색을 설정 합니다.|  
|[CMFCOutlookBarPane::SetBackImage](../Topic/CMFCOutlookBarPane::SetBackImage.md)|배경 이미지를 설정합니다.|  
|[CMFCOutlookBarPane::SetDefaultState](../Topic/CMFCOutlookBarPane::SetDefaultState.md)|Outlook 표시줄 창에 원래 단추 집합에 다시 설정합니다.|  
|[CMFCOutlookBarPane::SetExtraSpace](../Topic/CMFCOutlookBarPane::SetExtraSpace.md)|Outlook 표시줄 창에서 단추를 사용 하는 안쪽의 픽셀 수를 설정 합니다.|  
|[CMFCOutlookBarPane::SetTextColor](../Topic/CMFCOutlookBarPane::SetTextColor.md)|Outlook 표시줄 창에 일반 및 강조 표시 된 텍스트의 색을 설정합니다.|  
|[CMFCOutlookBarPane::SetTransparentColor](../Topic/CMFCOutlookBarPane::SetTransparentColor.md)|Outlook 표시줄 창에 대 한 투명 색을 설정합니다.|  
|`CMFCOutlookBarPane::SmartUpdate`|내부적으로 Outlook 표시줄을 업데이트 하는 데 사용.  \(재정의 `CMFCToolBar::SmartUpdate`.\)|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](../Topic/CMFCOutlookBarPane::EnableContextMenuItems.md)|바로 가기 메뉴 항목을 사용자 지정 모드에서 표시할지 지정 합니다.|  
|[CMFCOutlookBarPane::RemoveAllButtons](../Topic/CMFCOutlookBarPane::RemoveAllButtons.md)|Outlook 표시줄 창에서 모든 단추를 제거합니다.  \(재정의 [CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md).\)|  
  
## 설명  
 Outlook 표시줄을 구현 하는 방법에 대 한 자세한 내용은 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Outlook 표시줄의 예를 들어 OutlookDemo 예제 프로젝트를 참조 하십시오.  
  
## 예제  
 다양 한 메서드를 사용 하는 방법 다음 예제는 `CMFCOutlookBarPane` 클래스입니다.  이 예제는 Outlook 표시줄 창, 페이지 스크롤 모드 사용, 도킹을 사용 만들고 Outlook 표시줄의 배경색을 설정 하는 방법.  이 코드 조각에 속하지는  [Outlook 다중 뷰 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## 요구 사항  
 **헤더:** afxoutlookbarpane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)