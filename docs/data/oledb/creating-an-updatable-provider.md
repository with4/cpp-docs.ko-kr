---
title: "업데이트 가능 공급자 만들기 | Microsoft Docs"
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
  - "알림, 공급자 지원"
  - "OLE DB 공급자, 만들기"
  - "OLE DB 공급자, 업데이트 가능"
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 업데이트 가능 공급자 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0은 읽기 전용 공급자만 지원합니다.  Visual C\+\+ .NET은 업데이트 가능 공급자를 지원합니다. 또는 데이터 저장소를 업데이트할 수 있는, 즉 데이터 저장소에 쓸 수 있는 공급자를 지원합니다.  이 항목에서는 OLE DB 템플릿을 사용하여 업데이트 가능 공급자를 만드는 방법에 대해 설명합니다.  
  
 이 항목에서는 작동 가능한 공급자가 있고 이 공급자로 작업을 시작한다고 가정합니다.  업데이트 가능 공급자를 만들려면 두 단계 작업을 해야 합니다.  먼저 공급자가 데이터 저장소를 변경하는 방법\(변경이 즉시 이루어지는지 업데이트 명령을 발행할 때까지 변경이 지연되는지 여부\)을 결정해야 합니다.  공급자 코드에서 수행해야 할 변경 내용과 설정에 대한 설명은 "[공급자를 업데이트할 수 있도록 만들기](#vchowmakingprovidersupdatable)" 단원에서 설명합니다.  
  
 그런 다음 소비자가 요청하는 것을 지원하기 위한 모든 기능이 공급자에게 있는지 확인해야 합니다.  소비자가 데이터 저장소를 업데이트하려는 경우에는 공급자에게 데이터 저장소의 데이터를 영구히 보존하는 코드가 있어야 합니다.  예를 들어, C 런타임 라이브러리나 MFC를 사용하여 데이터 소스에서 이러한 작업을 할 수 있습니다.  데이터 소스에 쓰는 방법, **NULL**과 기본값을 처리하는 방법 및 열 플래그를 설정하는 방법에 대해서는 "[데이터 소스에 쓰기](#vchowwritingtothedatasource)" 단원에서 설명합니다.  
  
> [!NOTE]
>  UpdatePV는 업데이트 가능 공급자의 한 예입니다.  UpdatePV는 MyProv와 같지만 업데이트를 지원합니다.  
  
##  <a name="vchowmakingprovidersupdatable"></a> 공급자를 업데이트 가능 공급자로 만들기  
 공급자를 업데이트 가능 공급자로 만들기 위한 핵심은 데이터 저장소에서 공급자가 수행할 작업과 이러한 작업의 수행 방법을 이해하는 것입니다.  특히, 데이터 저장소에 대한 업데이트를 즉시 수행할지 아니면 명령이 발생될 때까지 지연되도록\(일괄 처리되도록\)할지가 중요한 문제입니다.  
  
 먼저 행 집합 클래스의 `IRowsetChangeImpl`에서 상속할지 또는 `IRowsetUpdateImpl`에서 상속할지 결정해야 합니다.  둘 중 어느 것을 선택하여 구현하느냐에 따라 `SetData`, **InsertRows** 및 `DeleteRows`의 세 메서드의 기능에 영향을 줍니다.  
  
-   [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)에서 상속할 경우 이 세 메서드를 호출하면 데이터 저장소가 즉시 변경됩니다.  
  
-   [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)에서 상속할 경우 이 세 메서드는 **Update**, `GetOriginalData` 또는 **Undo**를 호출할 때까지 데이터 저장소에 대한 변경을 지연합니다.  업데이트에 여러 변경이 포함될 경우에는 변경이 일괄 처리 모드로 수행됩니다. 변경을 일괄 처리하면 메모리 오버헤드가 눈에 띄게 늘어납니다.  
  
 `IRowsetUpdateImpl`은 `IRowsetChangeImpl`에서 파생됩니다.  따라서 `IRowsetUpdateImpl`은 변경 기능뿐만 아니라 일괄 처리 기능을 제공합니다.  
  
#### 공급자에서 업데이트를 지원하려면  
  
