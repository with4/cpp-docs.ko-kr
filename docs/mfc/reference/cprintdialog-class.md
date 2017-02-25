---
title: "CPrintDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialog class"
  - "인쇄 대화 상자"
  - "Print Setup dialog box"
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CPrintDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인쇄에 대 한 Windows 공용 대화 상자에서 제공 하는 서비스를 캡슐화 합니다.  
  
## 구문  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialog::CPrintDialog](../Topic/CPrintDialog::CPrintDialog.md)|`CPrintDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)|인쇄 대화 상자를 표시 하지 않고 프린터 디바이스 컨텍스트를 만듭니다.|  
|[CPrintDialog::DoModal](../Topic/CPrintDialog::DoModal.md)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CPrintDialog::GetCopies](../Topic/CPrintDialog::GetCopies.md)|요청한 복사본 수를 검색 합니다.|  
|[CPrintDialog::GetDefaults](../Topic/CPrintDialog::GetDefaults.md)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|  
|[CPrintDialog::GetDeviceName](../Topic/CPrintDialog::GetDeviceName.md)|현재 선택된 된 프린터 장치의 이름을 검색합니다.|  
|[CPrintDialog::GetDevMode](../Topic/CPrintDialog::GetDevMode.md)|검색은 `DEVMODE` 구조.|  
|[CPrintDialog::GetDriverName](../Topic/CPrintDialog::GetDriverName.md)|현재 선택한 프린터 드라이버의 이름을 검색합니다.|  
|[CPrintDialog::GetFromPage](../Topic/CPrintDialog::GetFromPage.md)|시작 페이지의 인쇄 범위를 검색합니다.|  
|[CPrintDialog::GetPortName](../Topic/CPrintDialog::GetPortName.md)|현재 선택한 프린터 포트의 이름을 검색합니다.|  
|[CPrintDialog::GetPrinterDC](../Topic/CPrintDialog::GetPrinterDC.md)|프린터 디바이스 컨텍스트에 대 한 핸들을 검색합니다.|  
|[CPrintDialog::GetToPage](../Topic/CPrintDialog::GetToPage.md)|끝 페이지의 인쇄 범위를 검색합니다.|  
|[CPrintDialog::PrintAll](../Topic/CPrintDialog::PrintAll.md)|문서의 모든 페이지를 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialog::PrintCollate](../Topic/CPrintDialog::PrintCollate.md)|요청 복사본 한 부씩 인쇄 여부를 결정 합니다.|  
|[CPrintDialog::PrintRange](../Topic/CPrintDialog::PrintRange.md)|지정 된 범위의 페이지만 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialog::PrintSelection](../Topic/CPrintDialog::PrintSelection.md)|현재 선택한 항목만 인쇄 여부를 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialog::m\_pd](../Topic/CPrintDialog::m_pd.md)|사용자 지정 하는 데 사용 되는 구조체는 `CPrintDialog` 개체입니다.|  
  
## 설명  
 인쇄 및 인쇄 설정 대화 상자에서 Windows 표준에 맞는 방식으로 구현 방법은 일반적인 인쇄 대화 상자를 제공 합니다.  
  
