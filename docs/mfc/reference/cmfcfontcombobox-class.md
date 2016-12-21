---
title: "CMFCFontComboBox Class | Microsoft Docs"
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
  - "CMFCFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontComboBox class"
  - "CMFCFontComboBox::CompareItem method"
  - "CMFCFontComboBox::DrawItem method"
  - "CMFCFontComboBox::MeasureItem method"
  - "CMFCFontComboBox::PreTranslateMessage method"
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCFontComboBox` 클래스 글꼴 목록이 표시 된 콤보 상자 컨트롤을 만듭니다.  
  
## 구문  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCFontComboBox::CMFCFontComboBox](../Topic/CMFCFontComboBox::CMFCFontComboBox.md)|`CMFCFontComboBox` 개체를 생성합니다.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCFontComboBox::CompareItem`|현재 글꼴 콤보 상자 컨트롤의 정렬 된 목록 상자에서 새 항목의 상대 위치를 결정 하는 프레임 워크에서 호출 합니다.  \(재정의 [CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md).\)|  
|`CMFCFontComboBox::DrawItem`|현재 글꼴 콤보 상자 컨트롤에서 지정 된 항목을 그리려면 프레임 워크에서 호출 합니다.  \(재정의 [CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md).\)|  
|[CMFCFontComboBox::GetSelFont](../Topic/CMFCFontComboBox::GetSelFont.md)|현재 선택한 글꼴에 대 한 정보를 검색합니다.|  
|`CMFCFontComboBox::MeasureItem`|Windows 목록 상자에서 현재 글꼴 콤보 상자 컨트롤의 크기를 알리기 위해 프레임 워크에서 호출 합니다.  \(재정의 [CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md).\)|  
|`CMFCFontComboBox::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMFCFontComboBox::SelectFont](../Topic/CMFCFontComboBox::SelectFont.md)|글꼴 콤보 상자에서 지정 된 조건과 일치 하는 글꼴을 선택 합니다.|  
|[CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)|글꼴 콤보 상자에서 항목을 초기화합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCFontComboBox::m\_bDrawUsingFont](../Topic/CMFCFontComboBox::m_bDrawUsingFont.md)|프레임 워크를 현재 글꼴 콤보 상자에 항목 레이블을 사용 하는 글꼴을 나타냅니다.|  
  
## 설명  
 사용 하는 `CMFCFontComboBox` 개체 대화 상자에서 추가 `CMFCFontComboBox` 변수 대화 상자 클래스에 있습니다.  다음에 `OnInitDialog` 호출 대화 상자 클래스의 메서드는 [CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md) 콤보 상자 컨트롤에서 항목 목록을 초기화 하는 메서드.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## 요구 사항  
 **헤더:** afxfontcombobox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Class](../../mfc/reference/cmfcfontinfo-class.md)