1.  행 집합 클래스에서 `IRowsetChangeImpl`이나 `IRowsetUpdateImpl`로부터 상속합니다.  이 두 클래스는 데이터 저장소 변경에 대한 적절한 인터페이스를 제공합니다.  
  
     **IRowsetChange 추가**  
  
     다음 형식을 사용하여 상속 체인에 `IRowsetChangeImpl`을 추가합니다.  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     행 집합 클래스의 `BEGIN_COM_MAP` 구역에 `COM_INTERFACE_ENTRY(IRowsetChange)`도 추가합니다.  
  
     **IRowsetUpdate 추가**  
  
     다음 형식을 사용하여 상속 체인에 `IRowsetUpdate`를 추가합니다.  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  상속 체인에서 `IRowsetChangeImpl` 줄을 제거해야 합니다.  앞의 지시문에서 `IRowsetChangeImpl` 줄을 제거한 곳에 `IRowsetChangeImpl`에 대한 코드를 포함해야 합니다.  
  
2.  COM 맵\(**BEGIN\_COM\_MAP ... END\_COM\_MAP**\):  
  
    |구현할 클래스|COM 맵에 추가할 코드|  
    |-------------|-------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  명령에서 속성 집합 맵\(**BEGIN\_PROPSET\_MAP ... END\_PROPSET\_MAP**\)에 다음을 추가합니다.  
  
    |구현할 클래스|속성 집합 맵에 추가할 코드|  
    |-------------|---------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  또한 다음 설정을 모두 그대로 속성 집합 맵에 포함시켜야 합니다.  
  
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
  
     Atldb.h에서 속성 ID와 값을 보고 이러한 매크로 호출에 사용된 값을 찾을 수 있습니다. Atldb.h가 온라인 설명서와 다를 경우에는 Atldb.h가 설명서보다 우선합니다.  
  
    > [!NOTE]
    >  **VARIANT\_FALSE**와 `VARIANT_TRUE` 설정의 대부분은 OLE DB 템플릿의 필수 요소입니다. OLE DB 사양에서는 이 둘을 읽기\/쓰기라고 명시하지만 OLE DB 템플릿은 두 값 중 하나만 지원할 수 있습니다.  
  
     **IRowsetChangeImpl을 구현하려면**  
  
     `IRowsetChangeImpl`을 구현하려면 공급자에 다음 속성을 설정해야 합니다.  다음 속성은 주로 **ICommandProperties::SetProperties**를 통해 인터페이스를 요청하는 데 사용됩니다.  
  
    -   `DBPROP_IRowsetChange`: 이 값을 설정하면 **DBPROP\_IRowsetChange**가 자동으로 설정됩니다.  
  
    -   `DBPROP_UPDATABILITY`: A bitmask specifying the supported methods on `IRowsetChange`: `SetData`, `DeleteRows` 또는 `InsertRow`에 지원되는 메서드를 지정하는 비트 마스크입니다.  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: 소비자는 새로 삽입한 행에 대해 **IRowsetChange::DeleteRows** 또는 `SetData`를 호출할 수 있습니다.  
  
    -   `DBPROP_IMMOBILEROWS`: 행 집합이 삽입되거나 업데이트된 행의 순서를 바꾸지 않습니다.  
  
     **IRowsetUpdateImpl을 구현하려면**  
  
     `IRowsetUpdateImpl`을 구현하려면 앞에서 나열한 `IRowsetChangeImpl`에 대한 모든 속성 외에도 다음 속성을 공급자에 설정해야 합니다.  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: READ\_ONLY AND VARIANT\_TRUE로 설정해야 합니다.  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ\_ONLY AND VARIANT\_TRUE로 설정해야 합니다.  
  
    -   `DBPROP_OTHERINSERT`: READ\_ONLY AND VARIANT\_TRUE로 설정해야 합니다.  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ\_ONLY AND VARIANT\_TRUE로 설정해야 합니다.  
  
    -   `DBPROP_REMOVEDELETED`: READ\_ONLY AND VARIANT\_TRUE로 설정해야 합니다.  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  알림을 지원할 경우에는 다른 속성도 설정해야 합니다. 설정할 속성 목록은 `IRowsetNotifyCP`에 대한 단원을 참조하십시오.  
  
     속성 설정 방법에 대한 예제를 보려면 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f)의 **CUpdateCommand**\(Rowset.h에 있음\)에 있는 속성 설정 맵을 참조하십시오.  
  
