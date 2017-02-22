---
title: "CMFCFontInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFontInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontInfo class"
  - "CMFCFontInfo::CMFCFontInfo constructor"
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCFontInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCFontInfo` 클래스 이름과 다른 글꼴의 특성을 설명 합니다.  
  
## 구문  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCFontInfo`|`CMFCFontInfo` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCFontInfo::GetFullName](../Topic/CMFCFontInfo::GetFullName.md)|검색 글꼴 및 해당 문자로 연결 된 이름 \(스크립트\)를 설정합니다.|  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCFontInfo::m\_nCharSet](../Topic/CMFCFontInfo::m_nCharSet.md)|글꼴과 관련 된 문자 집합 \(스크립트\)을 지정 하는 값입니다.|  
|[CMFCFontInfo::m\_nPitchAndFamily](../Topic/CMFCFontInfo::m_nPitchAndFamily.md)|피치 및 글꼴 패밀리를 지정 하는 값입니다.|  
|[CMFCFontInfo::m\_nType](../Topic/CMFCFontInfo::m_nType.md)|글꼴의 종류를 지정 하는 값입니다.|  
|[CMFCFontInfo::m\_strName](../Topic/CMFCFontInfo::m_strName.md)|글꼴의 이름입니다. 예를 들어,  **굴림**.|  
|[CMFCFontInfo::m\_strScript](../Topic/CMFCFontInfo::m_strScript.md)|글꼴과 관련 된 문자 집합 \(스크립트\)의 이름입니다.|  
  
## 설명  
 연결할 수는 `CMFCFontInfo` 개체의 항목에는 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md) 클래스.  호출 하는 [CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) 에 대 한 포인터를 검색 하는 메서드는 `CMFCFontInfo` 개체.  
  
## 예제  
 다양 한 멤버를 사용 하는 방법 다음 예제는 `CMFCFontInfo` 클래스입니다.  예제를 가져오는 방법을 보여 줍니다.를 `CMFCFontInfo` 에서 개체는 `CMFCRibbonFontComboBox`, 로컬 변수를 액세스 하는 방법.  이 이때의 일부인의  [MSOffice 2007 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/CPP/cmfcfontinfo-class_1.cpp)]  
  
## 요구 사항  
 **헤더:** afxtoolbarfontcombobox.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox Class](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox Class](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)