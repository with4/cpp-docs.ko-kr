---
title: "레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언(ODBC) | Microsoft Docs"
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
  - "ODBC 레코드 집합, 쿼리"
  - "미리 정의된 쿼리 및 레코드 집합"
  - "레코드 집합, 미리 정의된 쿼리"
  - "레코드 집합, 저장 프로시저"
  - "저장 프로시저, 레코드 집합"
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 레코드 집합: 미리 정의된 쿼리에 대한 클래스 선언(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 미리 정의된 쿼리에서 사용할 레코드 집합 클래스를 만드는 방법에 대해 설명합니다. 미리 정의된 쿼리를 Microsoft SQL Server 등 일부에서는 저장 프로시저라고도 합니다.  
  
> [!NOTE]
>  이 항목은 대량 행 페치가 구현되지 않은 `CRecordset`에서 파생된 개체에 적용됩니다.  대량 행 페치가 구현되어 있는 경우에도 프로세스는 유사합니다.  대량 행 페치를 구현하는 레코드 집합과 그렇지 않은 레코드 집합의 자세한 차이점은 [레코드 집합: 대량 레코드 페치\(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)를 참조하십시오.  
  
 일부 DBMS\(데이터베이스 관리 시스템\)에서는 미리 정의된 쿼리를 만들어 함수처럼 프로그램에서 호출할 수 있습니다.  쿼리에는 이름이 있고, 매개 변수를 사용하거나 레코드를 반환할 수 있습니다.  이 항목의 절차에서는 레코드를 반환하고 매개 변수를 받기도 하는 미리 정의된 쿼리를 호출하는 방법에 대해 설명합니다.  
  
 데이터베이스 클래스에서는 미리 정의된 쿼리를 업데이트하는 기능을 지원하지 않습니다.  스냅숏의 미리 정의된 쿼리와 다이너셋의 미리 정의된 쿼리 사이의 차이점은 업데이트할 수 있는지의 여부가 아니라 다른 사용자 또는 프로그램의 다른 레코드 집합에 의해 변경된 내용을 레코드 집합에서 볼 수 있는지 여부에 있습니다.  
  
> [!TIP]
>  레코드를 반환하지 않는 미리 정의된 쿼리를 호출하기 위해 레코드 집합은 필요없습니다.  아래에서 설명하는 방법으로 SQL 문을 준비하고 `CDatabase` 멤버 함수 [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)을 호출하여 실행하면 됩니다.  
  
 단일 레코드 집합 클래스를 만들어 미리 정의된 쿼리의 호출을 관리할 수 있지만 일부 작업은 직접 수행해야 합니다.  마법사는 특별히 이러한 목적으로 사용한 클래스를 만드는 기능은 지원하지 않습니다.  
  
#### 미리 정의된 쿼리\(저장 프로시저\)를 호출하기 위한 클래스를 만들려면  
  
1.  **클래스 추가**에서 [MFC ODBC 소비자 마법사](../../mfc/reference/adding-an-mfc-odbc-consumer.md)를 사용하여 쿼리에서 반환되는 대부분의 열을 포함하는 테이블에 사용할 레코드 집합 클래스를 만듭니다.  이렇게 하면 작업을 빠르게 진행할 수 있습니다.  
  
2.  쿼리에서는 반환되지만 마법사에서 자동으로 생성되지 않는 테이블의 모든 열에 대한 필드 데이터 멤버를 사용자가 직접 추가합니다.  
  
     예를 들어 쿼리가 두 개의 추가 테이블 각각에서 세 개의 열을 반환하면 적절한 데이터 형식을 사용하여 여섯 개의 필드 데이터 멤버를 클래스에 추가합니다.  
  
3.  추가한 각 필드 데이터 멤버의 데이터 형식에 해당하는 [RFX](../../data/odbc/record-field-exchange-rfx.md) 함수 호출을 클래스의 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 멤버 함수에 사용자가 직접 추가합니다.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  결과 집합에 반환되는 열의 데이터 형식과 순서를 알아야 합니다.  `DoFieldExchange`에서 RFX 함수 호출 순서는 결과 집합 열의 순서와 일치해야 합니다.  
  
4.  레코드 집합 클래스 생성자에서 새 필드 데이터 멤버를 사용자가 직접 추가적으로 초기화합니다.  
  
     또한 [m\_nFields](../Topic/CRecordset::m_nFields.md) 데이터 멤버에 대한 초기화 값을 증가시켜야 합니다.  마법사에서 초기화 코드를 작성하지만 그 초기화는 마법사에서 자동으로 추가한 필드 데이터 멤버에만 적용됩니다.  예를 들면 다음과 같습니다.  
  
    ```  
    m_nFields += 6;  
    ```  
  
     `CLongBinary`나 바이트 배열 같은 일부 데이터 형식은 여기에서 초기화되지 않습니다.  
  
5.  쿼리에 매개 변수가 전달되는 경우 각 매개 변수에 대한 매개 변수 데이터 멤버, RFX 함수 호출 및 초기화를 추가합니다.  
  
6.  이 절차의 4단계에서 추가된 필드에 대해 `m_nFields`를 증가시킨 것처럼 추가된 각 매개 변수에 대해 `m_nParams`를 증가시켜야 합니다.  자세한 내용은 [레코드 집합: 레코드 집합 매개 변수화\(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)를 참조하십시오.  
  
7.  다음과 같은 형식으로 SQL 문 문자열을 사용자가 직접 작성합니다.  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     여기서 **CALL**은 ODBC 키워드이고 **proc\-name**은 데이터 소스에 대한 쿼리 이름이며 "?" 항목은 런타임에 레코드 집합에 제공되는 매개 변수 값\(있을 경우\)에 대한 자리 표시자입니다.  다음 예제는 매개 변수 하나에 대한 자리 표시자를 준비합니다.  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  레코드 집합을 여는 코드에서 먼저 레코드 집합의 매개 변수 데이터 멤버 값을 설정한 다음 **lpszSQL** 매개 변수를 위한 SQL 문자열을 전달하여 **Open** 멤버 함수를 호출합니다.  또는 클래스에서 `GetDefaultSQL` 멤버 함수가 반환하는 문자열을 대체합니다.  
  
 다음 예제에서는 `Delinquent_Accts`라는 미리 정의된 쿼리를 호출하는 절차에 대해 설명합니다. 이 쿼리는 판매 구역 번호를 나타내는 매개 변수 하나를 받은 후  `Acct_No`, `L_Name`, `Phone`의 세 개 열을 반환합니다.  이 경우 모든 열은 Customers 테이블에 있습니다.  
  
 다음 레코드 집합은 쿼리에서 반환하는 열에 대한 필드 데이터 멤버 및 런타임에 요청하는 판매 구역 번호에 대한 매개 변수를 지정합니다.  
  
```  
class CDelinquents : public CRecordset  
{  
// Field/Param Data  
    LONG m_lAcct_No;  
    CString m_strL_Name;  
    CString m_strPhone;  
    LONG m_lDistParam;  
    // ...  
};  
```  
  
 이 클래스 선언은 `m_lDistParam` 멤버를 수동으로 추가한 점을 제외하면 마법사에서 작성한 그대로입니다.  다른 멤버는 여기에 표시하지 않았습니다.  
  
 다음 예제에서는 `CDelinquents` 생성자에서 데이터 멤버에 대한 초기화를 보여 줍니다.  
  
```  
CDelinquents::CDelinquents(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
    // Wizard-generated params:  
    m_lAcct_No = 0;  
    m_strL_Name = "";  
    m_strPhone = "";  
    m_nFields = 3;  
    // User-defined params:  
    m_nParams = 1;  
    m_lDistParam = 0;  
}  
```  
  
 [m\_nFields](../Topic/CRecordset::m_nFields.md) 및 [m\_nParams](../Topic/CRecordset::m_nParams.md)에 대한 초기화에 유의하십시오.  `m_nFields`는 마법사에서 초기화하고 `m_nParams`는 프로그래머가 직접 초기화합니다.  
  
 다음 예제는 `CDelinquents::DoFieldExchange`의 RFX 함수를 보여 줍니다.  
  
```  
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Long(pFX, "Acct_No", m_lAcct_No);  
    RFX_Text(pFX, "L_Name", m_strL_Name);  
    RFX_Text(pFX, "Phone", m_strPhone);  
    pFX->SetFieldType(CFieldExchange::param);  
    RFX_Long(pFX, "Dist_No", m_lDistParam);  
}  
```  
  
 반환되는 세 열에 대한 RFX 호출 외에 이 코드는 런타임에 전달하는 매개 변수의 바인딩을 관리합니다.  매개 변수는 `Dist_No`\(구역 번호\) 열에 입력됩니다.  
  
 다음 예제에서는 SQL 문자열을 설정하는 방법과 그 문자열을 사용하여 레코드 집합을 여는 방법을 보여 줍니다.  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 이 코드에서는 스냅숏을 생성하고 이전에 사용자가 입력한 매개 변수를 스냅숏에 전달하여 미리 정의된 쿼리를 호출합니다.  쿼리를 실행하면 지정된 판매 구역에 대한 레코드가 반환됩니다.  각 레코드에는 계정 번호, 고객의 성, 고객 전화 번호가 저장된 열이 있습니다.  
  
> [!TIP]
>  반환 값\(출력 매개 변수\)을 저장 프로시저에서 처리할 수도 있습니다.  자세한 내용 및 예제는 [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)을 참조하십시오.  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합 다시 쿼리\(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [레코드 집합: 테이블에 대한 클래스 선언\(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [레코드 집합: 조인 수행\(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)