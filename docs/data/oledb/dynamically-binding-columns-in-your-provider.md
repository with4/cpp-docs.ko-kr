---
title: "공급자에서 열을 동적으로 바인딩 | Microsoft Docs"
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
  - "열[C++], 동적 열 바인딩"
  - "동적 열 바인딩"
  - "공급자[C++], 동적 열 바인딩"
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자에서 열을 동적으로 바인딩
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

동적 열 바인딩이 실제로 필요한지 확인합니다.  다음과 같은 경우에 동적 열 바인딩이 필요할 수 있습니다.  
  
-   컴파일 타임에 행 집합 열이 정의되지 않은 경우  
  
-   열을 추가하는 책갈피 등의 요소를 지원할 경우  
  
### 동적 열 바인딩을 구현하려면  
  
1.  코드에 **PROVIDER\_COLUMN\_MAP**이 있으면 모두 제거합니다.  
  
2.  사용자 레코드\(사용자 구조\)에서 다음 선언을 추가합니다.  
  
    ```  
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
    ```  
  
3.  `GetColumnInfo` 함수를 구현합니다.  이 함수는 정보 저장 방법을 레이아웃합니다.  이 함수에 대한 속성이나 기타 정보를 가져와야 할 경우도 있습니다.  [COLUMN\_ENTRY](../../data/oledb/column-entry.md)와 비슷한 매크로를 작성하여 사용자 정보를 추가할 수도 있습니다.  
  
     다음 예제는 `GetColumnInfo` 함수를 보여 줍니다.  
  
    ```  
    // Check the property flag for bookmarks, if it is set, set the zero  
    // ordinal entry in the column map with the bookmark information.  
    CAgentRowset* pRowset = (CAgentRowset*) pThis;  
    CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
    CDBPropIDSet set(DBPROPSET_ROWSET);  
    set.AddPropertyID(DBPROP_BOOKMARKS);  
    DBPROPSET* pPropSet = NULL;  
    ULONG ulPropSet = 0;  
    HRESULT hr;  
  
    if (spRowsetProps)  
       hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
    if (pPropSet)  
    {  
       CComVariant var = pPropSet->rgProperties[0].vValue;  
       CoTaskMemFree(pPropSet->rgProperties);  
       CoTaskMemFree(pPropSet);  
  
       if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
       {  
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,   
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)  
          ulCols++;  
       }  
    }  
  
    // Next, set up the other columns.  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szCommand)  
    ulCols++;  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szText)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szCommand2)  
    ulCols++;  
    ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
       GUID_NULL, CAgentMan, szText2)  
    ulCols++;  
  
    if (pcCols != NULL)  
       *pcCols = ulCols;  
  
    return _rgColumns;  
    }  
    ```  
  
## 참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)