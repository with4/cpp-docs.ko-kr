---
title: "CMFCRibbonCustomizePropertyPage Class | Microsoft Docs"
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
  - "GetThisClass"
  - "CMFCRibbonCustomizePropertyPage::CreateObject"
  - "CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage.GetThisClass"
  - "CMFCRibbonCustomizePropertyPage.CreateObject"
  - "~CMFCRibbonCustomizePropertyPage"
  - "CreateObject"
  - "CMFCRibbonCustomizePropertyPage.~CMFCRibbonCustomizePropertyPage"
  - "CMFCRibbonCustomizePropertyPage::GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCRibbonCustomizePropertyPage destructor"
  - "CMFCRibbonCustomizePropertyPage class"
  - "CMFCRibbonCustomizePropertyPage class, 소멸자"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonCustomizePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구현에 대 한 사용자 지정 페이지의  **사용자 지정** 리본 메뉴 기반 응용 프로그램에서 대화 상자.  
  
## 구문  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](../Topic/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage.md)|`CMFCRibbonCustomizePropertyPage` 개체를 생성합니다.|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|소멸자.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](../Topic/CMFCRibbonCustomizePropertyPage::AddCustomCategory.md)|사용자 지정 범주에 추가 된  **명령** 콤보 상자.|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCRibbonCustomizePropertyPage::OnOK](../Topic/CMFCRibbonCustomizePropertyPage::OnOK.md)|클릭할 때 시스템에 의해 호출  **확인** 에 있는  **사용자 지정** 대화 상자.|  
  
## 설명  
 사용자 지정 명령을 추가 하는 경우는  **사용자 지정** 대화 상자 AFX\_WM\_ON\_RIBBON\_CUSTOMIZE 메시지를 처리 해야 합니다.  메시지 처리기에서 인스턴스화하는 `CMFCRibbonCustomizePropertyPage` 개체의 부모.  사용자 지정 명령 목록을 만들고 다음 호출 `AddCustomCategory` 새 페이지에 추가 하는  **사용자 지정** 대화 상자.  
  
## 예제  
 다음 예제에서는 생성 하는 방법을 보여 줍니다.는 `CMFCRibbonCustomizePropertyPage` 개체와 사용자 지정 범주를 추가 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/CPP/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncustomizedialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)