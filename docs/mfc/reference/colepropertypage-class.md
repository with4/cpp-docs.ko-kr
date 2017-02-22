---
title: "COlePropertyPage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COlePropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePropertyPage class"
  - "사용자 지정 컨트롤[MFC], 속성"
  - "displaying properties"
  - "OLE property pages"
  - "속성[C++], 표시"
  - "속성 페이지, OLE"
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COlePropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대화 상자와 비슷한 그래픽 인터페이스에 사용자 지정 컨트롤의 속성을 표시 하는 데 사용 합니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COlePropertyPage::COlePropertyPage](../Topic/COlePropertyPage::COlePropertyPage.md)|`COlePropertyPage` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COlePropertyPage::GetControlStatus](../Topic/COlePropertyPage::GetControlStatus.md)|사용자가 컨트롤의 값 수정 여부를 나타냅니다.|  
|[COlePropertyPage::GetObjectArray](../Topic/COlePropertyPage::GetObjectArray.md)|속성 페이지에서 편집 중인 개체의 배열을 반환 합니다.|  
|[COlePropertyPage::GetPageSite](../Topic/COlePropertyPage::GetPageSite.md)|속성 페이지로 포인터를 반환 합니다. `IPropertyPageSite` 인터페이스.|  
|[COlePropertyPage::IgnoreApply](../Topic/COlePropertyPage::IgnoreApply.md)|적용 단추 컨트롤을 사용 하지 않는 결정 합니다.|  
|[COlePropertyPage::IsModified](../Topic/COlePropertyPage::IsModified.md)|사용자 속성 페이지 수정 여부를 나타냅니다.|  
|[COlePropertyPage::OnEditProperty](../Topic/COlePropertyPage::OnEditProperty.md)|사용자가 속성을 편집 하는 경우 프레임 워크에서 호출 됩니다.|  
|[COlePropertyPage::OnHelp](../Topic/COlePropertyPage::OnHelp.md)|사용자가 도움말을 호출할 때 프레임 워크에 의해 호출 됩니다.|  
|[COlePropertyPage::OnInitDialog](../Topic/COlePropertyPage::OnInitDialog.md)|속성 페이지를 초기화 하면 프레임 워크에서 호출 됩니다.|  
|[COlePropertyPage::OnObjectsChanged](../Topic/COlePropertyPage::OnObjectsChanged.md)|새 속성을 가진 다른 OLE 컨트롤을 선택 하면 프레임 워크에서 호출 됩니다.|  
|[COlePropertyPage::OnSetPageSite](../Topic/COlePropertyPage::OnSetPageSite.md)|사이트 페이지의 속성 프레임을 제공 하면 프레임 워크에서 호출 됩니다.|  
|[COlePropertyPage::SetControlStatus](../Topic/COlePropertyPage::SetControlStatus.md)|사용자가 컨트롤의 값 수정 여부를 나타내는 플래그를 설정 합니다.|  
|[COlePropertyPage::SetDialogResource](../Topic/COlePropertyPage::SetDialogResource.md)|속성 페이지 대화 상자 리소스를 설정합니다.|  
|[COlePropertyPage::SetHelpInfo](../Topic/COlePropertyPage::SetHelpInfo.md)|해당 도움말 파일 및 도움말 컨텍스트는 이름, 속성 페이지의 간략 한 도움말 텍스트를 설정합니다.|  
|[COlePropertyPage::SetModifiedFlag](../Topic/COlePropertyPage::SetModifiedFlag.md)|사용자 속성 페이지 수정 여부를 나타내는 플래그를 설정 합니다.|  
|[COlePropertyPage::SetPageName](../Topic/COlePropertyPage::SetPageName.md)|속성 페이지의 이름 \(caption\)을 설정합니다.|  
  
## 설명  
 예를 들어, 속성 페이지를 보고, 컨트롤의 caption 속성을 수정 하는 편집 컨트롤을 포함할 수 있습니다.  
  
 각 컨트롤을 사용자 지정 하거나 스톡 속성에는 대화 상자 컨트롤의 현재 속성 값을 확인 하 고 필요한 경우 해당 값을 수정 하려면 컨트롤의 사용자가 있을 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `COlePropertyPage`, 문서를 참조 하십시오.  [ActiveX 컨트롤: 속성 페이지](../../mfc/mfc-activex-controls-property-pages.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## 요구 사항  
 **헤더:**  afxctl.h  
  
## 참고 항목  
 [MFC 샘플 CIRC3](../../top/visual-cpp-samples.md)   
 [TESTHELP MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)