---
title: "CMFCCaptionBar 클래스 | Microsoft Docs"
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
  - "CMFCCaptionBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionBar 클래스"
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCaptionBar 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A `CMFCCaptionBar` 개체는 세 가지 요소를 표시할 수 있는 컨트롤 막대: 단추, 텍스트 레이블 및 비트맵.  그는 한 번에 각 형식의 요소가 하나씩만 표시할 수 있습니다.  각 요소는 컨트롤의 왼쪽 또는 오른쪽 가장자리 또는 가운데에 맞출 수 있습니다.  평면 또는 3D 스타일 캡션 표시줄의 위쪽 및 아래쪽 테두리를 적용할 수도 있습니다.  
  
## 구문  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)|캡션 표시줄 컨트롤을 만들고 연결 하는 `CMFCCaptionBar` 개체입니다.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](../Topic/CMFCCaptionBar::DoesAllowDynInsertBefore.md)|다른 창 동적으로 상위 프레임의 캡션 표시줄 사이의 삽입 가능 여부를 나타냅니다.  \(재정의 [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCCaptionBar::EnableButton](../Topic/CMFCCaptionBar::EnableButton.md)|캡션 표시줄에 단추를 사용할 수 있거나.|  
|[CMFCCaptionBar::GetAlignment](../Topic/CMFCCaptionBar::GetAlignment.md)|지정 된 요소의 맞춤을 반환합니다.|  
|[CMFCCaptionBar::GetBorderSize](../Topic/CMFCCaptionBar::GetBorderSize.md)|캡션 표시줄의 테두리 크기를 반환합니다.|  
|[CMFCCaptionBar::GetButtonRect](../Topic/CMFCCaptionBar::GetButtonRect.md)|단추 캡션 표시줄의 경계 사각형을 검색합니다.|  
|[CMFCCaptionBar::GetMargin](../Topic/CMFCCaptionBar::GetMargin.md)|캡션 표시줄 컨트롤의 가장자리와 캡션 표시줄 요소의 가장자리 사이의 거리를 반환합니다.|  
|[CMFCCaptionBar::IsMessageBarMode](../Topic/CMFCCaptionBar::IsMessageBarMode.md)|캡션 표시줄 메시지 표시줄 모드에 있는지 여부를 지정 합니다.|  
|[CMFCCaptionBar::RemoveBitmap](../Topic/CMFCCaptionBar::RemoveBitmap.md)|비트맵 이미지는 캡션 표시줄에서 제거합니다.|  
|[CMFCCaptionBar::RemoveButton](../Topic/CMFCCaptionBar::RemoveButton.md)|캡션 표시줄에서 단추를 제거합니다.|  
|[CMFCCaptionBar::RemoveIcon](../Topic/CMFCCaptionBar::RemoveIcon.md)|캡션 표시줄에서 아이콘을 제거합니다.|  
|[CMFCCaptionBar::RemoveText](../Topic/CMFCCaptionBar::RemoveText.md)|텍스트 레이블 캡션 표시줄에서 제거합니다.|  
|[CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md)|캡션 표시줄에 대 한 비트맵 이미지를 설정합니다.|  
|[CMFCCaptionBar::SetBorderSize](../Topic/CMFCCaptionBar::SetBorderSize.md)|캡션 표시줄의 테두리 크기를 설정합니다.|  
|[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)|캡션 표시줄에 단추를 설정합니다.|  
|[CMFCCaptionBar::SetButtonPressed](../Topic/CMFCCaptionBar::SetButtonPressed.md)|단추가 눌린 상태로 있는지 여부를 지정 합니다.|  
|[CMFCCaptionBar::SetButtonToolTip](../Topic/CMFCCaptionBar::SetButtonToolTip.md)|단추에 대 한 도구 설명을 설정합니다.|  
|[CMFCCaptionBar::SetFlatBorder](../Topic/CMFCCaptionBar::SetFlatBorder.md)|캡션 표시줄의 테두리 스타일을 설정합니다.|  
|[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)|캡션 표시줄에 아이콘을 설정합니다.|  
|[CMFCCaptionBar::SetImageToolTip](../Topic/CMFCCaptionBar::SetImageToolTip.md)|이미지 캡션 표시줄에 대 한 도구 설명을 설정합니다.|  
|[CMFCCaptionBar::SetMargin](../Topic/CMFCCaptionBar::SetMargin.md)|캡션 표시줄 컨트롤의 가장자리와 캡션 표시줄 요소의 가장자리 사이의 거리를 설정합니다.|  
|[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)|캡션 표시줄에 대 한 텍스트 레이블을 설정합니다.|  
  
