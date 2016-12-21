---
title: "CMFCToolBarComboBoxEdit Class | Microsoft Docs"
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
  - "CMFCComboEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarComboBoxEdit class"
  - "CMFCToolBarComboBoxEdit::PreTranslateMessage method"
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
caps.latest.revision: 25
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarComboBoxEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프레임 워크를 사용 하는 `CMFCToolBarComboBoxEdit` 클래스는 편집 가능한 콤보 상자 컨트롤 처럼 동작 하는 도구 모음 단추를 만들 수 있습니다.  
  
## 구문  
  
```  
class CMFCToolBarComboBoxEdit : public CEdit  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](../Topic/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit.md)|`CMFCToolBarComboBoxEdit` 개체를 생성합니다.|  
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|창 메시지를 디스패치하기 전에 변환의  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 기능입니다.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
  
### 설명  
 클래스에서 파생 되는 `CMFCToolBarComboBoxEdit` 편집 작업을 사용자 지정 하는 클래스입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbarcomboboxbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarComboBoxButton::CreateEdit](../Topic/CMFCToolBarComboBoxButton::CreateEdit.md)