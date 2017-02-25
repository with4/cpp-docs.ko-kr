---
title: "CMFCStandardColorsPropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCStandardColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStandardColorsPropertyPage class"
ms.assetid: b84b7cfb-bb24-4c65-804a-5b642cb64400
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMFCStandardColorsPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 표준 색 색 대화 상자에서 선택할 수 있는 속성 페이지를 나타냅니다.  
  
## 구문  
  
```  
class CMFCStandardColorsPropertyPage : public CPropertyPage  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCStandardColorsPropertyPage::CMFCStandardColorsPropertyPage`|기본 생성자입니다.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCStandardColorsPropertyPage::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCStandardColorsPropertyPage::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
  
### 설명  
 `CMFCColorDialog` 클래스에서이 클래스를 사용 하 여 표준 색 속성 페이지를 표시 합니다.  `CMFCColorDialog`에 대한 자세한 내용은 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)를 참조하십시오.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCStandardColorsPropertyPage](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)  
  
## 요구 사항  
 **헤더:** afxstandardcolorspropertypage.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCCustomColorsPropertyPage Class](../../mfc/reference/cmfccustomcolorspropertypage-class.md)