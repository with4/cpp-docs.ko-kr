---
title: "CMFCCustomColorsPropertyPage Class | Microsoft Docs"
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
  - "CMFCCustomColorsPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCustomColorsPropertyPage class"
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCustomColorsPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 지정 색 색 대화 상자에서 선택할 수 있는 속성 페이지를 나타냅니다.  
  
## 구문  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## Members  
  
### Public 생성자  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|기본 생성자입니다.|  
  
### Public 메서드  
  
|||  
|-|-|  
|Name|설명|  
|`CMFCCustomColorsPropertyPage::CreateObject`|프레임 워크에서 사용 하는 이와 같은 클래스의 동적 인스턴스를 만들려면.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCCustomColorsPropertyPage::Setup](../Topic/CMFCCustomColorsPropertyPage::Setup.md)|구성 요소 속성 페이지의 색을 설정합니다.|  
  
### 설명  
 `CMFCColorDialog` 클래스에서이 클래스를 사용 하 여 사용자 지정 색 속성 페이지를 표시 합니다.  `CMFCColorDialog`에 대한 자세한 내용은 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 생성 하는 방법을 보여 줍니다.는 `CMFCCustomColorsPropertyPage` 개체 및 속성 페이지의 색 구성 요소를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/CPP/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## 요구 사항  
 **헤더:** afxcustomcolorspropertypage.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage Class](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)