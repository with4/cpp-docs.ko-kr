---
title: "CDBVariant Class | Microsoft Docs"
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
  - "CDBVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBVariant 클래스"
  - "Variant 데이터 형식, ODBC"
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ODBC 클래스에 대 한 variant 데이터 형식을 나타냅니다.  
  
## 구문  
  
```  
class CDBVariant  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDBVariant::CDBVariant](../Topic/CDBVariant::CDBVariant.md)|`CDBVariant` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDBVariant::Clear](../Topic/CDBVariant::Clear.md)|취소는 `CDBVariant` 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDBVariant::m\_dwType](../Topic/CDBVariant::m_dwType.md)|현재 저장 된 값의 데이터 형식을 포함 합니다.  `DWORD`를 입력합니다.|  
  
### 공용 구조체 멤버 공개  
  
|Name|설명|  
|----------|--------|  
|[CDBVariant::m\_boolVal](../Topic/CDBVariant::m_boolVal.md)|형식의 값이 포함 된  **BOOL**.|  
|[CDBVariant::m\_chVal](../Topic/CDBVariant::m_chVal.md)|형식의 값이 포함 된 `unsigned char`.|  
|[CDBVariant::m\_dblVal](../Topic/CDBVariant::m_dblVal.md)|형식의 값이 포함 된  **이중**.|  
|[CDBVariant::m\_fltVal](../Topic/CDBVariant::m_fltVal.md)|형식의 값이 포함 된  **float**.|  
|[CDBVariant::m\_iVal](../Topic/CDBVariant::m_iVal.md)|형식의 값이 포함 된  **짧은**.|  
|[CDBVariant::m\_lVal](../Topic/CDBVariant::m_lVal.md)|형식의 값이 포함 된  **긴**.|  
|[CDBVariant::m\_pbinary](../Topic/CDBVariant::m_pbinary.md)|개체 형식에 대 한 포인터를 포함 합니다. `CLongBinary`.|  
|[CDBVariant::m\_pdate](../Topic/CDBVariant::m_pdate.md)|개체 형식에 대 한 포인터를 포함 합니다.  **TIMESTAMP\_STRUCT**.|  
|[CDBVariant::m\_pstring](../Topic/CDBVariant::m_pstring.md)|개체 형식에 대 한 포인터를 포함 합니다. `CString`.|  
|[CDBVariant::m\_pstringA](../Topic/CDBVariant::m_pstringA.md)|ASCII에 대 한 포인터를 저장 합니다.  [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|  
|[CDBVariant::m\_pstringW](../Topic/CDBVariant::m_pstringW.md)|전체에 대 한 포인터를 저장 합니다.  [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|  
  
## 설명  
 `CDBVariant`기본 클래스에 없는 것입니다.  
  
 `CDBVariant`유사한  [COleVariant](../../mfc/reference/colevariant-class.md). 그러나 `CDBVariant` OLE를 사용 하지 않습니다.  `CDBVariant`값의 데이터 형식에 대 한 걱정 없이 값을 저장할 수 있습니다.  `CDBVariant`공용 구조체에 저장 된 현재 값의 데이터 형식을 추적 합니다.  
  
 클래스  [CRecordset](../../mfc/reference/crecordset-class.md) 이용 `CDBVariant` 개체에는 세 가지 멤버 함수: `GetFieldValue`, `GetBookmark`, 및 `SetBookmark`.  예를 들어, `GetFieldValue` 동적 데이터 열에서 반입할 수 있습니다.  런타임에 열의 데이터 형식을 알 수 없습니다 때문에 `GetFieldValue` 사용 하는 `CDBVariant` 열의 데이터를 저장 하는 개체입니다.  
  
## 상속 계층 구조  
 `CDBVariant`  
  
## 요구 사항  
 **헤더:**  afxdb.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)   
 [CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)   
 [CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)