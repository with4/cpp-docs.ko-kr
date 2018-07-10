---
title: 업데이트 가능 공급자 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 317ccd043b3a69489f9cbd2737ad7741389863c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098643"
---
# <a name="creating-an-updatable-provider"></a>업데이트 가능 공급자 만들기
Visual c + +에서는 업데이트 가능 공급자 또는 업데이트할 수 있는 공급자에 쓸 데이터 저장소입니다. 이 항목에서는 OLE DB 템플릿을 사용 하 여 업데이트할 수 있는 공급자를 만드는 방법에 설명 합니다.  
  
 이 항목에서는 처리 가능한 여러 공급자와 함께 시작 한다고 가정 합니다. 업데이트 가능 공급자 만들기 두 단계가 있습니다. 공급자는 변경할 방법이 데이터 저장소를 먼저 결정 해야 특히, 변경 내용을 즉시 수행 해야 하는 여부 update 명령이 실행 될 때까지 지연 합니다. 섹션 "[만드는 공급자 업데이트할 수 있는](#vchowmakingprovidersupdatable)" 변경 내용과 공급자 코드에서 작업을 수행 하는 데 필요한 설정을 설명 합니다.  
  
 다음으로 공급자는 소비자가 요청 하는 아무 것도 지원 하기 위해 모든 기능이 포함 되어 있는지 확인 해야 합니다. 소비자가 데이터 저장소를 업데이트 하려는 경우 공급자는 데이터 저장소에 데이터를 유지 하는 코드가 포함 합니다. 예를 들어 데이터 소스에서 이러한 작업을 수행 하는 C 런타임 라이브러리 또는 MFC를 사용할 수 있습니다. 섹션 "[데이터 소스에 기록](#vchowwritingtothedatasource)" 데이터 원본에 기록해을 처리 하는 방법을 설명 **NULL** 기본 값, 및 열 플래그를 설정 합니다.  
  
> [!NOTE]
>  UpdatePV는 업데이트 가능 공급자의 예시입니다. UpdatePV는 MyProv 뿐만 아니라 업데이트할 수 있는 지원을 통해 같습니다.  
  
