---
title: "데이터 페치 | Microsoft Docs"
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
  - "데이터[C++], 페칭"
  - "페칭"
  - "OLE DB 소비자 템플릿[C++], 데이터 페칭(fetching)"
  - "행 집합[C++], 페칭"
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 데이터 페치
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 소스, 세션 및 행 집합 개체를 연 후에는 데이터를 페치할 수 있습니다.  사용하는 접근자의 형식에 따라 열을 바인딩해야 하는 경우도 있습니다.  
  
### 데이터를 페치하려면  
  
1.  알맞은 **Open** 명령을 사용하여 행 집합을 엽니다.  
  
2.  `CManualAccessor`를 사용하고 있으면, 아직 출력 열을 바인딩하지 않은 경우 출력 열을 바인딩합니다.  열을 바인딩하려면 다음 예제와 같이 `GetColumnInfo`를 호출한 다음 바인딩을 가진 접근자를 만듭니다.  
  
    ```  
    // From the DBViewer Sample CDBTreeView::OnQueryEdit  
    // Get the column information  
    ULONG ulColumns       = 0;  
    DBCOLUMNINFO* pColumnInfo  = NULL;  
    LPOLESTR pStrings      = NULL;  
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)  
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);  
    struct MYBIND* pBind = new MYBIND[ulColumns];  
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);  
    for (ULONG l=0; l<ulColumns; l++)  
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);  
    rs.Bind();  
    ```  
  
3.  `while` 루프를 작성하여 데이터를 검색합니다.  다음 예제에서처럼 루프에서 `MoveNext`를 호출하여 커서를 다음으로 이동하고 S\_OK에 대한 반환 값을 검사합니다.  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  `while` 루프 내에서 접근자 형식에 따라 데이터를 페치할 수 있습니다.  
  
    -   [CAccessor](../../data/oledb/caccessor-class.md) 클래스를 사용하는 경우, 데이터 멤버가 들어 있는 사용자 레코드가 있어야 합니다.  다음 예제와 같이 이들 데이터 멤버를 사용하여 데이터에 액세스할 수 있습니다.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   `CDynamicAccessor` 또는 `CDynamicParameterAccessor` 클래스를 사용하는 경우, 다음 예제에서처럼 `GetValue` 및 `GetColumn` 액세스 함수를 사용하여 데이터를 페치할 수 있습니다.  사용하고 있는 데이터 형식을 확인하려는 경우에는 `GetType`을 사용하십시오.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the dynamic accessor functions to retrieve your data.  
  
            ULONG ulColumns = rs.GetColumnCount();  
            for (ULONG i=0; i<ulColumns; i++)  
            {  
                rs.GetValue(i);  
            }  
        }  
        ```  
  
    -   `CManualAccessor`를 사용하는 경우 다음 예제와 같이 사용자 고유의 데이터 멤버를 지정하여 바인딩한 후 직접 액세스해야 합니다.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## 참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)