##  <a name="vchowwritingtothedatasource"></a> 데이터 소스에 쓰기  
 데이터 소스에서 읽으려면 **Execute** 함수를 호출하고,  데이터 소스에 쓰려면 `FlushData` 함수를 호출합니다. 일반적으로 플러시는 테이블이나 인덱스에 수정한 내용을 디스크에 저장하는 것을 의미합니다.  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 행 핸들\(*HROW*\)과 접근자 핸들\(*HACCESSOR*\) 인수를 사용하여 쓰려는 영역을 지정할 수 있습니다.  대개 한 번에 한 데이터 필드에 씁니다.  
  
 `FlushData` 메서드는 데이터가 원래 저장된 형식으로 데이터를 씁니다.  이 함수를 재정의하지 않을 경우 공급자는 제대로 작동하지만 변경 내용이 데이터 저장소로 플러시되지 않습니다.  
  
### 플러시할 시기  
 공급자 템플릿은 데이터 저장소에 데이터를 써야 할 때마다 `FlushData`를 호출합니다. 항상 그런 것은 아니지만 일반적으로 다음 함수를 호출하면 공급자 템플릿이 `FlushData`를 호출합니다.  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows**\(행에 삽입할 새 데이터가 있을 경우\)  
  
-   **IRowsetUpdate::Update**  
  
### 작동 방식  
 소비자가 **Update**와 같이 플러시를 필요로 하는 호출을 만들면 호출이 공급자로 전달되고 공급자는 항상 다음 작업을 수행합니다.  
  
-   연결된 상태 값이 있을 때마다 `SetDBStatus`를 호출합니다. OLE DB Programmers Reference 6장, Data Parts: Status를 참조하십시오.  
  
-   열 플래그를 확인합니다.  
  
-   `IsUpdateAllowed`를 호출합니다.  
  
 이 세 단계는 보안을 제공합니다.  그런 다음 공급자가 `FlushData`를 호출합니다.  
  
### FlushData 구현 방법  
 `FlushData`를 구현하려면 다음과 같은 몇 가지 문제를 고려해야 합니다.  
  
-   데이터 저장소가 변경 내용을 처리할 수 있어야 합니다.  
  
-   **NULL** 값을 처리할 수 있어야 합니다.  
  
-   기본값을 처리할 수 있어야 합니다.  
  
 사용자 고유의 `FlushData` 메서드를 구현하려면 다음과 같이 하십시오.  
  
-   행 집합 클래스로 이동합니다.  
  
-   행 집합 클래스에 다음 선언을 넣습니다.  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   `FlushData`에 대한 구현을 제공합니다.  
  
 `FlushData`를 제대로 구현하면 실제로 업데이트된 행과 열만 저장합니다.  HROW와 HACCESSOR 매개 변수를 사용하여 최적화를 위해 저장할 현재 행과 열을 확인할 수 있습니다.  
  
 일반적으로 가장 어려운 문제는 사용자의 원시 데이터 저장소로 작업하는 것입니다.  가능하면 다음과 같이 하십시오.  
  
-   데이터 저장소에 쓰는 메서드를 되도록 단순하게 유지합니다.  
  
-   **NULL** 값을 처리합니다. 선택 사항이지만 이 옵션을 사용하는 것이 좋습니다.  
  
-   기본값을 처리합니다. 선택 사항이지만 이 옵션을 사용하는 것이 좋습니다.  
  
 가장 좋은 방법은 데이터 저장소에 **NULL** 값과 기본값에 대한 값을 실제로 지정하는 것입니다.  이 데이터를 추측할 수 있으면 가장 좋지만,  그렇지 않을 경우에는 **NULL** 값과 기본값을 허용하지 않는 것이 좋습니다.  
  
 다음은 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플의 `RUpdateRowset` 클래스에 `FlushData`를 구현하는 방법에 대한 예제입니다\(샘플 코드의 Rowset.h 참조\).  
  
