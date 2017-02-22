---
title: "CMFCRibbonCustomizeDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonCustomizeDialog"
  - "~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog::GetThisClass"
  - "CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog"
  - "CMFCRibbonCustomizeDialog.GetThisClass"
  - "CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizeDialog destructor"
  - "CMFCRibbonCustomizeDialog class"
  - "CMFCRibbonCustomizeDialog class, 소멸자"
  - "GetThisClass method"
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCRibbonCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 메뉴를 표시 합니다.  **사용자 지정** 페이지.  
  
## 구문  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](../Topic/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog.md)|`CMFCRibbonCustomizeDialog` 개체를 생성합니다.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
  
## 설명  
 MFC는 AFX\_WM\_ON\_RIBBON\_CUSTOMIZE 메시지를 처리 하지 않거나 메시지 처리기에서 0을 반환 하는 경우 자동으로이 클래스를 인스턴스화합니다.  
  
 리본 메뉴를 표시 하려면 응용 프로그램에서이 클래스를 사용 하려는 경우  **사용자 지정** 대화 상자에서 방금 인스턴스화할 한 호출의 `DoModal` 메서드.  
  
 이 클래스에서 파생 되므로 [CMFCPropertySheet Class](../../mfc/reference/cmfcpropertysheet-class.md), 사용자 지정 페이지를 사용 하 여 추가할 수 있는 `CMFCPropertySheet` API.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncustomizedialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)