##  <a name="vchowmakingprovidersupdatable"></a> 업데이트 가능 공급자를 만들기  
 업데이트할 수 있는 공급자를 제공 하기 위해 키 공급자 데이터 저장소 및 원하는 이러한 작업을 수행할 때 공급자에서 수행할 수 있는 작업을 파악 하 고 있습니다. 특히 중요 한 문제는 즉시 또는 지연 업데이트를 데이터 저장소에 요소가 있는지 (일괄 처리) update 명령이 실행 될 때까지 합니다.  
  
 상속 하는 것인지 먼저 결정 해야 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl` 행 집합 클래스에 있습니다. 다음 중 구현 하기로에 따라 세 가지 방법의 기능에 어떤 영향이: `SetData`, **InsertRows**, 및 `DeleteRows`합니다.  
  
-   상속 하는 경우 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md), 데이터 저장소 변경 세 메서드를 즉시 호출 합니다.  
  
-   상속 하는 경우 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md), 메서드를 호출할 때까지 데이터 저장소에 변경 내용을 연기 **업데이트**, `GetOriginalData`, 또는 **실행 취소**합니다. 업데이트에는 여러 변경이 포함 (변경 내용 일괄 처리 작업은 매우 많은 메모리 오버 헤드를 추가할 수 있는지 참고) 일괄 처리 모드로 수행 됩니다.  
  
 `IRowsetUpdateImpl` 에서 파생 `IRowsetChangeImpl`합니다. 따라서 `IRowsetUpdateImpl` 제공 기능 뿐만 아니라 일괄 처리 기능을 변경 합니다.  
  
#### <a name="to-support-updatability-in-your-provider"></a>업데이트를 지원 하려면 공급자에서  
  
1.  행 집합 클래스에서 상속 `IRowsetChangeImpl` 또는 `IRowsetUpdateImpl`합니다. 이러한 클래스는 데이터 저장소를 변경 하는 데 적절 한 인터페이스를 제공 합니다.  
  
     **IRowsetChange 추가**  
  
     추가 `IRowsetChangeImpl` 에이 양식을 사용 하 여 상속 체인에:  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     추가적으로 `COM_INTERFACE_ENTRY(IRowsetChange)` 에 `BEGIN_COM_MAP` 행 집합 클래스에서 섹션.  
  
     **IRowsetUpdate 추가**  
  
     추가 `IRowsetUpdate` 에이 양식을 사용 하 여 상속 체인에:  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  제거 해야는 `IRowsetChangeImpl` 의 상속 체인에 줄을 합니다. 앞에서 언급 한 지시문이 한 가지 예외에 대 한 코드를 포함 해야 `IRowsetChangeImpl`합니다.  
  
2.  다음 COM 맵의을 추가 합니다 (**BEGIN_COM_MAP... END_COM_MAP**):  
  
    |구현 하는 경우|COM 지도에 추가|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  명령에서 다음 속성 집합 구조에 추가 합니다 (**BEGIN_PROPSET_MAP... END_PROPSET_MAP**):  
  
    |구현 하는 경우|속성 집합 구조에 추가|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  속성 집합 맵에 포함 해야 다음 설정을 모두 아래 표시 된 대로:  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     속성 Id와 값을 Atldb.h에 검색 하 여 이러한 매크로 호출에 사용 되는 값을 찾을 수 있습니다 (Atldb.h 온라인 설명서와 다른 경우 Atldb.h 대체 설명서).  
  
    > [!NOTE]
    >  대부분의 **VARIANT_FALSE** 및 `VARIANT_TRUE` 설정이 OLE DB 템플릿에 필요한; OLE DB 사양은 OLE DB 템플릿 하나의 값만 지원할 수 있습니다 하지만 읽기/쓰기 될 수 있습니다.  
  
     **IRowsetChangeImpl를 구현 하는 경우**  
  
     구현 하는 경우 `IRowsetChangeImpl`를 공급자에서 다음 속성을 설정 해야 합니다. 이러한 속성은 주로 통해 인터페이스를 요청 하는 데 사용 됩니다 **icommandproperties:: Setproperties**합니다.  
  
    -   `DBPROP_IRowsetChange`: 설정은 자동으로 **DBPROP_IRowsetChange**합니다.  
  
    -   `DBPROP_UPDATABILITY`지원 되는 방법에 지정 하는 비트 마스크: `IRowsetChange`: `SetData`, `DeleteRows`, 또는 `InsertRow`합니다.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: 소비자를 호출할 수 **irowsetchange:: Deleterows** 또는 `SetData` 새로 삽입된 된 행에 대 한 합니다.  
  
    -   `DBPROP_IMMOBILEROWS`: 행 집합 삽입 되거나 업데이트 된 행 순서를 바꾸지 않습니다.  
  
     **IRowsetUpdateImpl를 구현 하는 경우**  
  
     구현 하는 경우 `IRowsetUpdateImpl`를 설정 해야 다음 속성을 공급자 뿐만 아니라 모든 속성을 설정 하 `IRowsetChangeImpl` 앞에 나열 된:  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    -   `DBPROP_OTHERINSERT`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    -   `DBPROP_REMOVEDELETED`: READ_ONLY 및 VARIANT_TRUE 여야 합니다.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  또한 다른 속성 뿐만; 알림을 지원할 경우 해야했습니다 섹션을 참조 하십시오 `IRowsetNotifyCP` 이 목록에 대 한 합니다.  
  
     예를 들어, 속성 설정 방법의 속성을 설정할 지도 참조 **CUpdateCommand** (에서 Rowset.h)에서 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)합니다.  
  
##  <a name="vchowwritingtothedatasource"></a> 데이터 소스에 기록  
 데이터 소스에서 읽고 호출는 **Execute** 함수입니다. 데이터 원본에 쓰려고 호출에서 `FlushData` 함수입니다. (일반적인 의미에서 플러시 수단을 테이블이 나 인덱스를 디스크에 수정 내용을 저장 합니다.)  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 행 핸들 (*HROW*) 및 접근자 핸들 (*HACCESSOR*) 인수를 사용 하면 작성 하는 영역을 지정할 수 있습니다. 일반적으로 한 번에 단일 데이터 필드를 작성 합니다.  
  
 `FlushData` 메서드는 원래 저장 된 형식에 데이터를 기록 합니다. 이 함수를 재정의 하지 않으면 공급자는 올바르게 작동 하지만 변경 내용을 데이터 저장소에 플러시되지 않습니다.  
  
### <a name="when-to-flush"></a>플러시 하는 경우  
 공급자 템플릿 호출 `FlushData` 데이터 데이터 저장소에 작성 해야 할 때마다, 뿐만 아니라 다음 함수를 호출한 결과로 일반적으로 (항상 그렇지는 않지만) 발생 하는이:  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** (경우에 새 데이터를 행에 삽입할)  
  
-   **IRowsetUpdate::Update**  
  
### <a name="how-it-works"></a>작동 방법  
 소비자가 플러시를 필요로 하는 호출 (예: **업데이트**)이이 호출은 항상 다음을 수행 하는 공급자에 전달 됩니다.  
  
-   호출 `SetDBStatus` 바인딩된 상태 값이 있을 때마다 (참조 *OLE DB 프로그래머 참조*, 6 장 *데이터 부분: 상태*).  
  
-   열 플래그를 확인합니다.  
  
-   `IsUpdateAllowed`.  
  
 이 세 단계 보안을 제공 하는 데 도움이 됩니다. 그런 다음 공급자 호출 `FlushData`합니다.  
  
### <a name="how-to-implement-flushdata"></a>FlushData를 구현 하는 방법  
 구현 하려면 `FlushData`, 몇 가지 문제를 고려해 야 할 필요 합니다.  
  
-   이때 데이터 저장소에 변경 내용을 처리할 수 있도록 해야 합니다.  
  
-   처리 **NULL** 값입니다.  
  
-   기본 값을 처리 합니다.  
  
 자체적으로 구현 하려면 `FlushData` 메서드를 해야 합니다.  
  
-   행 집합 클래스로 이동 합니다.  
  
-   행 집합에서 클래스의 선언을 저장합니다.  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   구현을 제공 `FlushData`합니다.  
  
 제대로 구현 하면 `FlushData` 행과 실제로 업데이트 된 열을 저장 합니다. 사용할 수는 *HROW* 및 *HACCESSOR* 매개 변수를 현재 행 및 최적화를 위해 저장 되는 열을 결정 합니다.  
  
 일반적으로 가장 큰 문제는 사용자의 기본 데이터 저장소로 작업 합니다. 가능 하면 하려고 합니다.  
  
-   가능한 한 단순하게 데이터 저장소에 쓰는 메서드를 유지 합니다.  
  
-   처리 **NULL** 값 (이 권장 되지만 선택 사항).  
  
-   기본값 (이 권장 되지만 선택 사항)를 처리 합니다.  
  
 가장 좋은 방법은 실제 값을 지정에 대 한 데이터 저장소에 **NULL** 값과 기본값입니다. 이 데이터를 추정 하면 것이 좋습니다. 그렇지 않은 것이 좋습니다를 허용 하지 않도록 하는 경우 **NULL** 값과 기본값입니다.  
  
 다음 예제와 방법을 `FlushData` 에서 구현 되는 `RUpdateRowset` 클래스에 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플 (샘플 코드에서 Rowset.h 참조):  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
...  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");  
  
    USES_CONVERSION;  
    enum {  
        sizeOfString = 256,  
        sizeOfFileName = MAX_PATH  
    };  
    FILE*    pFile = NULL;  
    TCHAR    szString[sizeOfString];  
    TCHAR    szFile[sizeOfFileName];  
    errcode  err = 0;  
  
    ObjectLock lock(this);  
  
    // From a filename, passed in as a command text,   
    // scan the file placing data in the data array.  
    if (m_strCommandText == (BSTR)NULL)  
    {  
        ATLTRACE( "RRowsetUpdate::FlushData -- "  
                  "No filename specified\n");  
        return E_FAIL;  
    }  
  
    // Open the file  
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));  
    if ((szFile[0] == _T('\0')) ||   
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))  
    {  
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");  
        return DB_E_NOTABLE;  
    }  
  
    // Iterate through the row data and store it.  
    for (long l=0; l<m_rgRowData.GetSize(); l++)  
    {  
        CAgentMan am = m_rgRowData[l];  
  
        _putw((int)am.dwFixed, pFile);  
  
        if (_tcscmp(&am.szCommand[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
    }  
  
    if (fflush(pFile) == EOF || fclose(pFile) == EOF)  
    {  
        ATLTRACE("RRowsetUpdate::FlushData -- "  
                 "Couldn't flush or close file\n");  
    }  
  
    return S_OK;  
}  
```  
  
