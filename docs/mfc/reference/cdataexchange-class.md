---
title: "CDataExchange Class | Microsoft Docs"
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
  - "CDataExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataExchange class"
  - "DDV (dialog data validation)"
  - "DDV (dialog data validation), custom DDV routines"
  - "DDX(대화 상자 데이터 교환)"
  - "DDX(대화 상자 데이터 교환), between dialog and CDialog"
  - "DDX(대화 상자 데이터 교환), custom DDX routines"
  - "DDX(대화 상자 데이터 교환), direction of exchange"
  - "DDX/DDV"
  - "DDX/DDV, CDataExchange class"
  - "DDX/DDV, Technical Note 26"
  - "exchanging data between dialogs and CDialogs"
  - "m_bSaveAndValidate"
  - "데이터 유효성 검사, dialog box data entry"
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대화 상자 데이터 교환 \(DDX\) 및 mfc에서 사용 되는 대화 상자 데이터 유효성 검사 \(DDV\) 루틴을 지원 합니다.  
  
## 구문  
  
```  
class CDataExchange  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDataExchange::CDataExchange](../Topic/CDataExchange::CDataExchange.md)|`CDataExchange` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDataExchange::Fail](../Topic/CDataExchange::Fail.md)|유효성 검사에 실패 하면 호출 됩니다.  이전 컨트롤에 포커스를 다시 설정 하 고 예외를 throw 합니다.|  
|[CDataExchange::PrepareCtrl](../Topic/CDataExchange::PrepareCtrl.md)|지정 된 컨트롤에 데이터 교환 또는 유효성 검사를 준비합니다.  Nonedit 컨트롤을 사용 합니다.|  
|[CDataExchange::PrepareEditCtrl](../Topic/CDataExchange::PrepareEditCtrl.md)|데이터 교환 또는 유효성 검사에 대 한 지정 된 편집 컨트롤을 준비합니다.|  
|[CDataExchange::PrepareOleCtrl](../Topic/CDataExchange::PrepareOleCtrl.md)|지정 된 OLE 컨트롤 데이터 교환 또는 유효성 검사를 준비합니다.  Nonedit 컨트롤을 사용 합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDataExchange::m\_bSaveAndValidate](../Topic/CDataExchange::m_bSaveAndValidate.md)|DDX 및 DDV 방향에 대 한 플래그를 지정 합니다.|  
|[CDataExchange::m\_pDlgWnd](../Topic/CDataExchange::m_pDlgWnd.md)|대화 상자 또는 창 위치 데이터 교환 됩니다.|  
  
## 설명  
 `CDataExchange`기본 클래스에 없는 것입니다.  
  
 사용자 지정 데이터 형식 또는 컨트롤에 대 한 데이터 교환 루틴을 작성 하는 경우이 클래스를 사용 하거나 사용자 고유의 데이터 유효성 검사 루틴을 작성 하는 경우.  자신의 DDX 및 DDV 루틴에 대 한 자세한 내용은  [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md).  DDX 및 DDV 개요  [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및  [대화 상자](../../mfc/dialog-boxes.md).  
  
 A `CDataExchange` 개체 배치 DDX 및 DDV 데 필요한 컨텍스트 정보를 제공 합니다.  플래그 `m_bSaveAndValidate` 는  **FALSE** 때 DDX 사용 대화 상자 컨트롤에서 데이터 멤버의 초기 값을 입력 합니다.  플래그 `m_bSaveAndValidate` 는  **TRUE** 때 DDX 사용 데이터 멤버 및 DDV를 사용 하 여 데이터 값을 검사할 때에 대화 상자 컨트롤의 현재 값을 설정 합니다.  DDV 유효성 검사에 실패할 경우 DDV 프로시저 입력된 오류를 설명 하는 메시지 상자가 표시 됩니다.  DDV 프로시저 호출 다음  **실패** 잘못 된 컨트롤에 포커스를 다시 설정 하 여 유효성 검사 프로세스를 중지 하려면 예외를 throw 합니다.  
  
## 상속 계층 구조  
 `CDataExchange`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [VIEWEX MFC 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)