```  
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
  
### 변경 내용 처리  
 공급자가 변경 내용을 처리할 수 있도록 하려면 먼저 데이터 저장소\(예: 텍스트 파일, 비디오 파일 등\)에 데이터 저장소를 변경할 수 있는 기능이 있는지 확인해야 합니다.  이러한 기능이 없으면 공급자 프로젝트와는 별도로 해당 코드를 만들어야 합니다.  
  
### NULL 데이터 처리  
 최종 사용자가 **NULL** 데이터를 보내는 경우가 있을 수 있습니다.  데이터 소스의 필드에 **NULL** 값을 쓰게 되면 문제가 발생할 가능성이 있습니다.  도시와 우편 번호 값을 허용하는 주문 처리 응용 프로그램이 있다고 가정합니다. 이 응용 프로그램은 두 값 중 하나 또는 두 값 모두를 허용할 수는 있지만, 두 값을 모두 허용하지 않는 경우 상품 배달이 불가능하기 때문에 두 값을 모두 허용하지 않을 수는 없습니다.  이 경우 응용 프로그램이 제대로 작동하려면 필드에 특정 **NULL** 값 조합만 넣을 수 있도록 제한해야 합니다.  
  
 공급자를 개발하는 개발자는 데이터를 저장하는 방법, 데이터 저장소에서 데이터를 읽는 방법 및 사용자에게 이러한 방법을 지정하는 방법 등을 고려해야 합니다.  특히, 데이터 소스에 있는 행 집합 데이터의 상태\(예: DataStatus \= **NULL**\)를 변경하는 방법을 고려해야 합니다.  즉, 소비자가 **NULL** 값이 있는 필드에 액세스할 경우 소비자에게 반환할 값을 결정해야 합니다.  
  
 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플의 코드를 검토하십시오. 이 샘플을 통해 공급자가 **NULL** 데이터를 처리하는 방법을 볼 수 있습니다.  UpdatePV에서 공급자는 데이터 저장소에 "NULL" 문자열을 씀으로써 **NULL** 데이터를 저장합니다.  공급자가 데이터 저장소에서 **NULL** 데이터를 읽을 경우 "NULL" 문자열을 식별한 다음 **NULL** 문자열을 만들어 버퍼를 비웁니다.  `IRowsetImpl::GetDBStatus`를 재정의한 것도 포함되어 있는데, 이 경우 데이터 값이 비어 있으면 **DBSTATUS\_S\_ISNULL**을 반환합니다.  
  
### Null 허용 열 표시  
 스키마 행 집합\(`IDBSchemaRowsetImpl` 참조\)을 구현하려면 **DBSCHEMA\_COLUMNS** 행 집합\(일반적으로 공급자에서 **C**xxx**SchemaColSchemaRowset**으로 표시된 행 집합\)에 열이 Null 허용 열임을 지정해야 합니다.  
  
 또한 모든 Null 허용 열에 **DBCOLUMNFLAGS\_ISNULLABLE** 값이 포함됨을 사용자의 `GetColumnInfo`버전에 지정해야 합니다.  
  
 OLE DB 템플릿을 구현할 때 열을 Null 허용 열로 표시하지 않으면 공급자는 열이 값을 포함해야 하고 소비자가 Null 값으로 된 열을 보낼 수 없는 것으로 간주하게 됩니다.  
  
 다음 예제에서는 UpdatePV의 **CUpdateCommand**\(UpProvRS.cpp 참조\)에 **CommonGetColInfo** 함수를 구현하는 방법을 보여 줍니다.  어떤 방법으로 Null 허용 열에 **DBCOLUMNFLAGS\_ISNULLABLE**이 설정되는지 주목하여 보십시오.  
  
```  
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
  
### 기본값  
 **NULL** 데이터와 마찬가지로 변경되는 기본값도 처리할 수 있어야 합니다.  
  
 `FlushData`와 **Execute**의 기본값은 `S_OK`를 반환하는 것입니다.  따라서 이 함수를 재정의하지 않으면 `S_OK`가 반환되어 변경 내용이 성공한 것처럼 보이지만 변경 내용이 데이터 저장소로 전송되지 않게 됩니다.  
  
 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플\(Rowset.h에 있음\)에서 `SetDBStatus` 메서드는 기본값을 다음과 같이 처리합니다.  
  
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
  
### 열 플래그  
 If you support default values on your columns, you need to set it using metadata in the **\<***provider class***\>SchemaRowset** class.  m\_bColumnHasDefault \= `VARIANT_TRUE`로 설정합니다.  
  
 열 플래그도 설정해야 합니다. **DBCOLUMNFLAGS** 열거 형식을 사용하여 설정할 수 있습니다.  열 플래그는 열 특성을 설명합니다.  
  
 예를 들어, [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f)\(Session.h에 있음\)의 `CUpdateSessionColSchemaRowset` 클래스에는 첫째 열이 다음과 같이 설정되어 있습니다.  
  
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
  
 이 코드는 특히 열이 기본값 0을 지원하고, 쓰기 가능하며, 이 열에 있는 각 데이터의 길이가 모두 같다는 것을 지정합니다.  열에 있는 각 데이터의 길이를 다양하게 하려면 이 플래그를 설정하지 않아야 합니다.  
  
## 참고 항목  
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)