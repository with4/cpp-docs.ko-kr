---
title: "CRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordView 클래스"
  - "ODBC 레코드 집합, viewing records"
  - "레코드, viewing ODBC"
  - "뷰, ODBC"
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤에서 데이터베이스 레코드를 표시 하는 보기입니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRecordView::CRecordView](../Topic/CRecordView::CRecordView.md)|`CRecordView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRecordView::IsOnFirstRecord](../Topic/CRecordView::IsOnFirstRecord.md)|현재 레코드는 연결 된 레코드 집합의 첫 번째 레코드일 경우 0이 아닌 값을 반환 합니다.|  
|[CRecordView::IsOnLastRecord](../Topic/CRecordView::IsOnLastRecord.md)|연결 된 레코드 집합의 마지막 레코드로 현재 레코드 않으면 0을 반환 합니다.|  
|[CRecordView::OnGetRecordset](../Topic/CRecordView::OnGetRecordset.md)|파생 된 클래스의 개체에 대 한 포인터를 반환 `CRecordset`.  클래스 마법사를이 함수를 재정의 하 고 필요한 경우 레코드 집합을 만듭니다.|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)||  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRecordView::OnMove](../Topic/CRecordView::OnMove.md)|현재 레코드가 변경 되 면 데이터 소스를 업데이트 하 고 지정 된 레코드로 이동 \(다음, 이전, 첫째 또는 마지막\).|  
  
## 설명  
 보기 양식 보기에 직접 연결 되는 `CRecordset` 개체입니다.  보기 대화 상자 템플릿 리소스를 만들어 필드의 표시는 `CRecordset` 대화 상자 템플릿의 컨트롤에 개체입니다.  `CRecordView` 개체를 사용 하 고 레코드 필드 교환 \(RFX\) 대화 상자 데이터 교환 \(DDX\) 레코드 집합의 필드를 폼에 있는 컨트롤 사이의 데이터 이동을 자동화 합니다.  `CRecordView`또한 이동 하는 기본 구현을 제공 하는 첫 번째 다음, 이전 또는 마지막 레코드 및 보기의 현재 기록을 업데이트 하는 인터페이스입니다.  
  
> [!NOTE]
>  개방형 데이터베이스 연결 \(ODBC\) 클래스 대신 데이터 액세스 개체 \(DAO\) 클래스를 작업 하는 경우 클래스 사용  [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 대신 합니다.  자세한 내용은  [개요: 데이터베이스 프로그래밍](../../data/data-access-programming-mfc-atl.md).  
  
 레코드 뷰를 작성 하는 가장 일반적인 방법은 응용 프로그램 마법사에 있습니다.  Tge 응용 프로그램 마법사는 레코드 뷰 클래스와 연결 된 레코드 집합 클래스 기초 시작 응용 프로그램의 일부로 만들어집니다.  응용 프로그램 마법사에서 레코드 뷰 클래스를 만들지 않을 경우 클래스 마법사를 나중에 만들 수 있습니다.  단일 폼을 간단 하 게 해야 하는 경우 응용 프로그램 마법사 방법은 쉽습니다.  클래스 마법사 개발 프로세스에서 나중에 사용 하는 레코드 보기를 결정할 수 있습니다.  클래스 마법사를 사용 하 여 레코드 뷰 및 레코드 집합을 별도로 만드는 다음 이들을 연결 하는 가장 유연한 방법은 명명 된 레코드 집합 클래스에서 더 많은 컨트롤을 제공 하기 때문에 및 해당.H \/.CPP 파일입니다.  또한이 방법은 같은 레코드 집합 클래스에서 레코드 뷰가 여러 개 있을 수 있습니다.  
  
 쉽게 레코드 보기에서 레코드를 이동 하는 최종 사용자를 위한 메뉴와 선택적 도구 모음 응용 프로그램 마법사를 만듭니다 이동 하기 위한 리소스를 첫 번째, 다음, 이전 또는 마지막 레코드.  클래스 마법사와 레코드 뷰 클래스를 만드는 경우 이러한 리소스는 메뉴 및 비트맵을 편집기 만들어야 할.  
  
 레코드에서 이동 하기 위한 기본 구현에 대 한 자세한 내용은 `IsOnFirstRecord` 및 `IsOnLastRecord` 및 문서  [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md).  
  
 `CRecordView`사용자의 위치는 레코드 집합에서 레코드 뷰의 사용자 인터페이스를 업데이트할 수 있도록 추적 합니다.  레코드 보기 레코드 집합의 양쪽 끝을 이동할 때 사용자 인터페이스 개체를 비활성화\-메뉴 항목 또는 도구 모음 단추\-이동 같은 방향에서.  
  
 자세한 정보를 선언 하 고 레코드 뷰와 레코드 집합 클래스를 사용 하 여 "디자인 및 만들기는 레코드 뷰"는 문서를 참조 하십시오  [레코드 뷰](../../data/record-views-mfc-data-access.md).  작업 레코드를 어떻게 표시 및 사용 방법에 대 한 자세한 내용은  [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)