### <a name="handling-changes"></a>변경 내용 처리  
 에 대 한 변경 내용을 처리 하 여 공급자를 먼저 데이터 저장소 (예: 텍스트 파일 또는 비디오 파일)에 있도록 수 있는 기능이 있는지 확인 해야 합니다. 표시 되지 않는 공급자 프로젝트에서 해당 코드를 별도로 만들 해야 있습니다.  
  
### <a name="handling-null-data"></a>NULL 데이터를 처리합니다.  
 최종 사용자 송신할 수 **NULL** 데이터입니다. 작성 하는 경우 **NULL** 값을 데이터 원본의 필드에 있는 문제가 발생할 가능성이 있습니다. 도시와 우편 번호;에 대 한 값을 허용 하는 주문 처리 응용 프로그램을 가정해 보세요. 이 경우 배달 불가능 하기 때문에 값 중 하나 또는 모두 있지만 둘 다 하지 수락할 수 있습니다. 따라서 특정 조합 해야 **NULL** 응용 프로그램에 의미 있는 필드의 값입니다.  
  
 공급자 개발자로 서 해당 데이터를 저장 하는 방법, 데이터 저장소에서 데이터를 읽는 방법 및 방법을 지정 하는 사용자에 게 고려해 야 합니다. 데이터 원본의 행 집합 데이터의 상태를 변경 하는 방법을 고려해 야 하는 구체적으로, (예: DataStatus = **NULL**). 소비자 포함 하는 필드에 액세스 하는 경우 반환할 값을 결정 한 **NULL** 값입니다.  
  
 코드는 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플; 공급자를 처리할 수는 어떻게 설명 하는지 **NULL** 데이터. UpdatePV의 원본 제어 공급자 **NULL** 데이터 저장소에 문자열 "NULL"을 작성 하 여 데이터입니다. 읽을 때 **NULL** 데이터에서 데이터 저장소를 하 한 다음 버퍼를 비웁니다 만들기는 **NULL** 문자열입니다. 역시 재정의 `IRowsetImpl::GetDBStatus` 에서 반환 하는 **DBSTATUS_S_ISNULL** 해당 데이터 값이 비어 있습니다.  
  
