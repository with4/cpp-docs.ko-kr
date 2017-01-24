---
title: "CPrintDialogEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintDialogEx class"
  - "인쇄 대화 상자"
  - "Print Setup dialog box"
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrintDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 2000 인쇄 속성 시트에서 제공 하는 서비스를 캡슐화 합니다.  
  
## 구문  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialogEx::CPrintDialogEx](../Topic/CPrintDialogEx::CPrintDialogEx.md)|`CPrintDialogEx` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialogEx::CreatePrinterDC](../Topic/CPrintDialogEx::CreatePrinterDC.md)|인쇄 대화 상자를 표시 하지 않고 프린터 디바이스 컨텍스트를 만듭니다.|  
|[CPrintDialogEx::DoModal](../Topic/CPrintDialogEx::DoModal.md)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CPrintDialogEx::GetCopies](../Topic/CPrintDialogEx::GetCopies.md)|요청한 복사본 수를 검색 합니다.|  
|[CPrintDialogEx::GetDefaults](../Topic/CPrintDialogEx::GetDefaults.md)|대화 상자를 표시 하지 않고 장치 기본값을 검색 합니다.|  
|[CPrintDialogEx::GetDeviceName](../Topic/CPrintDialogEx::GetDeviceName.md)|현재 선택된 된 프린터 장치의 이름을 검색합니다.|  
|[CPrintDialogEx::GetDevMode](../Topic/CPrintDialogEx::GetDevMode.md)|검색은 `DEVMODE` 구조.|  
|[CPrintDialogEx::GetDriverName](../Topic/CPrintDialogEx::GetDriverName.md)|시스템에서 정의 된 프린터 장치 드라이버의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPortName](../Topic/CPrintDialogEx::GetPortName.md)|현재 선택한 프린터 포트의 이름을 검색합니다.|  
|[CPrintDialogEx::GetPrinterDC](../Topic/CPrintDialogEx::GetPrinterDC.md)|프린터 디바이스 컨텍스트에 대 한 핸들을 검색합니다.|  
|[CPrintDialogEx::PrintAll](../Topic/CPrintDialogEx::PrintAll.md)|문서의 모든 페이지를 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintCollate](../Topic/CPrintDialogEx::PrintCollate.md)|요청 복사본 한 부씩 인쇄 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintCurrentPage](../Topic/CPrintDialogEx::PrintCurrentPage.md)|문서의 현재 페이지를 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintRange](../Topic/CPrintDialogEx::PrintRange.md)|지정 된 범위의 페이지만 인쇄할지 여부를 결정 합니다.|  
|[CPrintDialogEx::PrintSelection](../Topic/CPrintDialogEx::PrintSelection.md)|현재 선택한 항목만 인쇄 여부를 결정 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPrintDialogEx::m\_pdex](../Topic/CPrintDialogEx::m_pdex.md)|사용자 지정 하는 데 사용 되는 구조체는 `CPrintDialogEx` 개체입니다.|  
  
## 설명  
 인쇄 과정에 대 한 응용 프로그램의 많은 부분을 처리 하는 프레임 워크에서 사용할 수 있습니다.  프레임 워크를 사용 하 여 인쇄 작업을 처리 하는 방법에 대 한 자세한 내용은  [인쇄](../../mfc/printing.md).  
  
 응용 프로그램 프레임 워크의 개입 없이 인쇄를 처리 하는 원하는 경우에 사용할 수 있습니다는 `CPrintDialogEx` "있는 그대로" 제공 되는 생성자를 클래스 또는 대화 상자 클래스에서 파생 될 수 있습니다 `CPrintDialogEx` 하 고 필요에 맞게 생성자를 작성 합니다.  두 경우 모두 이러한 대화 상자 클래스에서 파생 된 때문에 표준 MFC 대화 상자 처럼 동작 합니다 `CCommonDialog`.  
  
 사용 하는 `CPrintDialogEx` 개체, 먼저 사용 하 여 개체를 만들는 `CPrintDialogEx` 생성자입니다.  대화 상자 생성 된 후에 설정 하거나 모든 값을 수정 된  [m\_pdex](../Topic/CPrintDialogEx::m_pdex.md) 구조는 대화 상자 컨트롤의 값을 초기화 합니다.  `m_pdex` 구조체의 형식이  [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844).  이 구조에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 핸들에서 지정 하지 않은 경우 `m_pdex` 에  **hDevMode** 및  **hDevNames** 구성원 Windows 함수를 호출 해야  **GlobalFree** 대화 상자를 완료 하면이 핸들에 대 한.  
  
 호출 대화 상자의 컨트롤을 초기화 한 후에 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 인쇄 옵션을 선택할 수 있습니다.  때 `DoModal` 을 반환 하는 사용자 확인, 적용 또는 취소 단추를 선택한 여부를 확인할 수 있습니다.  
  
 사용자가 확인을 누를 경우 수 `CPrintDialogEx`의 멤버 함수는 사용자가 입력 한 정보를 검색할 수 있습니다.  
  
 `CPrintDialogEx::GetDefaults` 멤버 함수 현재 프린터 기본값 대화 상자를 표시 하지 않고 검색 하는 데 유용 합니다.  이 메서드는 사용자 개입이 필요 합니다.  
  
 창 수  **CommDlgExtendedError** 함수 대화 상자를 초기화 하는 동안 오류가 있는지 여부를 확인 하 고 오류에 대 한 자세한.  이 함수에 대 한 자세한 내용은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 사용에 대 한 자세한 내용은 `CPrintDialogEx`를 참조 하십시오  [공용 대화 상자 클래스](../../mfc/common-dialog-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPrintInfo Structure](../../mfc/reference/cprintinfo-structure.md)