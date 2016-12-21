---
title: "CMFCStatusBar Class | Microsoft Docs"
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
  - "CMFCStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStatusBar class"
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCStatusBar` 클래스와 유사한 상태 표시줄 구현 된 `CStatusBar` 클래스.  그러나는 `CMFCStatusBar` 클래스에서 제공 하지 않는 기능에는 `CStatusBar` 클래스, 이미지, 애니메이션 및 진행률 표시줄; 표시 하는 기능 등 및 마우스를 응답을 두 번 클릭 합니다.  
  
## 구문  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCStatusBar::CalcFixedLayout](../Topic/CMFCStatusBar::CalcFixedLayout.md)|\(재정의 [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCStatusBar::CommandToIndex](../Topic/CMFCStatusBar::CommandToIndex.md)||  
|[CMFCStatusBar::Create](../Topic/CMFCStatusBar::Create.md)|컨트롤 막대를 만들고 연결 하는  [CPane](../../mfc/reference/cpane-class.md) 개체입니다.  \(재정의 [CPane::Create](../Topic/CPane::Create.md).\)|  
|[CMFCStatusBar::CreateEx](../Topic/CMFCStatusBar::CreateEx.md)|컨트롤 막대를 만들고 연결 하는  [CPane](../../mfc/reference/cpane-class.md) 개체입니다.  \(재정의 [CPane::CreateEx](../Topic/CPane::CreateEx.md).\)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](../Topic/CMFCStatusBar::DoesAllowDynInsertBefore.md)|다른 창 동적이 창과 부모 프레임 삽입 가능 여부를 결정 합니다.  \(재정의 [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCStatusBar::EnablePaneDoubleClick](../Topic/CMFCStatusBar::EnablePaneDoubleClick.md)|활성화 또는 비활성화 상태 표시줄에 마우스 처리를 두 번 클릭 합니다.|  
|[CMFCStatusBar::EnablePaneProgressBar](../Topic/CMFCStatusBar::EnablePaneProgressBar.md)|지정한 창에서 진행률 표시줄을 표시합니다.|  
|[CMFCStatusBar::GetCount](../Topic/CMFCStatusBar::GetCount.md)|창의 상태 표시줄에 반환합니다.|  
|[CMFCStatusBar::GetDrawExtendedArea](../Topic/CMFCStatusBar::GetDrawExtendedArea.md)||  
|[CMFCStatusBar::GetExtendedArea](../Topic/CMFCStatusBar::GetExtendedArea.md)||  
|[CMFCStatusBar::GetItemID](../Topic/CMFCStatusBar::GetItemID.md)||  
|[CMFCStatusBar::GetItemRect](../Topic/CMFCStatusBar::GetItemRect.md)||  
|[CMFCStatusBar::GetPaneInfo](../Topic/CMFCStatusBar::GetPaneInfo.md)||  
|[CMFCStatusBar::GetPaneProgress](../Topic/CMFCStatusBar::GetPaneProgress.md)||  
|[CMFCStatusBar::GetPaneStyle](../Topic/CMFCStatusBar::GetPaneStyle.md)|창의 스타일을 반환합니다.  \(재정의 [CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md).\)|  
|[CMFCStatusBar::GetPaneText](../Topic/CMFCStatusBar::GetPaneText.md)||  
|[CMFCStatusBar::GetPaneWidth](../Topic/CMFCStatusBar::GetPaneWidth.md)|너비를 픽셀 단위로 지정 된 창의 상태 표시줄을 반환합니다.|  
|[CMFCStatusBar::GetTipText](../Topic/CMFCStatusBar::GetTipText.md)|지정한 창의 상태 표시줄에 대 한 도구 설명 텍스트를 반환합니다.|  
|[CMFCStatusBar::InvalidatePaneContent](../Topic/CMFCStatusBar::InvalidatePaneContent.md)|지정한 창의 무효화 하 고 해당 내용을 다시 그립니다.|  
|[CMFCStatusBar::PreCreateWindow](../Topic/CMFCStatusBar::PreCreateWindow.md)|프레임 워크에 연결 하려면이 창 만들기 전에 호출 `CWnd` 개체입니다.  \(재정의 [CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).\)|  
|[CMFCStatusBar::SetDrawExtendedArea](../Topic/CMFCStatusBar::SetDrawExtendedArea.md)||  
|[CMFCStatusBar::SetIndicators](../Topic/CMFCStatusBar::SetIndicators.md)||  
|[CMFCStatusBar::SetPaneAnimation](../Topic/CMFCStatusBar::SetPaneAnimation.md)|애니메이션은 지정한 창에 할당합니다.|  
|[CMFCStatusBar::SetPaneBackgroundColor](../Topic/CMFCStatusBar::SetPaneBackgroundColor.md)|지정한 창의 상태 표시줄 배경색을 설정합니다.|  
|[CMFCStatusBar::SetPaneIcon](../Topic/CMFCStatusBar::SetPaneIcon.md)|지정 된 창 상태 표시줄의 표시기 아이콘을 설정합니다.|  
|[CMFCStatusBar::SetPaneInfo](../Topic/CMFCStatusBar::SetPaneInfo.md)||  
|[CMFCStatusBar::SetPaneProgress](../Topic/CMFCStatusBar::SetPaneProgress.md)|지정한 창의 상태 표시줄의 진행률 표시줄의 현재 진행률을 설정합니다.|  
|[CMFCStatusBar::SetPaneStyle](../Topic/CMFCStatusBar::SetPaneStyle.md)|창 스타일을 설정합니다.  \(재정의 [CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md).\)|  
|[CMFCStatusBar::SetPaneText](../Topic/CMFCStatusBar::SetPaneText.md)||  
|[CMFCStatusBar::SetPaneTextColor](../Topic/CMFCStatusBar::SetPaneTextColor.md)|지정 된 창 상태 표시줄의 텍스트 색을 설정합니다.|  
|[CMFCStatusBar::SetPaneWidth](../Topic/CMFCStatusBar::SetPaneWidth.md)|픽셀 단위로 지정 된 창 상태 표시줄의 너비를 설정합니다.|  
|[CMFCStatusBar::SetTipText](../Topic/CMFCStatusBar::SetTipText.md)|지정한 창의 상태 표시줄에 대 한 도구 설명 텍스트를 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCStatusBar::OnDrawPane](../Topic/CMFCStatusBar::OnDrawPane.md)|창의 상태 표시줄을 다시 그립니다 때 프레임 워크에 의해 호출 됩니다.|  
  
## 설명  
 다음 다이어그램은 그림의 상태 표시줄에서  [상태 표시줄 데모 샘플](../../top/visual-cpp-samples.md) 응용 프로그램.  
  
 ![CMFCStatusBar의 예제](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar")  
  
## 예제  
 다음 예제는 응용 프로그램을 사용 하 여 다양 한 메서드를 호출 하는 지역 변수는 `CMFCStatusBar` 클래스입니다.  Statusbardemoview.h에서 이러한 변수를 선언 합니다.  주 프레임에 MainFrm.h 선언, 문서 Statusbardemodoc.h에 선언 된 보기 Statusbardemoview.h에 선언 됩니다.  이 코드 조각에 속해 있는  [상태 표시줄 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_1.h)]  
  
## 예제  
 다음 예제를 참조 하는 방법 `CMFCStatusBar` 도입 하 여 개체의 `GetStatusBar` MainFrm.h 및이 메서드를 호출 하 고 메서드는 `GetStatusBar` Statusbardemoview.h에서 메서드.  이 코드 조각에 속해 있는  [상태 표시줄 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_2.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_3.h)]  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 호출 하는 `CMFCStatusBar` 클래스에서 StatusBarDemoView.cpp.  Mainfrm.h의 상수를 선언 합니다.  이 예제에서는 아이콘을 설정, 상태 표시줄 창의 도구 설명 텍스트를 설정 합니다. 지정한 창에 진행률 표시줄을 표시, 애니메이션을 지정 된 창에 할당, 텍스트 및 너비는 상태 표시줄 창에 설정 하 고 현재 진행률 표시기가 상태 표시줄 창에 대 한 진행률 표시줄을 설정 방법을 보여 줍니다.  이 코드 조각에 속해 있는  [상태 표시줄 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_4.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_5.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_6.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_7.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_8.cpp)]  
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/CPP/cmfcstatusbar-class_9.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## 요구 사항  
 **헤더:** afxstatusbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)