### <a name="marking-nullable-columns"></a>Null 허용 열을 표시합니다.  
 또한 스키마 행 집합을 구현 하는 경우 (참조 `IDBSchemaRowsetImpl`), 구현에서 지정 해야는 **DBSCHEMA_COLUMNS** 행 집합 (일반적으로 표시 하 여 공급자에 **C***xxx*** SchemaColSchemaRowset**) 열이 null을 허용 합니다.  
  
 모든 null 허용 열이 포함 되도록 지정할 해야는 **DBCOLUMNFLAGS_ISNULLABLE** 값의 버전에는 `GetColumnInfo`합니다.  
  
 OLE DB 템플릿 구현을 열 null 허용으로 표시 하지 않으면 공급자 가정 값을 포함 해야 하 고 소비자 null 값을 보낼 수 없습니다.  
  
 다음 예제와 방법을 **CommonGetColInfo** 에서 함수를 구현 하는 **CUpdateCommand** (UpProvRS.cpp 참조) UpdatePV에 있습니다. 열이 있는 어떻게 **DBCOLUMNFLAGS_ISNULLABLE** null 허용 열에 대 한 합니다.  
  
```cpp
/////////////////////////////////////////////////////////////////////////////  
// CUpdateCommand (in UpProvRS.cpp)  
  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)  
{  
    static ATLCOLUMNINFO _rgColumns[6];  
    ULONG ulCols = 0;  
  
    if (bBookmark)  
    {  
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,  
                            sizeof(DWORD), DBTYPE_BYTES,  
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,  
                            DBCOLUMNFLAGS_ISBOOKMARK)  
        ulCols++;  
    }  
  
    // Next set the other columns up.  
    // Add a fixed length entry for OLE DB conformance testing purposes  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,  
                        10, 255, GUID_NULL, CAgentMan, dwFixed,   
                        DBCOLUMNFLAGS_WRITE |   
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand,  
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,   
                        255, 255, GUID_NULL, CAgentMan, szText,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szText2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    if (pcCols != NULL)  
    {  
        *pcCols = ulCols;  
    }  
  
    return _rgColumns;  
}  
```  
  