> [!NOTE]
>  `CPrintDialogEx` Windows 2000 인쇄 속성 시트에서 제공 하는 서비스 클래스를 캡슐화 합니다.  자세한 내용은  [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) 개요.  
  
 `CPrintDialog`기능을 하 여 대체 된  [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)를 모두 인쇄 설정 및 페이지 설정에 대 한 공용 대화 상자를 제공 하도록 설계 되었습니다.  
  
 인쇄 과정에 대 한 응용 프로그램의 많은 부분을 처리 하는 프레임 워크에서 사용할 수 있습니다.  이런 경우 프레임 워크 자동 인쇄 Windows 공용 대화 상자를 표시합니다.  또한 인쇄에 대 한 응용 프로그램 프레임 워크 핸들이 없는 수 있지만 일반적인 인쇄 대화 상자에 직접 인쇄 대화 상자를 무시.  프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은  [인쇄](../../mfc/printing.md).  
  
 응용 프로그램 프레임 워크의 개입 없이 인쇄를 처리 하는 원하는 경우에 사용할 수 있습니다는 `CPrintDialog` "있는 그대로" 제공 되는 생성자를 클래스 또는 대화 상자 클래스에서 파생 될 수 있습니다 `CPrintDialog` 하 고 필요에 맞게 생성자를 작성 합니다.  두 경우 모두 이러한 대화 상자 클래스에서 파생 된 때문에 표준 MFC 대화 상자 처럼 동작 합니다 `CCommonDialog`.  
  
 사용 하는 `CPrintDialog` 개체, 먼저 사용 하 여 개체를 만들는 `CPrintDialog` 생성자입니다.  대화 상자 생성 된 후에 설정 하거나 모든 값을 수정 된  [m\_pd](../Topic/CPrintDialog::m_pd.md) 구조는 대화 상자 컨트롤의 값을 초기화 합니다.  `m_pd` 구조체의 형식이  [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843).  이 구조에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 핸들에서 지정 하지 않은 경우 `m_pd` 에  **hDevMode** 및  **hDevNames** 구성원 Windows 함수를 호출 해야  **GlobalFree** 대화 상자를 완료 하면이 핸들에 대 한.  제공 하는 프레임 워크의 인쇄 설정 구현은 사용 하는 경우 `CWinApp::OnFilePrintSetup`, 이러한 핸들을 해제 하지 않아도 됩니다.  핸들에 의해 유지 됩니다 `CWinApp` 에서 해제 된 `CWinApp`의 소멸자입니다.  사용 하는 경우 이러한 핸들을 해제 하는 데 필요한 것만 `CPrintDialog` 독립 실행형.  
  
 호출 대화 상자의 컨트롤을 초기화 한 후에 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 인쇄 옵션을 선택할 수 있습니다.  `DoModal`사용자가 확인 선택 여부를 반환 \(**IDOK**\) 또는 취소 \(**IDCANCEL**\) 단추.  
  
 경우 `DoModal` 반환  **IDOK**, 중 하나를 사용할 수 있습니다 `CPrintDialog`의 멤버 함수는 사용자가 입력 한 정보를 검색할 수 있습니다.  
  
 `CPrintDialog::GetDefaults` 멤버 함수 현재 프린터 기본값 대화 상자를 표시 하지 않고 검색 하는 데 유용 합니다.  이 함수는 사용자 개입이 필요 합니다.  
  
 창 수  **CommDlgExtendedError** 함수 대화 상자를 초기화 하는 동안 오류가 있는지 여부를 확인 하 고 오류에 대 한 자세한.  이 함수에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CPrintDialog`COMMDLG에 의존합니다.Windows 3.1 및 이후 버전에 제공 되는 DLL 파일입니다.  
  
 사용자 지정 대화 상자에는 클래스에서 파생 `CPrintDialog`확장된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵 추가, 사용자 지정 대화 상자 템플릿을 제공 합니다.  처리 되지 않은 모든 메시지를 기본 클래스에 전달 합니다.  후크 함수를 사용자 지정 하지 않아도 됩니다.  
  
 인쇄 하거나 인쇄 설정 대화 상자 인지에 따라 다르게 동일한 메시지를 처리 하는 각 대화 상자 클래스를 파생 되어야 합니다.  또한 Windows를 재정의 해야  **AttachOnSetup** 인쇄 대화 상자에서 인쇄 설정 단추를 선택 하면 새 대화 상자 만들기를 처리 하는 함수를.  
  
 사용에 대 한 자세한 내용은 `CPrintDialog`를 참조 하십시오  [공용 대화 상자 클래스](../../mfc/common-dialog-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [Diblook에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)