---
title: "CMFCToolBarDateTimeCtrl Class | Microsoft Docs"
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
  - "CMFCToolBarDateTimeCtrl::OnDraw"
  - "OnDraw"
  - "CMFCToolBarDateTimeCtrl.Serialize"
  - "CMFCToolBarDateTimeCtrl.OnSize"
  - "CMFCToolBarDateTimeCtrl.OnDrawOnCustomizeList"
  - "OnSize"
  - "OnCalculateSize"
  - "CMFCToolBarDateTimeCtrl"
  - "CMFCToolBarDateTimeCtrl::OnCalculateSize"
  - "SetStyle"
  - "CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList"
  - "CMFCToolBarDateTimeCtrl.OnDraw"
  - "CMFCToolBarDateTimeCtrl.SetStyle"
  - "CMFCToolBarDateTimeCtrl::SetStyle"
  - "CMFCToolBarDateTimeCtrl.OnCalculateSize"
  - "CMFCToolBarDateTimeCtrl::Serialize"
  - "CMFCToolBarDateTimeCtrl::OnSize"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarDateTimeCtrl class"
  - "OnCalculateSize method"
  - "OnDraw method"
  - "OnDrawOnCustomizeList method"
  - "OnSize method"
  - "Serialize method"
  - "SetStyle method"
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCToolBarDateTimeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

날짜 및 시간 선택 컨트롤 포함 된 도구 모음 단추.  
  
## 구문  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](../Topic/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl.md)|`CMFCToolBarDateTimeCtrl` 개체를 생성합니다.|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](../Topic/CMFCToolBarDateTimeCtrl::CanBeStretched.md)|사용자 중 사용자 지정 단추를 늘릴 수 있는지 여부를 지정 합니다.  \(재정의 [CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md).\)|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](../Topic/CMFCToolBarDateTimeCtrl::CopyFrom.md)|현재 단추를 다른 도구 모음 단추의 속성을 복사합니다.  \(재정의 [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md).\)|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|다음에 사용하도록 예약됩니다.|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|텍스트 도구 모음 단추에서는 메뉴에 복사 합니다.|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](../Topic/CMFCToolBarDateTimeCtrl::GetByCmd.md)|첫 번째 검색 `CMFCToolBarDateTimeCtrl` 지정 된 명령 ID가 응용 프로그램 개체|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](../Topic/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl.md)|날짜 및 시간 선택 컨트롤에 포인터를 반환 합니다.|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](../Topic/CMFCToolBarDateTimeCtrl::GetHwnd.md)|도구 모음 단추와 연결 된 창 핸들을 검색 합니다.  \(재정의 [CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md).\)|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCToolBarDateTimeCtrl::GetTime](../Topic/CMFCToolBarDateTimeCtrl::GetTime.md)|날짜 및 시간 선택 컨트롤에서 선택한 시간을 가져오고 지정 된 배치  [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조.|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](../Topic/CMFCToolBarDateTimeCtrl::GetTimeAll.md)|지정 된 명령 ID가 시간 선택 컨트롤 단추에서 선택한 시간을 반환 합니다.|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](../Topic/CMFCToolBarDateTimeCtrl::HaveHotBorder.md)|사용자가 단추를 선택할 때 테두리 단추를 표시할지 여부를 결정 합니다.  \(재정의 [CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md).\)|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](../Topic/CMFCToolBarDateTimeCtrl::NotifyCommand.md)|단추를 처리 하는지 여부를 지정 하는  [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) 메시지.  \(재정의 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](../Topic/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage.md)|단추를 추가 하면 프레임 워크에서 호출을  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|지정 된 디바이스 컨텍스트 및 도킹 상태 단추의 크기를 계산 하는 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](../Topic/CMFCToolBarDateTimeCtrl::OnChangeParentWnd.md)|새 도구 모음에 단추를 삽입 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnClick](../Topic/CMFCToolBarDateTimeCtrl::OnClick.md)|컨트롤을 클릭할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](../Topic/CMFCToolBarDateTimeCtrl::OnCtlColor.md)|상위 도구 모음을 처리할 때 프레임 워크에 의해 호출 된 `WM_CTLCOLOR` 메시지.  \(재정의 [CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|지정 된 스타일 및 옵션을 사용 하 여 단추를 그리려면 프레임 워크에서 호출 합니다.  \(재정의 [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|단추를 그리려면 프레임 워크에 의해 호출의  **명령** 창에  **사용자 지정** 대화 상자.  \(재정의 [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](../Topic/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged.md)|전체 글꼴을 변경할 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnMove](../Topic/CMFCToolBarDateTimeCtrl::OnMove.md)|상위 도구 모음을 이동 하면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnShow](../Topic/CMFCToolBarDateTimeCtrl::OnShow.md)|단추 될 때 프레임 워크에서 보이거나 보이지 않는 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md).\)|  
|`CMFCToolBarDateTimeCtrl::OnSize`|프레임 워크에서 상위 도구 모음 크기 변경 위치 및이 변경 하면 크기를 변경 하려면 단추를 때 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md).\)|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](../Topic/CMFCToolBarDateTimeCtrl::OnUpdateToolTip.md)|상위 도구 모음 도구 설명 텍스트를 업데이트 하는 경우 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md).\)|  
|`CMFCToolBarDateTimeCtrl::Serialize`|이 개체는 보관 파일에서 읽거나에 아카이브를 작성 \(재정의 [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md).\)|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|도구 모음 단추의 스타일을 설정합니다.  \(재정의 [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md).\)|  
|[CMFCToolBarDateTimeCtrl::SetTime](../Topic/CMFCToolBarDateTimeCtrl::SetTime.md)|시간 및 날짜 시간 선택 컨트롤에 설정합니다.|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](../Topic/CMFCToolBarDateTimeCtrl::SetTimeAll.md)|지정 된 명령 ID가 있는 모든 인스턴스에서 시간 선택 컨트롤의 날짜와 시간을 설정|  
  
## 설명  
 날짜 및 시간 선택 컨트롤을 사용 하는 방법의 예를 들어 ToolbarDateTimePicker 예제 프로젝트를 참조 하십시오.  도구 모음 단추 컨트롤을 추가 하는 방법에 대 한 자세한 내용은 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbardatetimectrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)