### <a name="default-values"></a>기본값  
 와 마찬가지로 **NULL** 데이터, 기본 값을 변경 하 여 처리할 있어야 합니다.  
  
 기본값은 `FlushData` 및 **Execute** 반환 하는 것 `S_OK`합니다. 따라서이 함수를 재정의 하지 않으면 변경 내용을 성공한 것 처럼 보이지만 (`S_OK` 반환할), 데이터 저장소에 전송 되지 않게 됩니다.  
  
 에 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플 (Rowset.h)는 `SetDBStatus` 메서드 기본 값을 다음과 같이 처리 합니다.  
  
```  
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,  
                            ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);  
  
    void* pData = NULL;  
    char* pDefaultData = NULL;  
    DWORD* pFixedData = NULL;  
  
    switch (*pdbStatus)  
    {  
        case DBSTATUS_S_DEFAULT:  
            pData = (void*)&m_rgRowData[pRow->m_iRowset];  
            if (pColInfo->wType == DBTYPE_STR)  
            {  
                pDefaultData = (char*)pData + pColInfo->cbOffset;  
                strcpy_s(pDefaultData, "Default");  
            }  
            else  
            {  
                pFixedData = (DWORD*)((BYTE*)pData +   
                                          pColInfo->cbOffset);  
                *pFixedData = 0;  
                return S_OK;  
            }  
            break;  
        case DBSTATUS_S_ISNULL:  
        default:  
            break;  
    }  
    return S_OK;  
}  
```  
  
### <a name="column-flags"></a>플래그 열  
 메타 데이터를 사용 하 여 설정 해야 하는 열에서 기본값을 지원 하는 경우는  **\< ***공급자 클래스***> w s e t** 클래스입니다. 설정 *m_bColumnHasDefault* = `VARIANT_TRUE`합니다.  
  
 있습니다를 사용 하 여 지정 된 열 플래그 설정 된 **DBCOLUMNFLAGS** 열거 형식입니다. 열 플래그 열 특성을 설명 합니다.  
  
 예를 들어는 `CUpdateSessionColSchemaRowset` 클래스 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f) (Session.h)의 첫 번째 열은 이런 방식이으로 설정:  
  
```  
// Set up column 1  
trData[0].m_ulOrdinalPosition = 1;  
trData[0].m_bIsNullable = VARIANT_FALSE;  
trData[0].m_bColumnHasDefault = VARIANT_TRUE;  
trData[0].m_nDataType = DBTYPE_UI4;  
trData[0].m_nNumericPrecision = 10;  
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |  
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;  
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));  

m_rgRowData.Add(trData[0]);  
```  
  
 이 코드 지정, 무엇 보다도 열 지원 하 고 기본값은 0, 쓰기, 가능 있고 열의 모든 데이터를 동일한 길이로 지 합니다. 가변 길이 열의에 데이터를 원하는 경우이 플래그를 설정 하지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)