---
title: "CMFCToolBarFontComboBox Class | Microsoft Docs"
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
  - "CMFCToolBarFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontComboBox class"
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

도구 모음 단추 시스템 글꼴 목록에서 글꼴을 선택 하는 사용자가 콤보 상자 컨트롤을 포함 합니다.  
  
## 구문  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](../Topic/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox.md)|`CMFCToolBarFontComboBox` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md)|반환에 대 한 포인터는 `CMFCFontInfo` 콤보 상자에서 지정 된 인덱스에 대 한 개체.|  
|[CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md)|접두사 및 문자 집합의 글꼴 또는 글꼴 이름을 글꼴 콤보 상자 하나에 따라 글꼴을 선택합니다.|  
  
### 데이터 멤버  
 [CMFCToolBarFontComboBox::m\_nFontHeight](../Topic/CMFCToolBarFontComboBox::m_nFontHeight.md)  
 콤보 상자의 글꼴의 문자 높이입니다.  
  
## 설명  
 글꼴 콤보 상자 단추를 도구 모음에 추가 하려면 다음과이 같이 하십시오.  
  
1.  부모 리소스 도구 모음 단추에 대 한 더미 리소스 ID를 예약 합니다.  
  
2.  `CMFCToolBarFontComboBox` 개체를 생성합니다.  
  
3.  처리 된 메시지 처리기에서는 `AFX_WM_RESETTOOLBAR` 메시지, 새 콤보 상자 단추를 사용 하 여 원래 단추를 대체 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md).  
  
4.  동기화를 사용 하 여 문서에서 글꼴을 콤보 상자에서 선택 된 글꼴의 [CMFCToolBarFontComboBox::SetFont](../Topic/CMFCToolBarFontComboBox::SetFont.md) 메서드.  
  
 콤보 상자에서 선택한 글꼴은 문서의 글꼴 동기화에 사용 된 [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) 메서드는 선택한 글꼴의 특성을 검색 하 고 해당 특성을 사용 하 여 만들 수는 [CFont Class](../../mfc/reference/cfont-class.md) 개체.  
  
 Win32 함수를 호출 하는 콤보 상자 글꼴 단추  [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) 시스템에 사용할 수 있는 화면 및 프린터 글꼴을 결정 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbarfontcombobox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [연습: 도구 모음에 컨트롤 배치](../../mfc/walkthrough-putting-controls-on-toolbars.md)