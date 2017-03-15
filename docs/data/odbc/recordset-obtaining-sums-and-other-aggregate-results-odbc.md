---
title: "레코드 집합: 합계 및 다른 집계 결과 구하기(ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC 레코드 집합, SQL 집계 값 검색"
  - "레코드 집합, SQL 집계 값 검색"
  - "레코드 집합에서 SQL 집계 값 검색"
  - "SQL 집계 값"
  - "SQL 집계 값, 레코드 집합에서 검색"
  - "SQL Server 프로젝트, 레코드 집합에서 집계 값 검색"
  - "SQL, 레코드 집합에서 집계 값 검색"
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 레코드 집합: 합계 및 다른 집계 결과 구하기(ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목은 MFC ODBC 클래스에 적용됩니다.  
  
 이 항목에서는 다음과 같은 [SQL](../../data/odbc/sql.md) 키워드를 사용하여 집계 결과를 얻는 방법에 대해 설명합니다.  
  
-   **SUM** 숫자 데이터 형식의 열에서 값의 합계를 계산합니다.  
  
-   **MIN** 숫자 데이터 형식의 열에서 가장 작은 값을 추출합니다.  
  
-   **MAX** 숫자 데이터 형식의 열에서 가장 큰 값을 추출합니다.  
  
-   **AVG** 숫자 데이터 형식의 열에서 모든 값의 평균을 계산합니다.  
  
-   **COUNT** 모든 데이터 형식의 열에서 레코드 수를 계산합니다.  
  
 이러한 SQL 함수는 데이터 소스에서 레코드를 추출하기 위한 것이 아니라 데이터 소스의 레코드에 대한 통계 정보를 구하는 데 사용됩니다.  모든 열이 집계인 경우 이러한 함수의 결과로 생성되는 레코드 집합은 대개 레코드 하나에 모든 값이 저장됩니다. 그러나 **GROUP BY** 절을 사용한 경우에는 두 개 이상의 레코드가 포함될 수도 있습니다. 이 값은 계산 결과이거나 SQL 함수에 의해 추출된 것입니다.  
  
> [!TIP]
>  SQL **GROUP BY** 절과 가능한 경우 **HAVING** 절을 함께 SQL 문에 추가하려면 **m\_strFilter**의 끝에 절을 추가합니다.  예를 들면 다음과 같습니다.  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 이렇게 하면 열을 필터링하거나 정렬하여 집계 결과를 구하는데 사용하는 레코드 수를 제한할 수 있습니다.  
  
> [!CAUTION]
>  일부 집계 연산자는 집계하고 있는 열과 다른 데이터 형식을 반환합니다.  
  
-   **SUM**과 **AVG**는 한 수준 위의 큰 데이터 형식을 반환할 수도 있습니다. 예를 들어, `int` 형식을 대상으로 이러한 함수를 호출하면 **LONG**이나 **double** 형식이 반환됩니다.  
  
-   **COUNT**는 대개 대상 열의 형식에 관계없이 **LONG**을 반환합니다.  
  
-   **MAX**와 **MIN**은 계산하는 열과 동일한 데이터 형식을 반환합니다.  
  
     예를 들어, **클래스 추가** 마법사에서 Sales 열에 사용할 `long` `m_lSales`를 만든 경우 집계 결과를 저장하려면 이를 `double m_dblSumSales` 데이터 멤버로 대체해야 합니다.  다음 예제를 참조하십시오.  
  
#### 레코드 집합의 집계 결과를 구하려면  
  
1.  [MFC ODBC 소비자 추가](../../mfc/reference/adding-an-mfc-odbc-consumer.md)에 설명된 방법에 따라 집계 결과를 구할 열이 포함된 레코드 집합을 만듭니다.  
  
2.  레코드 집합의 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) 함수를 수정합니다.  열 이름을 나타내는 문자열\([RFX](../../data/odbc/record-field-exchange-using-rfx.md) 함수 호출의 둘째 인수\)을 열의 집계 함수를 나타내는 문자열로 바꿉니다.  예를 들면 다음과 같은 문자열이 있습니다.  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     이 문자열을 아래와 같이 바꿉니다.  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  레코드 집합을 엽니다.  집계 연산의 결과는 `m_dblSumSales`에 남습니다.  
  
> [!NOTE]
>  실제로 마법사는 헝가리언 접두사 없이 데이터 멤버 이름을 할당합니다.  예를 들어, 마법사에서는 Sales 열에 대해 이전 예제에서 본 `m_lSales` 대신 `m_Sales`를 만듭니다.  
  
 데이터를 보기 위해 [CRecordView](../../mfc/reference/crecordview-class.md) 클래스를 사용하는 경우 새 데이터 멤버 값을 표시하려면 DDX 함수 호출을 변경해야 합니다. 이 예에서는 다음 코드를  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 받는 사람:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## 참고 항목  
 [레코드 집합\(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [레코드 집합: 레코드 집합의 레코드 선택 방법\(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)