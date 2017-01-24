---
title: "CPropertySheet Class | Microsoft Docs"
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
  - "CPropertySheet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPropertySheet class"
  - "대화 상자, 탭"
  - "속성 시트, CPropertySheet class"
  - "탭 대화 상자"
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPropertySheet Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭 대화 상자 라고도 하는 속성 시트를 나타냅니다.  
  
## 구문  
  
```  
class CPropertySheet : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md)|`CPropertySheet` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md)|속성 시트에 페이지를 추가합니다.|  
|[CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md)|`CPropertySheet` 개체를 생성합니다.|  
|[CPropertySheet::Create](../Topic/CPropertySheet::Create.md)|모덜리스 속성 시트를 표시합니다.|  
|[CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md)|모달 속성 시트를 표시합니다.|  
|[CPropertySheet::EnableStackedTabs](../Topic/CPropertySheet::EnableStackedTabs.md)|속성 시트 탭 누적 또는 스크롤을 사용할지 여부를 나타냅니다.|  
|[CPropertySheet::EndDialog](../Topic/CPropertySheet::EndDialog.md)|속성 시트를 종료합니다.|  
|[CPropertySheet::GetActiveIndex](../Topic/CPropertySheet::GetActiveIndex.md)|속성 시트의 현재 페이지의 인덱스를 검색합니다.|  
|[CPropertySheet::GetActivePage](../Topic/CPropertySheet::GetActivePage.md)|현재 페이지의 개체를 반환합니다.|  
|[CPropertySheet::GetPage](../Topic/CPropertySheet::GetPage.md)|지정 된 페이지에 대 한 포인터를 검색합니다.|  
|[CPropertySheet::GetPageCount](../Topic/CPropertySheet::GetPageCount.md)|속성 시트에서 페이지 수를 검색합니다.|  
|[CPropertySheet::GetPageIndex](../Topic/CPropertySheet::GetPageIndex.md)|속성 시트의 지정 된 페이지의 인덱스를 검색합니다.|  
|[CPropertySheet::GetTabControl](../Topic/CPropertySheet::GetTabControl.md)|탭 컨트롤에 대 한 포인터를 검색합니다.|  
|[CPropertySheet::MapDialogRect](../Topic/CPropertySheet::MapDialogRect.md)|대화 상자 단위 사각형의 화면 단위를 변환합니다.|  
|[CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md)|속성 시트를 초기화를 확대 하도록 재정의 합니다.|  
|[CPropertySheet::PressButton](../Topic/CPropertySheet::PressButton.md)|선택 속성 시트에서 단추를 시뮬레이션합니다.|  
|[CPropertySheet::RemovePage](../Topic/CPropertySheet::RemovePage.md)|속성 시트에서 페이지를 제거합니다.|  
|[CPropertySheet::SetActivePage](../Topic/CPropertySheet::SetActivePage.md)|현재 page 개체를 프로그래밍 방식으로 설정합니다.|  
|[CPropertySheet::SetFinishText](../Topic/CPropertySheet::SetFinishText.md)|마침 단추의 텍스트를 설정합니다.|  
|[CPropertySheet::SetTitle](../Topic/CPropertySheet::SetTitle.md)|속성 시트의 캡션을 설정합니다.|  
|[CPropertySheet::SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md)|마법사 단추가 활성화 됩니다.|  
|[CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md)|마법사 모드를 활성화 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPropertySheet::m\_psh](../Topic/CPropertySheet::m_psh.md)|Windows  [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) 구조.  기본 속성 시트 매개 변수 액세스를 제공합니다.|  
  
## 설명  
 구성 속성 시트는 `CPropertySheet` 개체와 하나 이상의  [CPropertyPage](../../mfc/reference/cpropertypage-class.md) 개체입니다.  프레임 워크 속성 시트를 탭 인덱스 및 페이지 현재 선택된 영역에 창으로 표시 됩니다.  사용자는 적절 한 탭을 사용 하 여 특정 페이지로 이동 합니다.  
  
 `CPropertySheet`지원에 대 한 확장 된  [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) 구조 도입에 [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] 및 Windows NT 2000.  구조 플래그를 추가 하 고 "워터 마크" 배경 비트맵을 사용 하 여 지원 되는 멤버를 포함 합니다.  
  
 이러한 새 이미지 자동으로 속성 시트에 개체를 표시 하려면 호출을 이미지의 비트맵 및 색상표에 대 한 유효한 값 전달  [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) 또는  [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 경우에 `CPropertySheet` 에서 파생 된  [CDialog](../../mfc/reference/cdialog-class.md), 관리는 `CPropertySheet` 개체는 다음과 같이 관리는 `CDialog` 개체.  예를 들어, 속성 시트를 두 부분 생성 만들어야: 생성자를 호출 하 고 호출  [DoModal](../Topic/CPropertySheet::DoModal.md) 모달 속성 시트 또는  [만들기](../Topic/CPropertySheet::Create.md) 모덜리스 속성 시트에 대 한.  `CPropertySheet`두 가지 형식의 생성자 있습니다:  [CPropertySheet::Construct](../Topic/CPropertySheet::Construct.md) 및  [CPropertySheet::CPropertySheet](../Topic/CPropertySheet::CPropertySheet.md).  
  
 구성 하는 경우는 `CPropertySheet` 개체, 일부 [창 스타일](../../mfc/reference/window-styles.md) 첫째 예외를 발생 합니다.  이 시트를 작성 하기 전에 속성 시트의 스타일을 변경 하는 시스템에서 발생 합니다.  이 예외가 발생 하지 않도록 하려면 사용자를 만들 때 다음과 같은 스타일을 설정 해야 하면 `CPropertySheet`.  
  
-   DS\_3DLOOK  
  
-   DS\_CONTROL  
  
-   WS\_CHILD  
  
-   WS\_TABSTOP  
  
 다음 스타일 며 첫째 예외가 발생 하지 않습니다.  
  
-   DS\_SHELLFONT  
  
-   DS\_LOCALEDIT  
  
-   WS\_CLIPCHILDREN  
  
 기타 `Window Styles` 금지 되 고 사용 하지 않습니다.  
  
 간에 데이터를 교환 하는 `CPropertySheet` 개체와 외부 개체는 비슷한 데이터를 교환 하는 `CDialog` 개체.  일반적으로 멤버 변수를 속성 시트의 설정을 지 중요 한 차이점은는 `CPropertyPage` 개체 대신에 `CPropertySheet` 개체 자체.  
  
 탭 대화 상자 호출 시퀀스를 사용자의 장치를 설치 하거나 회보를 만드는 등의 작업을 단계별로 안내 하는 속성 페이지를 속성 시트의 구성 마법사 형식을 만들 수 있습니다.  마법사 종류 탭 대화 상자에서 속성 페이지 탭 없고 하나의 속성 페이지를 한 번에 표시 됩니다.  없이,  **확인** 및  **지금 적용** 마법사 종류 탭 대화 상자 단추를 한는  **다시** 단추는  **다음** 또는  **완료** 단추를는  **취소** 단추를와  **도움말** 단추.  
  
 마법사 종류 대화 상자를 만들려면 호출 하지만 표준 속성 시트를 만들려면 따라가는 동일한 단계를 수행 하십시오.  [SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) 를 호출 하기 전에  [DoModal](../Topic/CPropertySheet::DoModal.md).  \[마법사\] 단추를 사용 하려면 호출  [SetWizardButtons](../Topic/CPropertySheet::SetWizardButtons.md), 플래그를 사용 하 여 그 기능과 모양을 사용자 지정할 수 있습니다.  사용 하는  **완료** 단추를 호출  [SetFinishText](../Topic/CPropertySheet::SetFinishText.md) 사용자가 마법사의 마지막 페이지에서 작업을 수행한 후.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CPropertySheet` 문서를 참조 하는 개체를  [속성 시트 및 속성 페이지](../../mfc/property-sheets-and-property-pages-in-mfc.md).  또한 기술 자료 문서 q146916를 참조 하십시오: 방법: 모덜리스 CPropertySheet 표준 단추를 만들고 문서 Q300606: 방법: MFC 속성 시트 크기 조정 가능한 디자인.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## 요구 사항  
 **헤더:** afxdlgs.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [MFC PROPDLG 샘플에서](../../top/visual-cpp-samples.md)   
 [MFC SNAPVW 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)