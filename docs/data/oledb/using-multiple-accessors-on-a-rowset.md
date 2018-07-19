---
title: 행 집합에서 여러 접근자 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR macro, multiple accessors
- rowsets [C++], multiple accessors
- accessors [C++], rowsets
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a30108ec344091631094cd55f6a3bd3f0f4a4a54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111317"
---
# <a name="using-multiple-accessors-on-a-rowset"></a>행 집합에서 여러 접근자 사용
여러 접근자를 사용 해야 하는 세 가지 기본 시나리오에는  
  
-   **여러 읽기/쓰기 행 집합입니다.** 이 시나리오에서는 기본 키가 있는 테이블이 있을 수 있습니다. 기본 키를 포함 하 여 행의 모든 열을 읽을 수 있도록 하려고 합니다. 또한 수 (기본 키 열에 쓸 수 없습니다) 때문에 기본 키를 제외한 모든 열에 데이터를 쓸 수 합니다. 이 경우 두 명의 접근자를 설정할 수도 있습니다.  
  
    -   모든 열을 포함 하는 접근자 0입니다.  
  
    -   접근자 1 기본 키를 제외한 모든 열을 포함 합니다.  
  
-   **성능.** 이 시나리오에서는 하나 이상의 열 많은 양의 데이터를 예를 들어, 그래픽, 사운드 또는 비디오 파일을 포함 합니다. 행으로 이동할 때마다 아마도 원하지 않는 대용량 데이터 파일에 열을 검색 하 이렇게 하면 지금는 응용 프로그램의 성능이 저하 되므로 합니다.  
  
     첫 번째 접근자 대규모 데이터를 제외한 모든 열을 포함 하 고 자동으로 이러한 열에서 데이터를 검색 하는 별도 접근자를 설정할 수 있습니다. 자동 접근자입니다. 두 번째 접근자 대용량 데이터가 포함 된 열만을 검색 하지만 검색 하지는 않습니다 데이터가이 열에서 자동으로 합니다. 업데이트 하거나 필요에 따라 대형 데이터를 인출 합니다. 다른 메서드를 사용할 수 있습니다.  
  
    -   접근자 0은 자동 접근자; 대규모 데이터를 제외한 모든 열을 검색 합니다.  
  
    -   접근자 1 자동 접근자; 아닙니다. 열에 큰 데이터를 검색합니다.  
  
     Auto 인수를 사용 하 여 접근자 자동 접근자가 있는지 여부를 지정 합니다.  
  
-   **여러 ISequentialStream 열입니다.** 이 시나리오에서는 포함 한 개 이상의 열이 있는 `ISequentialStream` 데이터입니다. 그러나 각 접근자는 1 개로 제한 `ISequentialStream` 데이터 스트림을 합니다. 이 문제를 해결 하기 위해 설정 여러 접근자를 각각 하나 포함 된 `ISequentialStream` 포인터입니다.  
  
 일반적으로 사용 하 여 접근자를 만들기는 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) 및 [END_ACCESSOR](../../data/oledb/end-accessor.md) 매크로입니다. 사용할 수도 있습니다는 [db_accessor](../../windows/db-accessor.md) 특성입니다. (접근자는에서 더 자세히 설명 [사용자 레코드](../../data/oledb/user-records.md).) 매크로 또는 특성 접근자는 자동 또는 자동이 아닌 접근자 있는지 여부를 지정 합니다.  
  
-   자동 접근자 메서드를 같은 이동 **MoveFirst**, `MoveLast`, `MoveNext`, 및 `MovePrev` 모든 열을 자동으로 지정에 대 한 데이터를 검색 합니다. 접근자 0은 자동 접근자 여야 합니다.  
  
-   자동이 아닌 접근자를 검색 하는 작업 발생 하지 않습니다 명시적으로 호출한 메서드 등 **업데이트**, **삽입**, **인출**, 또는 **삭제**. 위에서 설명한 시나리오에서는 있습니다 하지 않을 이동할 때마다에 있는 모든 열을 검색 합니다. 하나 이상의 열을 별도 접근자에 배치할 수 있으며 다음 사항을 자동이 아닌 접근자를 아래와 같이 수 있습니다.  
  
 다음 예에서는 읽기 및 쓰기의 여러 접근자를 사용 하 여 SQL Server pubs 데이터베이스 작업 테이블에 여러 접근자를 사용 합니다. 이것은 여러 접근자;의 가장 일반적인 용도 위를 "여러 읽기/쓰기 행 집합"를 참조 하십시오.  
  
 사용자 레코드 클래스는 다음과 같습니다. 두 명의 접근자 설정:에 기본 키 열만 (ID)를 포함 하는 접근자 0 및 1 접근자 다른 열을 포함 합니다.  
  
