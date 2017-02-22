---
title: "CLongBinary Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "BLOB"
  - "CLongBinary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB(이진 대형 개체)"
  - "BLOB(이진 대형 개체), CLongBinary 클래스"
  - "CLongBinary 클래스"
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CLongBinary Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매우 큰 이진 데이터 개체 \(Blob, 또는 "이진 대형 개체" 라고도 함\) 데이터베이스에서 작업을 단순화 합니다.  
  
## 구문  
  
```  
class CLongBinary : public CObject  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CLongBinary::CLongBinary](../Topic/CLongBinary::CLongBinary.md)|`CLongBinary` 개체를 생성합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CLongBinary::m\_dwDataLength](../Topic/CLongBinary::m_dwDataLength.md)|실제 크기 \(바이트\)의 데이터 개체에 핸들을 저장 포함 `m_hData`.|  
|[CLongBinary::m\_hData](../Topic/CLongBinary::m_hData.md)|Windows에 포함 된 `HGLOBAL` 실제 이미지 개체를 처리 합니다.|  
  
## 설명  
 예를 들어, SQL 테이블에서 레코드 필드 비트맵 그림을 나타내는 포함 될 수 있습니다.  A `CLongBinary` 개체 이러한 개체를 저장 하 고 해당 크기를 추적 합니다.  
  
> [!NOTE]
>  일반적으로 사용 하기 좋습니다 이제는  [CByteArray](../../mfc/reference/cbytearray-class.md) 와 함께에서  [DFX\_Binary](../Topic/DFX_Binary.md) 함수입니다.  계속 사용할 수 없습니다 `CLongBinary`, 하지만 일반적 `CByteArray` 이상 이므로 16 비트 발생 크기 제한을 win32에서 더 많은 기능을 제공 합니다. `CByteArray`.  개방형 데이터베이스 연결 \(ODBC\) 뿐만 아니라 데이터 액세스 개체 \(DAO\) 프로그래밍이이 조언을 적용 됩니다.  
  
 사용 하는 `CLongBinary` 개체 형식의 필드 데이터 멤버 선언 `CLongBinary` 레코드 집합 클래스에서.  이 멤버 레코드 집합 클래스에 포함 된 구성원이 될 및 레코드 집합이 생성 될 때 생성 됩니다.  후에 `CLongBinary` 개체는 생성, 레코드 필드 교환 \(RFX\) 메커니즘 데이터 개체는 데이터 소스에서 현재 레코드의 필드에서 로드 하는 레코드가 업데이트 될 때 다시 레코드를 저장 합니다.  RFX는 데이터 소스 쿼리 크기의 이진 대형 개체 할당에 저장소를 \(통해는 `CLongBinary` 개체의 `m_hData` 데이터 멤버\), 저장 하 고는 `HGLOBAL` 데이터 처리 `m_hData`.  RFX는 저장 되는 데이터 개체의 실제 크기는 `m_dwDataLength` 데이터 멤버입니다.  데이터 개체를 통해 작업을 `m_hData`, Windows에 저장 된 데이터를 조작 하려면 일반적으로 사용 하는 동일한 기술을 사용 하 여 `HGLOBAL` 처리 합니다.  
  
 포함 된 recordset을 파괴 `CLongBinary` 개체를 소멸도 및 소멸자가 할당 된 `HGLOBAL` 데이터 핸들.  
  
 대형 개체 및 사용에 대 한 자세한 내용은 `CLongBinary`, 문서를 참조 하십시오.  [레코드 집합 \(ODBC\)](../../data/odbc/recordset-odbc.md) 및  [레코드 집합: 대형 데이터 항목 \(ODBC\) 작업](../../data/odbc/recordset-working-with-large-data-items-odbc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## 요구 사항  
 **헤더:**  afxdb\_.h  
  
## 참고 항목  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)