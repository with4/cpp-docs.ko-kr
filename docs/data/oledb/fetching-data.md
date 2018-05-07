---
title: 데이터 페치 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data [C++], fetching
- rowsets [C++], fetching
- fetching
- OLE DB consumer templates [C++], fetching data
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab03da7c303552a715c6766af7829e74025866ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fetching-data"></a>데이터 페치
데이터 원본, 세션 및 행 집합 개체를 연 후에 데이터를 인출할 수 있습니다. 사용 하는 접근자의 형식에 따라 열을 바인딩할 할 수 있습니다.  
  
### <a name="to-fetch-data"></a>데이터를 인출  
  
1.  적절 한 사용 하 여 행 집합을 열고 **열려** 명령입니다.  
  
2.  사용 중인 경우 `CManualAccessor`을 아직 수행 하지 않은 경우 출력 열을 바인딩합니다. 열을 바인딩하려면 호출 `GetColumnInfo`, 다음 예제에 나와 있는 것 처럼 접근자에 바인딩을 만듭니다.  
  
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
  
3.  작성 한 `while` 루프 데이터를 검색 합니다. 루프에 호출 `MoveNext` 커서를 이동 하 고 다음 예제와 같이 S_OK에 대 한 반환 값을 검사 하려면:  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  내에서 `while` 루프 접근자 형식에 따라 데이터를 인출할 수 있습니다.  
  
    -   사용 하는 경우는 [CAccessor](../../data/oledb/caccessor-class.md) 클래스 데이터 멤버를 포함 하는 사용자 레코드가 있어야 합니다. 다음 예제에 나와 있는 것 처럼 이들 데이터 멤버를 사용 하 여 데이터를 액세스할 수 있습니다.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   사용 하는 경우는 `CDynamicAccessor` 또는 `CDynamicParameterAccessor` 클래스 액세스 함수를 사용 하 여 데이터를 인출할 수 `GetValue` 및 `GetColumn`다음 예제에 나온 것 처럼 합니다. 사용 하는, 사용 하 여 데이터의 형식을 결정 하려면 `GetType`합니다.  
  
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
  
    -   사용 하는 경우 `CManualAccessor`, 사용자 고유의 데이터 멤버를 지정, 직접, 바인딩 및 예제에 나와 있는 것 처럼, 직접 액세스 해야 합니다.  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿 작업](../../data/oledb/working-with-ole-db-consumer-templates.md)