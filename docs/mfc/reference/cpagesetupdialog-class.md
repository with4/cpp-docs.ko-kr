---
title: "CPageSetupDialog Class | Microsoft Docs"
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
  - "CPageSetupDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPageSetupDialog class"
  - "OLE Page Setup dialog box"
  - "페이지 설정"
  - "페이지 설정 대화 상자"
  - "Print Setup dialog box"
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPageSetupDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 일반 OLE 페이지 설정 대화 상자에서 설정 하 고 인쇄 여백 수정에 대 한 추가 지원을 제공 되는 서비스를 캡슐화 합니다.  
  
## 구문  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CPageSetupDialog::CPageSetupDialog](../Topic/CPageSetupDialog::CPageSetupDialog.md)|`CPageSetupDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPageSetupDialog::CreatePrinterDC](../Topic/CPageSetupDialog::CreatePrinterDC.md)|인쇄에 대 한 장치 컨텍스트를 만듭니다.|  
|[CPageSetupDialog::DoModal](../Topic/CPageSetupDialog::DoModal.md)|대화 상자를 표시 하 고 사용자 만들기를 선택할 수 있습니다.|  
|[CPageSetupDialog::GetDeviceName](../Topic/CPageSetupDialog::GetDeviceName.md)|프린터의 장치 이름을 반환합니다.|  
|[CPageSetupDialog::GetDevMode](../Topic/CPageSetupDialog::GetDevMode.md)|현재 반환 `DEVMODE` 프린터.|  
|[CPageSetupDialog::GetDriverName](../Topic/CPageSetupDialog::GetDriverName.md)|프린터에서 사용 되는 드라이버를 반환 합니다.|  
|[CPageSetupDialog::GetMargins](../Topic/CPageSetupDialog::GetMargins.md)|현재 프린터의 여백 설정을 반환합니다.|  
|[CPageSetupDialog::GetPaperSize](../Topic/CPageSetupDialog::GetPaperSize.md)|프린터의 용지 크기를 반환합니다.|  
|[CPageSetupDialog::GetPortName](../Topic/CPageSetupDialog::GetPortName.md)|출력 포트 이름을 반환합니다.|  
|[CPageSetupDialog::OnDrawPage](../Topic/CPageSetupDialog::OnDrawPage.md)|인쇄 된 페이지의 화면 이미지를 렌더링 하는 프레임 워크에서 호출 됩니다.|  
|[CPageSetupDialog::PreDrawPage](../Topic/CPageSetupDialog::PreDrawPage.md)|프레임 워크에서 인쇄 된 페이지의 화면 이미지를 렌더링 하기 전에 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPageSetupDialog::m\_psd](../Topic/CPageSetupDialog::m_psd.md)|사용자 지정 하는 데 사용 되는 구조체는 `CPageSetupDialog` 개체입니다.|  
  
## 설명  
 이 클래스는 인쇄 설정 대화 상자를 대신 하도록 설계 되었습니다.  
  
 사용 하는 `CPageSetupDialog` 개체, 먼저 사용 하 여 개체를 만들는 `CPageSetupDialog` 생성자입니다.  대화 상자 생성 된 후에 설정 하거나 모든 값을 수정의 `m_psd` 데이터 멤버는 대화 상자 컨트롤의 값을 초기화 합니다.  [M\_psd](../Topic/CPageSetupDialog::m_psd.md) 구조체의 형식이  **PAGESETUPDLG**.  
  
 호출 대화 상자의 컨트롤을 초기화 한 후에 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 인쇄 옵션을 선택할 수 있습니다.  `DoModal`사용자가 확인 선택 여부를 반환 \(**IDOK**\) 또는 취소 \(**IDCANCEL**\) 단추.  
  
 경우 `DoModal` 반환  **IDOK**를 여러 개 사용할 수 있습니다 `CPageSetupDialog`의 멤버 함수 또는 액세스를 `m_psd` 검색 사용자가 정보를 입력 하는 데이터 멤버를.  
  
> [!NOTE]
>  일반 OLE 페이지 설정 대화 상자를 해제 한 후 프레임 워크에서 사용자가 변경 내용을 저장 되지 않습니다.  이 대화 상자에서 응용 프로그램의 문서 또는 응용 프로그램 클래스의 멤버와 같은 영구적인 위치에 값을 저장 하면 응용 프로그램이 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [MFC 샘플 워드 패드](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)