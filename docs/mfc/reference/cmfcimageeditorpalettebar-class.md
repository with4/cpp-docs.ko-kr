---
title: "CMFCImageEditorPaletteBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImageEditorPaletteBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorPaletteBar class"
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCImageEditorPaletteBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

팔레트 막대 기능에는 이미지 편집기 대화 상자를 제공합니다.  
  
## 구문  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## Members  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCImageEditorPaletteBar::GetRowHeight](../Topic/CMFCImageEditorPaletteBar::GetRowHeight.md)|도구 모음 단추의 높이 반환합니다.  \(재정의 [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](../Topic/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable.md)|도구 모음 테두리 확장 된 단추를 표시할 수 있는지 여부를 결정 합니다.  \(재정의 [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
  
### 설명  
 이 클래스는 사용자 코드에서 직접 사용할 수 없습니다.  
  
 프레임 워크는이 클래스를 사용 하 여 이미지 편집기 대화 상자의 색상표 막대를 표시 합니다.  이미지 편집기 대화 상자에 대 한 자세한 내용은 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## 요구 사항  
 **헤더:** afximageeditordialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Class](../../mfc/reference/cmfcimageeditordialog-class.md)