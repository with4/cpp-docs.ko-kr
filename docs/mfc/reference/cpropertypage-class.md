---
title: "CPropertyPage Class | Microsoft Docs"
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
  - "CPropertyPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertyPage class"
  - "대화 상자, 탭"
  - "속성 페이지, CPropertyPage class"
  - "탭 대화 상자"
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertyPage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭 대화 상자로 알려져 속성 시트의 개별 페이지를 나타냅니다.  
  
## 구문  
  
```  
class CPropertyPage : public CDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPropertyPage::CPropertyPage](../Topic/CPropertyPage::CPropertyPage.md)|`CPropertyPage` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPropertyPage::CancelToClose](../Topic/CPropertyPage::CancelToClose.md)|확인 단추 닫기, 읽을 수 변경 및 모달 속성 시트 페이지에서를 복구할 수 없는 변경 후 취소 단추를 사용할 수 없습니다.|  
|[CPropertyPage::Construct](../Topic/CPropertyPage::Construct.md)|`CPropertyPage` 개체를 생성합니다.  사용 `Construct` 매개 변수를 실행된 시간에 지정 하려는 경우 또는 배열을 사용 하는 경우.|  
|[CPropertyPage::GetPSP](../Topic/CPropertyPage::GetPSP.md)|Windows 검색  [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) 구조와 연관 된 `CPropertyPage` 개체.|  
|[CPropertyPage::OnApply](../Topic/CPropertyPage::OnApply.md)|지금 적용 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CPropertyPage::OnCancel](../Topic/CPropertyPage::OnCancel.md)|취소 단추를 클릭 하면 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md)|현재 페이지에 더 이상 활성 페이지가 아니면 프레임 워크에서 호출 됩니다.  여기서 데이터의 유효성을 검사하십시오.|  
|[CPropertyPage::OnOK](../Topic/CPropertyPage::OnOK.md)|확인, 이제 적용 또는 닫기 단추를 클릭 하면 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnQueryCancel](../Topic/CPropertyPage::OnQueryCancel.md)|프레임 워크에서 취소 단추를 클릭 하 고 취소 작업이 수행 되기 전에 호출 됩니다.|  
|[CPropertyPage::OnReset](../Topic/CPropertyPage::OnReset.md)|취소 단추를 클릭 하면 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md)|때 페이지가 활성 페이지 프레임 워크에서 호출 됩니다.|  
|[CPropertyPage::OnWizardBack](../Topic/CPropertyPage::OnWizardBack.md)|마법사 형식의 속성 시트를 사용 하는 동안 \[뒤로\] 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CPropertyPage::OnWizardFinish](../Topic/CPropertyPage::OnWizardFinish.md)|마법사 형식의 속성 시트를 사용 하는 동안 \[마침\] 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CPropertyPage::OnWizardNext](../Topic/CPropertyPage::OnWizardNext.md)|마법사 형식의 속성 시트를 사용 하는 동안 \[다음\] 단추를 클릭할 때 프레임 워크에 의해 호출 됩니다.|  
|[CPropertyPage::QuerySiblings](../Topic/CPropertyPage::QuerySiblings.md)|속성 시트의 각 페이지에 메시지를 전달합니다.|  
|[CPropertyPage::SetModified](../Topic/CPropertyPage::SetModified.md)|전화 활성화 또는 적용 단추를 비활성화 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPropertyPage::m\_psp](../Topic/CPropertyPage::m_psp.md)|Windows  [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548) 구조.  기본 속성 페이지의 매개 변수를 액세스를 제공합니다.|  
  
## 설명  
 표준 대화 상자 클래스에서 파생 되는 `CPropertyPage` 를 속성 시트의 각 페이지에 대 한.  사용 `CPropertyPage`\-파생된 개체를 처음 만들는  [CPropertySheet](../../mfc/reference/cpropertysheet-class.md) 개체를 가리킨 다음 속성 시트에 이동 하는 각 페이지에 대 한 개체를 만듭니다.  호출  [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) 각 페이지에 시트, 및 다음 호출 하 여 속성 시트를 표시  [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) 는 모달 속성 시트 또는  [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) 모덜리스 속성 시트에 대 한.  
  
 탭 대화 상자 호출 시퀀스를 사용자의 장치를 설치 하거나 회보를 만드는 등의 작업을 단계별로 안내 하는 속성 페이지를 속성 시트의 구성 마법사 형식을 만들 수 있습니다.  마법사 종류 탭 대화 상자에서 속성 페이지 탭 없고 하나의 속성 페이지를 한 번에 표시 됩니다.  또한 확인 하 고 지금 적용 단추를 사용 하는 대신 마법사 종류 탭 대화 상자 뒤로 단추, 다음 또는 마침 단추 및 취소 단추가 있습니다.  
  
 마법사 속성 시트 설정에 대 한 자세한 내용은  [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md).  사용에 대 한 자세한 내용은 `CPropertyPage` 문서를 참조 하는 개체를  [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [MFC PROPDLG 샘플에서](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW 샘플](../../top/visual-cpp-samples.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)