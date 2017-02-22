---
title: "CPrintInfo Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPrintInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrintInfo structure"
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPrintInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인쇄 또는 인쇄 미리 보기 작업에 대 한 정보를 저장합니다.  
  
## 구문  
  
```  
struct CPrintInfo  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CPrintInfo::GetFromPage](../Topic/CPrintInfo::GetFromPage.md)|인쇄할 첫 페이지의 수를 반환 합니다.|  
|[CPrintInfo::GetMaxPage](../Topic/CPrintInfo::GetMaxPage.md)|문서의 마지막 페이지 번호를 반환합니다.|  
|[CPrintInfo::GetMinPage](../Topic/CPrintInfo::GetMinPage.md)|문서의 첫 번째 페이지 번호를 반환합니다.|  
|[CPrintInfo::GetOffsetPage](../Topic/CPrintInfo::GetOffsetPage.md)|결합 된 DocObject 인쇄 작업에서 인쇄 중인 DocObject 항목의 첫 번째 페이지의 앞 페이지 수를 반환 합니다.|  
|[CPrintInfo::GetToPage](../Topic/CPrintInfo::GetToPage.md)|인쇄할 마지막 페이지를 반환 합니다.|  
|[CPrintInfo::SetMaxPage](../Topic/CPrintInfo::SetMaxPage.md)|문서의 마지막 페이지 번호를 설정합니다.|  
|[CPrintInfo::SetMinPage](../Topic/CPrintInfo::SetMinPage.md)|문서의 첫 번째 페이지 번호를 설정합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CPrintInfo::m\_bContinuePrinting](../Topic/CPrintInfo::m_bContinuePrinting.md)|프레임 워크는 인쇄 루프를 계속 해야 하는지 나타내는 플래그를 포함 합니다.|  
|[CPrintInfo::m\_bDirect](../Topic/CPrintInfo::m_bDirect.md)|문서 직접 \(인쇄 대화 상자를 표시 하지 않고\) 인쇄 되 고 있는지 여부를 나타내는 플래그를 포함 합니다.|  
|[CPrintInfo::m\_bDocObject](../Topic/CPrintInfo::m_bDocObject.md)|인쇄 중인 문서는 DocObject 인지 여부를 나타내는 플래그를 포함 합니다.|  
|[CPrintInfo::m\_bPreview](../Topic/CPrintInfo::m_bPreview.md)|문서를 미리 볼 것인지를 나타내는 플래그를 포함 합니다.|  
|[CPrintInfo::m\_dwFlags](../Topic/CPrintInfo::m_dwFlags.md)|Docobject의 인쇄 작업을 지정합니다.|  
|[CPrintInfo::m\_lpUserData](../Topic/CPrintInfo::m_lpUserData.md)|사용자가 만든 구조에 대 한 포인터를 포함 합니다.|  
|[CPrintInfo::m\_nCurPage](../Topic/CPrintInfo::m_nCurPage.md)|현재 인쇄 중인 페이지를 식별 합니다.|  
|[CPrintInfo::m\_nJobNumber](../Topic/CPrintInfo::m_nJobNumber.md)|현재 인쇄 작업에 대 한 운영 체제에 의해 할당 된 작업 번호를 지정 합니다.|  
|[CPrintInfo::m\_nNumPreviewPages](../Topic/CPrintInfo::m_nNumPreviewPages.md)|미리 보기 창에 표시 되는 페이지의 번호를 나타냅니다. 1 또는 2입니다.|  
|[CPrintInfo::m\_nOffsetPage](../Topic/CPrintInfo::m_nOffsetPage.md)|결합 된 DocObject 인쇄 작업에서 특정 Docobject의 첫 번째 페이지의 오프셋을 지정합니다.|  
|[CPrintInfo::m\_pPD](../Topic/CPrintInfo::m_pPD.md)|포인터를 포함의 `CPrintDialog` 개체에 대 한 인쇄 대화 상자를 사용 합니다.|  
|[CPrintInfo::m\_rectDraw](../Topic/CPrintInfo::m_rectDraw.md)|현재 사용할 수 있는 페이지 영역을 정의 하는 사각형을 지정 합니다.|  
|[CPrintInfo::m\_strPageDesc](../Topic/CPrintInfo::m_strPageDesc.md)|페이지 번호 표시에 대 한 형식 문자열을 포함 합니다.|  
  
## 설명  
 `CPrintInfo`구조 이며는 기본 클래스가 없습니다.  
  
 개체의 프레임 워크를 만드는 `CPrintInfo` 때마다 인쇄 또는 인쇄 미리 보기 명령을 선택 하 고 명령이 완료 되 면 삭제 합니다.  
  
 `CPrintInfo`인쇄할 페이지 범위와 같은 전체 인쇄 작업이 현재 인쇄 중인 페이지 같은 인쇄 작업의 현재 상태에 대 한 정보가 들어 있습니다.  일부 정보가 저장 되는 연결에서  [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 개체입니다. 인쇄 대화 상자에서 사용자가 입력 한 값이이 개체를 포함 합니다.  
  
 A `CPrintInfo` 개체 프레임 워크에서 뷰 클래스 사이의 인쇄 과정에서 전달 되 고 서로 정보를 교환 하는 데 사용 됩니다.  예를 들어, 뷰 클래스의 값을 지정 하 여 인쇄할 문서 페이지 프레임 워크에 게 알립니다의 `m_nCurPage` 의 구성원 `CPrintInfo`. 뷰 클래스 값을 검색 하 고 지정 된 페이지의 실제 인쇄를 수행 합니다.  
  
 인쇄 될 때까지 문서의 길이 알 수 없는 또 다른 예가입니다.  이 이런 경우 페이지가 인쇄 될 때마다 문서 끝에 대 한 뷰 클래스를 테스트 합니다.  뷰 클래스의 끝에 도달 하면 설정 하는 `m_bContinuePrinting` 소속 `CPrintInfo` 에  **FALSE**. 이 인쇄 루프를 중지 하는 프레임 워크를 알립니다.  
  
 `CPrintInfo`멤버 함수가 사용 `CView` 나열 "참고도." Mfc 라이브러리에서 제공 하는 인쇄 아키텍처에 대 한 자세한 내용은  [프레임 Windows](../../mfc/frame-windows.md) 및  [문서\/뷰 아키텍처](../../mfc/document-view-architecture.md) 와 기사  [인쇄](../../mfc/printing.md) 및  [인쇄: Multipage 문서](../../mfc/multipage-documents.md).  
  
## 상속 계층 구조  
 `CPrintInfo`  
  
## 요구 사항  
 **헤더:**  afxext.h  
  
## 참고 항목  
 [Diblook에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)   
 [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md)   
 [CView::OnEndPrintPreview](../Topic/CView::OnEndPrintPreview.md)   
 [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)   
 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)