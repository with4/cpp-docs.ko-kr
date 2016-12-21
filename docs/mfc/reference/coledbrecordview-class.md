---
title: "COleDBRecordView Class | Microsoft Docs"
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
  - "COleDBRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDBRecordView 클래스"
  - "MFC, OLE DB"
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDBRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤에서 데이터베이스 레코드를 표시 하는 보기입니다.  
  
## 구문  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDBRecordView::COleDBRecordView](../Topic/COleDBRecordView::COleDBRecordView.md)|`COleDBRecordView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDBRecordView::OnGetRowset](../Topic/COleDBRecordView::OnGetRowset.md)|반환 하는 표준 `HRESULT` 값입니다.|  
|[COleDBRecordView::OnMove](../Topic/COleDBRecordView::OnMove.md)|\(변경 하는 경우\) 데이터 소스에 현재 레코드를 업데이트 한 다음 지정 된 레코드로 이동 \(다음, 이전, 첫째 또는 마지막\).|  
  
## 설명  
 보기 양식 보기에 직접 연결 되는 `CRowset` 개체입니다.  보기 대화 상자 템플릿 리소스를 만들어 필드의 표시는 `CRowset` 대화 상자 템플릿의 컨트롤에 개체입니다.  `COleDBRecordView` 개체 사용 하 여 대화 상자 데이터 교환 \(DDX\) 및 탐색 기능 내장 `CRowset`, 행 집합의 필드를 폼에 있는 컨트롤 사이의 데이터 이동을 자동화 합니다.  `COleDBRecordView`또한 이동 하는 기본 구현을 제공 하는 첫 번째 다음, 이전 또는 마지막 레코드 및 보기의 현재 기록을 업데이트 하는 인터페이스입니다.  
  
 DDX 함수를 **COleDbRecordView**와 사용하여 데이터베이스 레코드 집합의 데이터를 직접 구해서 대화 상자 컨트롤에 표시할 수 있습니다.  `DDX_FieldText` 같은 **DDX\_Field\*** 함수가 아닌 `DDX_Text` 같은 **DDX\_\*** 메서드를 **COleDbRecordView**와 함께 사용해야 합니다.  `DDX_FieldText`작동 하지 않습니다  **COleDbRecordView** 때문에 `DDX_FieldText` 형식의 추가 인수  **CRecordset \*** \(에 대 한 `CRecordView`\) 또는  **CDaoRecordset \*** \(에 대 한 `CDaoRecordView`\).  
  
> [!NOTE]
>  OLE DB 소비자 템플릿 클래스 대신 데이터 액세스 개체 \(DAO\) 클래스를 작업 하는 경우 클래스 사용  [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 대신 합니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 `COleDBRecordView`사용자의 위치가 행 집합에서 레코드 뷰의 사용자 인터페이스를 업데이트할 수 있도록 추적 합니다.  사용자가 행 집합의 한쪽 끝을 이동 하면 레코드 뷰 사용자 인터페이스 개체를 비활성화\-메뉴 항목 또는 도구 모음 단추\-이동 같은 방향에서.  
  
 행 집합 클래스에 대 한 자세한 내용은  [를 사용 하 여 OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md) 문서를 참조.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## 요구 사항  
 **헤더:**  afxoledb.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)