---
title: "CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO[C++], DDX(대화 상자 데이터 교환) 지원"
  - "데이터베이스[C++], DDX(대화 상자 데이터 교환) 지원"
  - "DDX(대화 상자 데이터 교환)[C++], 데이터베이스 지원"
  - "DDX(대화 상자 데이터 교환)[C++], 함수"
  - "DDX_Field 함수"
  - "ODBC[C++], DDX(대화 상자 데이터 교환) 지원"
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 [CRecordset](../../mfc/reference/crecordset-class.md) 및 [CRecordView](../../mfc/reference/crecordview-class.md) 양식 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 및 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 양식 간에 데이터를 교환하기 위해 사용되는 DDX\_Field 함수를 작성합니다.  
  
> [!NOTE]
>  DDX\_Field 함수는 폼 컨트롤을 사용하여 데이터를 교환한다는 점에서 DDX 함수와 비슷합니다.  그러나 DDX와 다르게, DDX\_Field 함수는 자체 레코드 뷰의 필드를 사용하는 대신 뷰의 연관된 레코드 집합 개체의 필드를 사용하여 데이터를 교환합니다.  자세한 내용은, 클래스 `CRecordView` 및 `CDaoRecordView`을 참조하십시오.  
  
### DDX\_Field 함수  
  
|||  
|-|-|  
|[DDX\_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|레코드 집합 필드 데이터 멤버와 [CRecordView](../../mfc/reference/crecordview-class.md) 또는 [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) 안의 콤보 상자의 현재 선택 영역의 인덱스 사이에서 정수 데이터를 전송합니다.|  
|[DDX\_FieldCBString](../Topic/DDX_FieldCBString.md)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView` 안의 콤보 상자의 편집 컨트롤 사이에서 `CString` 데이터를 전송합니다.  레코드 집합에서 컨트롤로 데이터를 이동시킬 때, 이 함수는 지정된 문자열 안의 문자로 시작하는 콤보 상자에서 항목을 선택합니다.|  
|[DDX\_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView` 안의 콤보 상자의 편집 컨트롤 사이에서 `CString` 데이터를 전송합니다.  레코드 집합에서 컨트롤로 데이터를 이동시킬 때, 이 함수는 지정된 문자열과 정확히 일치하는 콤보 상자에서 항목을 선택합니다.|  
|[DDX\_FieldCheck](../Topic/DDX_FieldCheck.md)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView` 안의 확인란 사이에서 부울 데이터를 전송합니다.|  
|[DDX\_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView` 안의 목록 상자의 현재 선택 영역의 인덱스 사이에서 정수 데이터를 전송합니다.|  
|[DDX\_FieldLBString](../Topic/DDX_FieldLBString.md)|목록 상자 컨트롤과 레코드 집합의 필드 데이터 멤버 사이에서 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 데이터 전송을 관리합니다.  레코드 집합에서 컨트롤로 데이터를 이동시킬 때, 이 함수는 지정된 문자열 안의 문자로 시작하는 목록 상자에서 항목을 선택합니다.|  
|[DDX\_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|목록 상자 컨트롤과 레코드 집합의 필드 데이터 멤버 사이에서 `CString` 데이터 전송을 관리합니다.  레코드 집합에서 컨트롤로 데이터를 이동시킬 때, 이 함수는 지정된 문자열과 정확히 일치하는 첫번째 항목을 선택합니다.|  
|[DDX\_FieldRadio](../Topic/DDX_FieldRadio.md)|레코드 집합 필드 데이터 멤버와 `CRecordView` 또는 `CDaoRecordView`의 라디오 단추 그룹 사이에서 정수 데이터를 전송합니다.|  
|[DDX\_FieldScroll](../Topic/DDX_FieldScroll.md)|`CRecordView` 또는 `CDaoRecordView`에서 스크롤 막대 컨트롤의 스크롤 위치를 가져오거나 설정합니다.  사용자의 [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) 함수로부터 호출합니다.|  
|[DDX\_FieldText](../Topic/DDX_FieldText.md)|오버로드된 버전이 `CRecordView` 또는 `CDaoRecordView`의 레코드 집합 필드 데이터 멤버와 편집 박스 사이에서 `int`, **UINT**, **long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **short**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), [COleCurrency](../../mfc/reference/colecurrency-class.md) 데이터를 전송하는 것이 가능합니다.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)