### Protected 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCCaptionBar::OnDrawBackground](../Topic/CMFCCaptionBar::OnDrawBackground.md)|캡션 표시줄의 배경을 채우는 데 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawBorder](../Topic/CMFCCaptionBar::OnDrawBorder.md)|캡션 표시줄의 테두리를 그리려면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawButton](../Topic/CMFCCaptionBar::OnDrawButton.md)|캡션 표시줄 단추를 그리려면 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawImage](../Topic/CMFCCaptionBar::OnDrawImage.md)|캡션 표시줄 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCCaptionBar::OnDrawText](../Topic/CMFCCaptionBar::OnDrawText.md)|캡션 표시줄 텍스트를 그리려면 프레임 워크에 의해 호출 됩니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCCaptionBar::m\_clrBarBackground](../Topic/CMFCCaptionBar::m_clrBarBackground.md)|캡션 표시줄의 배경색입니다.|  
|[CMFCCaptionBar::m\_clrBarBorder](../Topic/CMFCCaptionBar::m_clrBarBorder.md)|캡션 표시줄의 테두리 색입니다.|  
|[CMFCCaptionBar::m\_clrBarText](../Topic/CMFCCaptionBar::m_clrBarText.md)|캡션 표시줄 텍스트의 색입니다.|  
  
## 설명  
 캡션 표시줄을 만들려면 다음과이 같이 하십시오.  
  
1.  생성 된 `CMFCCaptionBar` 개체입니다.  일반적으로 프레임 창 클래스에 캡션 표시줄을 추가 합니다.  
  
2.  호출 된 [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) 캡션 표시줄 컨트롤을 작성 하 고 여기에 연결 하는 `CMFCCaptionBar` 개체.  
  
3.  호출 [CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md), [CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md), [CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md), 및 [CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md) 캡션 표시줄 요소를 설정 합니다.  
  
 Button 요소를 설정 하는 경우 단추의 명령 ID를 할당 해야 합니다.  캡션 표시줄 경로 단추를 클릭할 때 사용자의 `WM_COMMAND` 부모 프레임 창에이 ID를 가진 메시지입니다.  
  
 캡션 표시줄 에뮬레이션 2007 Microsoft Office 응용 프로그램에서 표시 되는 메시지 표시줄 메시지 표시줄 모드에서 작업할 수도 있습니다.  비트맵, 메시지, 및 일반적으로 대화 상자를 엽니다.\)는 단추 \(메시지 표시줄 모드에서 캡션 표시줄 표시 됩니다. 비트맵을 도구 설명을 지정할 수 있습니다.  
  
 메시지 표시줄 모드를 사용 하려면 호출 [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) 네 번째 매개 변수 \(bIsMessageBarMode\)로 설정 하 고 `TRUE`.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 `CMFCCaptionBar` 클래스입니다.  캡션 표시줄 컨트롤을 만드는, 캡션 표시줄에 3D 테두리를 설정, 캡션 표시줄 컨트롤의 가장자리와 캡션 표시줄 요소 가장자리 사이의 픽셀 거리를 설정, 캡션 표시줄에 단추를 설정, 단추에 대 한 도구 설명을 설정, 캡션 표시줄에 대 한 텍스트 레이블을 설정, 캡션 표시줄에 대 한 비트맵 이미지를 설정 하는 예제를 보여 줍니다.및 캡션 표시줄에는 이미지의 도구 설명을 설정 합니다.  이 코드의 일부인의  [MS Office 2007 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/CPP/cmfccaptionbar-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## 요구 사항  
 **헤더:** afxcaptionbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)