```  
class CJobs  
{  
public:  
    enum {  
        sizeOfDescription = 51  
    };  
  
    short nID;  
    char szDescription[ sizeOfDescription ];  
    short nMinLvl;  
    short nMaxLvl;  
  
    DWORD dwID;  
    DWORD dwDescription;  
    DWORD dwMinLvl;  
    DWORD dwMaxLvl;  
  
BEGIN_ACCESSOR_MAP(CJobs, 2)  
    // Accessor 0 is the automatic accessor  
    BEGIN_ACCESSOR(0, true)  
        COLUMN_ENTRY_STATUS(1, nID, dwID)  
    END_ACCESSOR()  
    // Accessor 1 is the non-automatic accessor  
    BEGIN_ACCESSOR(1, true)  
        COLUMN_ENTRY_STATUS(2, szDescription, dwDescription)  
        COLUMN_ENTRY_STATUS(3, nMinLvl, dwMinLvl)  
        COLUMN_ENTRY_STATUS(4, nMaxLvl, dwMaxLvl)  
    END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 기본 코드는 다음과 같습니다. 호출 `MoveNext` 접근자 0을 사용 하 여 기본 키 열 ID에서 데이터를 자동으로 검색 합니다. 참고 방법을 **삽입** 사용 접근자 1 기본 키 열에 쓰지 않으려면 부분의 메서드.  
  
```  
int main(int argc, char* argv[])  
{  
    // Initalize COM  
    ::CoInitialize(NULL);  
  
    // Create instances of the data source and session  
    CDataSource source;  
    CSession session;  
    HRESULT hr = S_OK;  
  
    // Set initialization properties  
    CDBPropSet dbinit(DBPROPSET_DBINIT);  
    dbinit.AddProperty(DBPROP_AUTH_USERID, OLESTR("my_user_id"));  
    dbinit.AddProperty(DBPROP_INIT_CATALOG, OLESTR("pubs"));  
    dbinit.AddProperty(DBPROP_INIT_DATASOURCE, OLESTR("(local)"));  
  
    hr = source.Open("SQLOLEDB.1", &dbinit);  
    if (hr == S_OK)  
    {  
        hr = session.Open(source);  
        if (hr == S_OK)  
        {  
            // Ready to fetch/access data  
            CTable<CAccessor<CJobs>> jobs;  
  
            // Set properties for making the rowset a read/write cursor  
            CDBPropSet dbRowset(DBPROPSET_ROWSET);  
            dbRowset.AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
            dbRowset.AddProperty(DBPROP_IRowsetChange, true);  
            dbRowset.AddProperty(DBPROP_UPDATABILITY,  
                DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE |  
                DBPROPVAL_UP_DELETE);  
  
            hr = jobs.Open(session, "jobs", &dbRowset);  
            if (hr == S_OK)  
            {  
                // Calling MoveNext automatically retrieves ID  
                // (using accessor 0)  
                while(jobs.MoveNext() == S_OK)  
                   printf_s("Description = %s\n", jobs.szDescription);  
  
                hr = jobs.MoveFirst();  
                if (hr == S_OK)  
                {  
                    jobs.nID = 25;  
                    strcpy_s(&jobs.szDescription[0],  
                             jobs.sizeOfDescription,  
                             "Developer");  
                    jobs.nMinLvl = 10;  
                    jobs.nMaxLvl = 20;  
  
                    jobs.dwDescription = DBSTATUS_S_OK;  
                    jobs.dwID = DBSTATUS_S_OK;  
                    jobs.dwMaxLvl = DBSTATUS_S_OK;  
                    jobs.dwMinLvl = DBSTATUS_S_OK;  
  
                    // Insert method uses accessor 1  
                    // (to avoid writing to the primary key column)  
                    hr = jobs.Insert(1);     
                }  
                jobs.Close();  
            }  
            session.Close();  
        }  
        source.Close();  
    }  
  
    // Uninitialize COM  
    ::CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)   
 [사용자 레코드](../../data/oledb/user-records.md)