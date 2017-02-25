---
title: "CDaoRecordView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 마법사[C++], creating record views"
  - "바인딩 컨트롤[C++], displaying database data"
  - "CDaoRecordView 클래스"
  - "컨트롤[MFC], data binding"
  - "데이터 바인딩[C++], DAO views"
  - "데이터 바인딩 컨트롤[C++], DAO 컨트롤"
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoRecordView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컨트롤에서 데이터베이스 레코드를 표시 하는 보기입니다.  
  
## 구문  
  
```  
  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDaoRecordView::CDaoRecordView](../Topic/CDaoRecordView::CDaoRecordView.md)|`CDaoRecordView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDaoRecordView::IsOnFirstRecord](../Topic/CDaoRecordView::IsOnFirstRecord.md)|현재 레코드는 연결 된 레코드 집합의 첫 번째 레코드일 경우 0이 아닌 값을 반환 합니다.|  
|[CDaoRecordView::IsOnLastRecord](../Topic/CDaoRecordView::IsOnLastRecord.md)|연결 된 레코드 집합의 마지막 레코드로 현재 레코드 않으면 0을 반환 합니다.|  
|[CDaoRecordView::OnGetRecordset](../Topic/CDaoRecordView::OnGetRecordset.md)|파생 된 클래스의 개체에 대 한 포인터를 반환 `CDaoRecordset`.  클래스 마법사를이 함수를 재정의 하 고 필요한 경우 레코드 집합을 만듭니다.|  
|[CDaoRecordView::OnMove](../Topic/CDaoRecordView::OnMove.md)|현재 레코드가 변경 되 면 데이터 소스를 업데이트 하 고 지정 된 레코드로 이동 \(다음, 이전, 첫째 또는 마지막\).|  
  
## 설명  
 보기 양식 보기에 직접 연결 되는 `CDaoRecordset` 개체입니다.  보기 대화 상자 템플릿 리소스를 만들어 필드의 표시는 `CDaoRecordset` 대화 상자 템플릿의 컨트롤에 개체입니다.  `CDaoRecordView` 개체를 사용 하 고 DAO 레코드 필드 교환 \(DFX\) 대화 상자 데이터 교환 \(DDX\) 레코드 집합의 필드를 폼에 있는 컨트롤 사이의 데이터 이동을 자동화 합니다.  `CDaoRecordView`또한 이동 하는 기본 구현을 제공 하는 첫 번째 인터페이스 보기에서 현재 레코드를 업데이트 한 다음, 이전 또는 마지막 레코드입니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스는 개방형 데이터베이스 연결 \(ODBC\)에 따라 MFC 데이터베이스 클래스와는 별개입니다.  모든 DAO 데이터베이스 클래스 이름을 "CDao" 접두사가 있습니다.  여전히 DAO 클래스가 ODBC 데이터 소스를 액세스 할 수 있습니다. DAO 클래스는 Microsoft Jet 데이터베이스 엔진을 사용 하기 때문에 일반적으로 탁월한 능력을 제공.  
  
 레코드 뷰를 작성 하는 가장 일반적인 방법은 응용 프로그램 마법사에 있습니다.  응용 프로그램 마법사는 레코드 뷰 클래스와 연결 된 레코드 집합 클래스 기초 시작 응용 프로그램의 일부로 만듭니다.  
  
 단일 폼을 간단 하 게 해야 하는 경우 응용 프로그램 마법사 방법은 쉽습니다.  클래스 마법사 개발 프로세스에서 나중에 사용 하는 레코드 보기를 결정할 수 있습니다.  응용 프로그램 마법사에서 레코드 뷰 클래스를 만들지 않을 경우 클래스 마법사를 나중에 만들 수 있습니다.  클래스 마법사를 사용 하 여 레코드 뷰 및 레코드 집합을 별도로 만드는 다음 이들을 연결 하는 가장 유연한 방법은 명명 된 레코드 집합 클래스에서 더 많은 컨트롤을 제공 하기 때문에 및 해당.H \/.CPP 파일입니다.  또한이 방법은 같은 레코드 집합 클래스에서 레코드 뷰가 여러 개 있을 수 있습니다.  
  
 쉽게 레코드 보기에서 레코드를 이동 하는 최종 사용자를 위한 메뉴와 선택적 도구 모음 응용 프로그램 마법사를 만듭니다 이동 하기 위한 리소스를 첫 번째, 다음, 이전 또는 마지막 레코드.  클래스 마법사와 레코드 뷰 클래스를 만드는 경우 이러한 리소스는 메뉴 및 비트맵을 편집기 만들어야 할.  
  
 레코드에서 이동 하기 위한 기본 구현에 대 한 자세한 내용은 `IsOnFirstRecord` 및 `IsOnLastRecord` 및 문서  [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md), 적용에 모두 `CRecordView` 및 `CDaoRecordView`.  
  
 `CDaoRecordView`사용자의 위치는 레코드 집합에서 레코드 뷰의 사용자 인터페이스를 업데이트할 수 있도록 추적 합니다.  레코드 보기 레코드 집합의 양쪽 끝을 이동할 때 사용자 인터페이스 개체를 비활성화\-메뉴 항목 또는 도구 모음 단추\-이동 같은 방향에서.  
  
 자세한 정보를 선언 하 고 레코드 뷰와 레코드 집합 클래스를 사용 하 여 "디자인 및 만들기는 레코드 뷰"는 문서를 참조 하십시오  [레코드 뷰](../../data/record-views-mfc-data-access.md).  작업 레코드를 어떻게 표시 및 사용 방법에 대 한 자세한 내용은  [레코드 뷰를 사용 하 여](../../data/using-a-record-view-mfc-data-access.md).  위에서 언급 한 모든 문서에 모두 적용 `CRecordView` 및 `CDaoRecordView`.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## 요구 사항  
 **헤더:**  afxdao.h  
  
## 참고 항목  
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)