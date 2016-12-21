---
title: "레코드 집합: 대량 레코드 페치(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대량 레코드 필드 교환"
  - "대량 RFX 함수"
  - "대량 행 페칭(fetching)"
  - "대량 행 페칭(fetching), 구현"
  - "DoBulkFieldExchange 메서드"
  - "대량 ODBC 레코드 페칭(fetching)"
  - "ODBC 레코드 집합, 대량 행 페칭(fetching)"
  - "레코드 집합, 대량 행 페칭(fetching)"
  - "RFX(ODBC), 대량"
  - "RFX(ODBC), 대량 행 페칭(fetching)"
  - "행 집합, 대량 행 페칭(fetching)"
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 대량 레코드 페치(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 `CRecordset` 클래스는 대량 행 페치를 지원하므로 데이터 소스에서 레코드를 한 번에 하나씩 검색하는 것이 아니라 단일 페치 프로세스에서 여러 레코드를 동시에 검색할 수 있습니다.  대량 행 페치는 파생된 `CRecordset` 클래스에서만 구현할 수 있습니다.  데이터 소스에서 레코드 집합 개체로 데이터를 전송하는 프로세스를 대량 RFX라고 합니다.  `CRecordset`에서 파생된 클래스에서 대량 행 페치를 사용하지 않는 경우 데이터는 RFX\(레코드 필드 교환\)를 통해 전송됩니다.  자세한 내용은 [RFX](../../data/odbc/record-field-exchange-rfx.md)를 참조하십시오.  
  
 다음은 이 항목에서 설명하는 내용입니다.  
  
-   [CRecordset에서 대량 행 페치를 지원하는 방법](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [대량 행 페치를 사용할 때의 유의 사항](#_core_special_considerations).  
  
-   [대량 레코드 필드 교환을 구현하는 방법](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> CRecordset에서 대량 행 페치를 지원하는 방법  
 레코드 집합 개체를 열기 전에 `SetRowsetSize` 멤버 함수를 사용하여 행 집합 크기를 정의할 수 있습니다.  행 집합 크기는 단일 페치 프로세스에서 검색할 레코드 개수를 지정합니다.  대량 행 페치가 구현되면 기본 행 집합 크기는 25입니다.  대량 행 페치를 구현하지 않은 경우 행 집합 크기는 1로 고정됩니다.  
  
 행 집합 크기를 초기화한 후 [Open](../Topic/CRecordset::Open.md) 멤버 함수를 호출합니다.  대량 행 페치를 구현하려면 이 호출 구문의 **dwOptions** 매개 변수에 `CRecordset::useMultiRowFetch` 옵션을 지정해야 합니다.  추가로 **CRecordset::userAllocMultiRowBuffers** 옵션을 설정할 수 있습니다.  대량 레코드 필드 교환 메커니즘은 배열을 사용하여 페치 중에 검색된 여러 행의 데이터를 저장합니다.  이러한 저장 버퍼는 프레임워크에 의해 자동으로 할당될 수도 있고 사용자가 직접 할당할 수도 있습니다.  사용자가 직접 할당하려는 경우 **CRecordset::userAllocMultiRowBuffers** 옵션을 지정합니다.  
  
 다음 표에는 대량 행 페치를 지원하기 위해 `CRecordset` 클래스에서 제공하는 멤버 함수가 나와 있습니다.  
  
|멤버 함수|설명|  
|-----------|--------|  
|[CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|페치 중에 발생하는 모든 오류를 처리하는 가상 함수입니다.|  
|[DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|대량 레코드 필드 교환을 구현합니다.  데이터의 여러 행을 데이터 소스에서 레코드 집합 개체로 전송하기 위해 자동으로 호출됩니다.|  
|[GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|행 집합 크기의 현재 설정을 검색합니다.|  
|[GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|페치 후에 실제 검색된 행의 수를 알려 줍니다.  불완전한 행 집합이 페치되는 경우를 제외하면 대부분의 경우 행 집합 크기와 같습니다.|  
|[GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|행 집합 내의 특정 행에 대한 페치 상태를 반환합니다.|  
|[RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|행 집합 내 특정 행의 데이터 및 상태를 새로 고칩니다.|  
|[SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|커서를 행 집합 내의 특정 행으로 이동합니다.|  
|[SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|행 집합 크기 설정을 지정된 값으로 변경하는 가상 함수입니다.|  
  
##  <a name="_core_special_considerations"></a> 유의 사항  
 대량 행 페치를 이용하면 성능이 향상되지만 일부 기능은 다르게 작동합니다.  대량 행 페치를 구현하기 전에 다음을 고려하십시오.  
  
-   프레임워크에서는 자동으로 `DoBulkFieldExchange` 멤버 함수를 호출하여 데이터를 데이터 소스에서 레코드 집합 개체로 전송합니다.  그러나 이와는 반대로 레코드 집합에서 데이터 소스로 데이터가 전송되지는 않습니다.  `AddNew`, **Edit**, **Delete** 또는 **Update** 멤버 함수를 호출하면 어설션이 실패하게 됩니다.  `CRecordset` 클래스는 현재 데이터의 대량 행 업데이트 메커니즘을 제공하지 않지만 ODBC API 함수인 **SQLSetPos**를 사용하여 직접 함수를 작성할 수 있습니다.  **SQLSetPos**에 대한 자세한 내용은 MSDN 설명서의 ODBC SDK 프로그래머 참조를 참조하십시오.  
  
-   `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty` 및 `SetFieldNull` 멤버 함수는 대량 행 페치를 구현하는 레코드 집합에 사용할 수 없습니다.  그러나 `IsDeleted` 대신 `GetRowStatus`를, `IsFieldNullable`대신 `GetODBCFieldInfo`를 호출할 수 있습니다.  
  
-   **Move** 작업을 수행하면 레코드 집합의 위치가 행 집합만큼씩 변경됩니다.  예를 들어 초기 행 집합 크기가 10이고 100개의 레코드가 있는 레코드 집합을 여는 경우  **Open**을 호출하면 1행에서 10행까지 페치되고 현재 레코드는 1행이 됩니다.  `MoveNext`를 호출하면 다음 행이 아니라 다음 행 집합을 페치합니다.  이 행 집합은 11행에서 20행까지로 구성되며 현재 레코드는 11행이 됩니다.  대량 행 페치를 구현하는 경우 `MoveNext`와 **Move\( 1 \)**는 서로 다르게 동작합니다.  **Move\(1\)**은 현재 레코드에서 1행부터 시작하는 행 집합을 페치합니다.  이 예제에서 **Open**을 호출한 다음 **Move\( 1 \)**를 호출하면 2행에서 11행까지의 행으로 구성된 행 집합이 페치되고 현재 레코드는 2행이 됩니다.  자세한 내용은 [Move](../Topic/CRecordset::Move.md) 멤버 함수를 참조하십시오.  
  
-   마법사는 레코드 필드 교환과 달리 대량 레코드 필드 교환을 지원하지 않습니다.  따라서 직접 대량 RFX 함수에 대한 호출을 작성하여 `DoBulkFieldExchange`를 재정의하고 사용자가 직접 필드 데이터 멤버를 선언해야 합니다.  자세한 내용은 클래스 라이브러리 참조의 [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md) 항목을 참조하십시오.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> 대량 레코드 필드 교환 구현 방법  
 대량 레코드 필드 교환은 데이터 소스에서 레코드 집합 개체로 데이터의 행 집합을 전송합니다.  대량 RFX 함수는 이 데이터를 배열에 저장할 뿐 아니라 행 집합의 각 데이터 항목 길이도 배열에 저장합니다.  데이터 배열에 액세스하려면 클래스 정의에서 필드 데이터 멤버를 포인터로 정의해야 합니다.  또한 길이 배열에 액세스하기 위한 포인터 집합을 정의해야 합니다.  매개 변수 데이터 멤버를 포인터로 선언하면 안 됩니다. 대량 레코드 필드 교환을 사용할 때 매개 변수 데이터 멤버를 선언하는 방식은 일반적인 레코드 필드 교환의 경우와 같습니다.  다음 코드는 간단한 예제를 보여 줍니다.  
  
```  
class MultiRowSet : public CRecordset  
{  
public:  
   // Field/Param Data  
      // field data members  
      long* m_rgID;  
      LPSTR m_rgName;  
  
      // pointers for the lengths  
      // of the field data  
      long* m_rgIDLengths;  
      long* m_rgNameLengths;  
  
      // input parameter data member  
      CString m_strNameParam;  
  
   .  
   .  
   .  
}  
```  
  
 이 저장 버퍼를 사용자가 직접 할당할 수도 있고 프레임워크에서 자동으로 할당되도록 할 수도 있습니다.  버퍼를 직접 할당하려면 **Open** 멤버 함수에서 **dwOptions** 매개 변수의 **CRecordset::userAllocMultiRowBuffers** 옵션을 지정해야 합니다.  또한 배열의 크기는 적어도 행 집합 크기와 같도록 설정해야 합니다.  프레임워크에서 자동으로 할당되도록 하려면 포인터를 **NULL**로 초기화해야 합니다. 이러한 작업은 대개 레코드 집합 개체의 생성자에서 수행됩니다.  
  
```  
MultiRowSet::MultiRowSet( CDatabase* pDB )  
   : CRecordset( pDB )  
{  
   m_rgID = NULL;  
   m_rgName = NULL;  
   m_rgIDLengths = NULL;  
   m_rgNameLengths = NULL;  
   m_strNameParam = "";  
  
   m_nFields = 2;  
   m_nParams = 1;  
  
   .  
   .  
   .  
}  
```  
  
 마지막으로 `DoBulkFieldExchange` 멤버 함수를 재정의해야 합니다.  필드 데이터 멤버에 대해서는 대량 RFX 함수를 호출하고 매개 변수 데이터 멤버에 대해서는 RFX 함수를 호출합니다.  SQL 문이나 저장 프로시저를 **Open**에 전달하여 레코드 집합을 연 경우 대량 RFX 호출 순서는 레코드 집합에 있는 열의 순서와 일치해야 합니다. 마찬가지로 매개 변수에 대한 RFX 호출 순서는 SQL 문이나 저장 프로시저의 매개 변수 순서와 일치해야 합니다.  
  
```  
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )  
{  
   // call the Bulk RFX functions  
   // for field data members  
   pFX->SetFieldType( CFieldExchange::outputColumn );  
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),  
                  &m_rgID, &m_rgIDLengths );  
   RFX_Text_Bulk( pFX, _T( "[colName]" ),  
                  &m_rgName, &m_rgNameLengths, 30 );  
  
   // call the RFX functions for  
   // for parameter data members  
   pFX->SetFieldType( CFieldExchange::inputParam );  
   RFX_Text( pFX, "NameParam", m_strNameParam );  
}  
```  
  
> [!NOTE]
>  파생 `CRecordset` 클래스가 범위를 벗어나기 전에 **Close** 멤버 함수를 호출해야 합니다.  그러면 프레임워크에서 할당한 메모리가 모두 해제됩니다.  대량 행 페치를 구현했는지에 관계없이 항상 명시적으로 **Close**를 호출하는 것이 좋습니다.  
  
 RFX\(레코드 필드 교환\)에 대한 자세한 내용은 [레코드 필드 교환: RFX 작동 방식](../../data/odbc/record-field-exchange-how-rfx-works.md)을 참조하십시오.  매개 변수 사용에 대한 자세한 내용은 [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) 및 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)   
 [CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)