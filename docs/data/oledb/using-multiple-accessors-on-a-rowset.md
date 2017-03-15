---
title: "행 집합에서 여러 접근자 사용 | Microsoft Docs"
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
  - "접근자[C++], 행 집합"
  - "BEGIN_ACCESSOR 매크로"
  - "BEGIN_ACCESSOR 매크로, 여러 접근자"
  - "행 집합[C++], 여러 접근자"
ms.assetid: 80d4dc5d-4940-4a28-a4ee-d8602f71d2a6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 행 집합에서 여러 접근자 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

여러 접근자를 사용해야 하는 세 가지 기본 시나리오가 있습니다.  
  
-   **여러 행 집합 읽기\/쓰기** 이 시나리오에서는 기본 키가 있는 테이블이 있습니다.  기본 키를 포함해서 행의 모든 열을 읽으려고 합니다.  또한 기본 키를 제외한\(기본 키 열에는 쓸 수 없음\) 모든 열에 데이터를 쓰려고 합니다.  이 경우 두 개의 접근자를 설정합니다.  
  
    -   접근자 0은 모든 열을 포함합니다.  
  
    -   접근자 1은 기본 키를 제외한 모든 열을 포함합니다.  
  
-   **성능.** 이 시나리오에서는 하나 이상의 열이 그래픽, 소리 또는 비디오 파일 등의 대용량 데이터를 포함합니다.  행으로 이동할 때마다 대용량 데이터 파일이 포함된 열은 검색하지 않으려고 합니다. 대용량 데이터 열을 검색하면 응용 프로그램 성능이 떨어지기 때문입니다.  
  
     별도의 접근자를 설정하여, 이 접근자 중 첫 접근자가 대용량 데이터가 포함된 열을 제외한 모든 열을 포함하며 자동으로 이러한 열에서 데이터를 검색하도록 할 수 있습니다. 이 접근자가 자동 접근자입니다.  두 번째 접근자는 대용량 데이터가 포함된 열만 검색하지만 자동으로 이 열에서 데이터를 검색하지는 않습니다.  요구가 있을 경우 다른 메서드에서 대용량 데이터를 업데이트하거나 페치합니다.  
  
    -   접근자 0은 자동 접근자이며, 대용량 데이터가 포함된 열을 제외한 모든 열을 검색합니다.  
  
    -   접근자 1은 자동 접근자가 아니며, 대용량 데이터가 포함된 열을 검색합니다 .  
  
     auto 인수를 사용하여 접근자가 자동 접근자인지 아닌지 지정합니다.  
  
-   **여러 ISequentialStream 열** 이 시나리오에서는 `ISequentialStream` 데이터를 포함한 열이 두 개 이상 있습니다.  그러나 각 접근자는 하나의 `ISequentialStream` 데이터 스트림에만 제한됩니다.  이 문제를 해결하기 위해 각각 `ISequentialStream` 포인터를 포함하는 여러 접근자를 설정합니다.  
  
 일반적으로 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) 및 [END\_ACCESSOR](../../data/oledb/end-accessor.md) 매크로를 사용하여 접근자를 만듭니다.  또한 [db\_accessor](../../windows/db-accessor.md) 특성을 사용할 수도 있습니다. 접근자에 대해서는 [사용자 레코드](../../data/oledb/user-records.md).에서 더 자세히 설명합니다. 매크로나 특성은 접근자가 자동 접근자인지 아닌지 지정합니다.  
  
-   자동 접근자에서는 **MoveFirst**, `MoveLast`, `MoveNext`, `MovePrev` 등의 move 메서드를 사용하여 지정된 모든 열에 대해 데이터를 자동으로 검색합니다.  접근자 0은 자동 접근자여야 합니다.  
  
-   자동 접근자가 아닌 경우에는 **Update**, **Insert**, **Fetch**, **Delete** 등의 메서드를 명시적으로 호출한 후에 검색이 이루어집니다.  위에 설명한 시나리오들의 경우 이동할 때마다 모든 열을 검색하고 싶지는 않을 것입니다.  아래와 같이, 별도의 접근자에 하나 이상의 열을 삽입하여 이 접근자를 자동 접근자가 아닌 접근자로 만듭니다.  
  
 다음 예제에서는 여러 접근자를 사용하여 SQL 서버 pubs 데이터베이스의 jobs 테이블을 읽고 씁니다.  일반적으로 이런 식으로 여러 접근자를 사용합니다. 위의 "여러 행 집합 읽기\/쓰기"를 참조하십시오.  
  
 사용자 레코드 클래스는 다음과 같습니다.  두 개의 접근자가 설정됩니다. 접근자 0은 기본 키 열, ID만을 포함하며 접근자 1은 다른 열들을 포함합니다.  
  
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
  
 main 코드는 다음과 같습니다.  `MoveNext`를 호출하면 접근자 0을 사용하여 기본 키 열 ID에서 자동으로 데이터를 검색합니다.  끝 부분의 **Insert** 메서드는 기본 키 열에 쓰지 않기 위해 접근자 1을 사용합니다.  
  
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
            CTable<CAccessor<CJobs> > jobs;  
  
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
  
## 참고 항목  
 [접근자 사용](../../data/oledb/using-accessors.md)   
 [사용자 레코드](../../data/oledb/user-records.md)