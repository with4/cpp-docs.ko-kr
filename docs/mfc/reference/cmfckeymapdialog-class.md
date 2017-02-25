---
title: "CMFCKeyMapDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCKeyMapDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCKeyMapDialog class"
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCKeyMapDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCKeyMapDialog` 클래스 지원 컨트롤 명령을 키보드 키를 매핑합니다.  
  
## 구문  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](../Topic/CMFCKeyMapDialog::CMFCKeyMapDialog.md)|`CMFCKeyMapDialog` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCKeyMapDialog::DoModal](../Topic/CMFCKeyMapDialog::DoModal.md)|키보드 매핑 대화 상자를 표시합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCKeyMapDialog::FormatItem](../Topic/CMFCKeyMapDialog::FormatItem.md)|키 매핑을 설명 하는 문자열을 작성 하는 프레임 워크에서 호출 됩니다.  기본적으로 명령 이름이 사용 되는 바로 가기 키, 바로 가기 키 설명을 문자열을 포함 합니다.|  
|[CMFCKeyMapDialog::GetCommandKeys](../Topic/CMFCKeyMapDialog::GetCommandKeys.md)|지정 된 명령과 연결 된 바로 가기 키 목록이 들어 있는 문자열을 검색 합니다.|  
|[CMFCKeyMapDialog::OnInsertItem](../Topic/CMFCKeyMapDialog::OnInsertItem.md)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에 새 항목을 삽입 하기 전에 프레임 워크에서 호출 됩니다.|  
|[CMFCKeyMapDialog::OnPrintHeader](../Topic/CMFCKeyMapDialog::OnPrintHeader.md)|키보드 맵에 대 한 머리글을 새 페이지에 인쇄 하려면 프레임 워크에서 호출 합니다.|  
|[CMFCKeyMapDialog::OnPrintItem](../Topic/CMFCKeyMapDialog::OnPrintItem.md)|키보드 매핑 항목을 인쇄 하려면 프레임 워크에서 호출 됩니다.|  
|[CMFCKeyMapDialog::OnSetColumns](../Topic/CMFCKeyMapDialog::OnSetColumns.md)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에서 열에 대 한 캡션을 설정 하는 프레임 워크에서 호출 합니다.|  
|[CMFCKeyMapDialog::PrintKeyMap](../Topic/CMFCKeyMapDialog::PrintKeyMap.md)|클릭할 때 프레임 워크에 의해 호출 된  **인쇄** 단추.|  
|[CMFCKeyMapDialog::SetColumnsWidth](../Topic/CMFCKeyMapDialog::SetColumnsWidth.md)|키보드 매핑 컨트롤을 지 원하는 내부 목록 컨트롤에 열 너비를 설정 하는 프레임 워크에서 호출 합니다.|  
  
## 설명  
 사용 된 `CMFCKeyMapDialog` 크기 조정 가능한 키보드 매핑 대화 상자를 구현 하는 클래스입니다.  대화 상자 바로 가기 키와 관련된 명령을 표시 하려면 list view 컨트롤을 사용 합니다.  
  
 사용 하는 `CMFCKeyMapDialog` 응용 프로그램에서 클래스, 매개 변수로 주 프레임 창에 전달 하는 포인터에는 `CMFCKeyMapDialog` 생성자입니다.  다음 호출에서 `DoModal` 메서드는 모달 대화 상자를 시작 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## 요구 사항  
 **헤더:** afxkeymapdialog.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager Class](../../mfc/reference/ckeyboardmanager-class.md)