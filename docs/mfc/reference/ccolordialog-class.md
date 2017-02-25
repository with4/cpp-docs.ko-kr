---
title: "CColorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColorDialog class"
  - "색, 대화 상자"
  - "대화 상자, 색"
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

색 선택 대화 상자를 응용 프로그램에 통합할 수 있습니다.  
  
## 구문  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CColorDialog::CColorDialog](../Topic/CColorDialog::CColorDialog.md)|`CColorDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CColorDialog::DoModal](../Topic/CColorDialog::DoModal.md)|색 대화 상자를 표시 하 고 사용자가 선택할 수 있습니다.|  
|[CColorDialog::GetColor](../Topic/CColorDialog::GetColor.md)|반환 된  **COLORREF** 선택한 색의 값을 포함 하는 구조입니다.|  
|[CColorDialog::GetSavedCustomColors](../Topic/CColorDialog::GetSavedCustomColors.md)|사용자가 만든 사용자 지정 색을 검색 합니다.|  
|[CColorDialog::SetCurrentColor](../Topic/CColorDialog::SetCurrentColor.md)|지정 된 색 현재 색 선택이 됩니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CColorDialog::OnColorOK](../Topic/CColorDialog::OnColorOK.md)|색 대화 상자에 입력 유효성 검사를 무시 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CColorDialog::m\_cc](../Topic/CColorDialog::m_cc.md)|설정 대화 상자의 사용자 지정 하는 데 사용 되는 구조입니다.|  
  
## 설명  
 A `CColorDialog` 개체 목록이 있는 대화 상자가 디스플레이 시스템에 정의 된 색입니다.  사용자가 선택 하거나 대화 상자를 종료할 때 다음 응용 프로그램을 다시 보고 되는 목록에서 특정 색상을 만들 수 있습니다.  
  
 생성 하는 `CColorDialog` 개체, 제공 된 생성자를 사용 하거나 새 클래스를 파생 및 고유의 사용자 지정 생성자를 사용 합니다.  
  
 대화 상자 생성 된 후에 설정 하거나 모든 값을 수정 된[m\_cc](../Topic/CColorDialog::m_cc.md) 구조는 대화 상자 컨트롤의 값을 초기화 합니다.  `m_cc` 구조체의 형식이  [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 호출 대화 상자의 컨트롤을 초기화 한 후에 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 색을 선택할 수 있습니다.  `DoModal`사용자 선택 대화 상자의 확인 반환 \(**IDOK**\) 또는 취소 \(**IDCANCEL**\) 단추.  
  
 경우 `DoModal` 반환  **IDOK**, 중 하나를 사용할 수 있습니다 `CColorDialog`의 멤버 함수는 사용자가 입력 한 정보를 검색할 수 있습니다.  
  
 창 수  [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 대화 상자를 초기화 하는 동안 오류가 있는지 여부를 확인 하 고 오류에 대 한 자세한.  
  
 `CColorDialog`COMMDLG에 의존합니다.Windows 3.1 및 이후 버전에 제공 되는 DLL 파일입니다.  
  
 사용자 지정 대화 상자에는 클래스에서 파생 `CColorDialog`확장된 컨트롤에서 알림 메시지를 처리 하는 메시지 맵 추가, 사용자 지정 대화 상자 템플릿을 제공 합니다.  처리 되지 않은 모든 메시지는 기본 클래스에 전달 합니다.  
  
 후크 함수를 사용자 지정 하지 않아도 됩니다.  
  
> [!NOTE]
>  일부 설치에는 `CColorDialog` 다른 수 있도록 프레임 워크를 사용한 경우 회색 배경으로 수 개체가 표시 되지 않습니다 `CDialog` 회색 개체입니다.  
  
 사용에 대 한 자세한 내용은 `CColorDialog`를 참조 하십시오  [공용 대화 상자 클래스](../../mfc/common-dialog-classes.md)  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## 요구 사항  
 **헤더:**  afxdlgs.h  
  
## 참고 항목  
 [MFC MDI 샘플](../../top/visual-cpp-samples.md)   
 [MFC DRAWCLI 샘플](../../top/visual-cpp-samples.md)   
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)