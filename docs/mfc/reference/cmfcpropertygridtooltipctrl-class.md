---
title: "CMFCPropertyGridToolTipCtrl Class | Microsoft Docs"
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
  - "CMFCPropertyGridToolTipCtrl::PreTranslateMessage"
  - "~CMFCPropertyGridToolTipCtrl"
  - "PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl.~CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl.PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCPropertyGridToolTipCtrl destructor"
  - "CMFCPropertyGridToolTipCtrl class"
  - "CMFCPropertyGridToolTipCtrl class, 소멸자"
  - "PreTranslateMessage method"
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현 도구 설명 컨트롤에 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md) 사용 하 여 도구 설명을 표시 합니다.  
  
## 구문  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](../Topic/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl.md)|`CMFCPropertyGridToolTipCtrl` 개체를 생성합니다.|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCPropertyGridToolTipCtrl::Create](../Topic/CMFCPropertyGridToolTipCtrl::Create.md)|도구 설명 컨트롤에 대 한 창을 만듭니다.|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](../Topic/CMFCPropertyGridToolTipCtrl::Deactivate.md)|비활성화 및 도구 설명 컨트롤을 숨깁니다.|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](../Topic/CMFCPropertyGridToolTipCtrl::GetLastRect.md)|도구 설명 컨트롤의 마지막 위치 좌표를 반환 합니다.|  
|[CMFCPropertyGridToolTipCtrl::Hide](../Topic/CMFCPropertyGridToolTipCtrl::Hide.md)|도구 설명 컨트롤을 숨깁니다.|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|클래스에 의해 사용 되는  [CWinApp](../../mfc/reference/cwinapp-class.md) 창 메시지를 디스패치하기 전에 변환 하는  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](../Topic/CMFCPropertyGridToolTipCtrl::SetTextMargin.md)|도구 설명 텍스트 및 도구 설명 창의 테두리 사이의 간격을 설정합니다.|  
|[CMFCPropertyGridToolTipCtrl::Track](../Topic/CMFCPropertyGridToolTipCtrl::Track.md)|도구 설명 컨트롤에 표시 됩니다.|  
  
## 설명  
 속성 이름에 포인터를 놓을 때 도구 설명이 표시 됩니다.  [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) 클래스는 사용자가 쉽게 읽을 수 있도록 도구 설명이 표시 됩니다.  일반적으로 도구 설명의 위치 포인터의 위치에 따라 결정 됩니다.  이 클래스를 사용 하 여 도구 설명 속성 이름 위에 나타나고 속성 이름을 완전히 볼 수 있도록 자연 속성 확장, 유사한.  
  
 MFC 자동으로이 컨트롤을 만들고 여기에 사용 하는 [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.을 `CMFCPropertyGridToolTipCtrl` 클래스 및 도구 설명 컨트롤에 표시 하는 방법.  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/CPP/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxpropertygridtooltipctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)