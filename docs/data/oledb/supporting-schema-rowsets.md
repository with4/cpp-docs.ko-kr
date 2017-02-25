---
title: "스키마 행 집합 지원 | Microsoft Docs"
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
  - "OLE DB 소비자 템플릿, 스키마 행 집합"
  - "OLE DB 공급자, 스키마 행 집합"
  - "OLE DB, 스키마 행 집합"
  - "스키마 행 집합"
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 스키마 행 집합 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스키마 행 집합을 사용하면 데이터 저장소의 내부 구조나 스키마에 대한 정보가 없어도 소비자가 데이터 저장소에 대한 정보를 얻을 수 있습니다.  예를 들어, 데이터 저장소에 사용자 정의 계층으로 구성된 테이블이 있고 이 테이블을 읽는 것 외에는 스키마를 알 수 있는 방법이 없는 경우가 있습니다. 또 다른 예로는 Visual C\+\+ 마법사가 스키마 행 집합을 사용하여 소비자에 대한 접근자를 생성하는 것을 들 수 있습니다. 소비자가 데이터 저장소에 대한 정보를 얻을 수 있도록 하기 위해 공급자의 세션 개체가 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 인터페이스에 메서드를 노출합니다.  Visual C\+\+ 응용 프로그램에서는 [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) 클래스를 사용하여 **IDBSchemaRowset**을 구현합니다.  
  
 `IDBSchemaRowsetImpl`은 다음 메서드를 지원합니다.  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)는 스키마 행 집합에 대해 제한 유효성을 검사합니다.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)은 템플릿 매개 변수로 지정한 개체에 대해 COM 개체 작성자 함수를 구현합니다.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)는 특정 스키마 행 집합에서 지원할 제한을 지정합니다.  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)은 인터페이스에서 상속한 스키마 행 집합을 반환합니다.  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)는 인터페이스에서 상속한 `IDBSchemaRowsetImpl::GetRowset`이 액세스할 수 있는 스키마 행 집합 목록을 반환합니다.  
  
## ATL OLE DB 공급자 마법사 지원  
 ATL OLE DB 공급자 마법사는 세션 헤더 파일에 세 스키마 클래스를 만듭니다.  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 이 세 클래스는 소비자의 스키마 정보 요청에 응답합니다. OLE DB 사양에 이 세 스키마 행 집합이 지원되어야 한다고 명시되어 있습니다.  
  
-   **C** *ShortName* **SessionTRSchemaRowset**은 테이블 정보\(`DBSCHEMA_TABLES` 스키마 행 집합\)에 대한 요청을 처리합니다.  
  
-   **C** *ShortName* **SessionColSchemaRowset**은 열 정보\(**DBSCHEMA\_COLUMNS** 스키마 행 집합\)에 대한 요청을 처리합니다.  마법사가 이러한 클래스에 대해 샘플 구현을 제공하는데, 이 구현이 DOS 공급자에게 스키마 행 집합을 반환합니다.  
  
-   **C** *ShortName* **SessionPTSchemaRowset**은 공급자 종류\(**DBSCHEMA\_PROVIDER\_TYPES** 스키마 행 집합\)에 대한 스키마 정보에 대하여 요청을 처리합니다.  마법사가 제공하는 기본 구현은 `S_OK`를 반환합니다.  
  
 이 세 클래스를 사용자 지정하여 공급자에 적절한 스키마 정보를 처리할 수 있습니다.  
  
-   **C**ShortName**SessionTRSchemaRowset**에서 카탈로그, 테이블 및 설명 필드\(**trData.m\_szType**, **trData.m\_szTable** 및 **trData.m\_szDesc**\)를 채워야 합니다.  마법사가 생성한 예제는 한 행\(테이블\)만 사용합니다.  다른 공급자는 테이블을 한 개 이상 반환할 수도 있습니다.  
  
-   **C**ShortName**SessionColSchemaRowset**에서 테이블의 이름을 **DBID**로 전달합니다.  
  
## 제한 설정  
 스키마 행 집합 지원의 중요한 개념은 제한을 설정하는 것입니다. 제한은 `SetRestrictions`를 사용하여 설정합니다.  제한을 설정하면 사용자가 "MyTable"이라는 테이블의 모든 열을 찾은 다음 일치하는 행만 페치할 수 있습니다.  제한은 선택 사항입니다. 제한을 지원하지 않을 경우, 즉 기본값을 사용할 경우에는 모든 데이터가 반환됩니다.  제한을 지원하는 공급자 예제는 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플을 참조하십시오.  
  
## 스키마 맵 설정  
 UpdatePV의 Session.h에 다음과 같이 스키마 맵을 설정합니다.  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 **IDBSchemaRowset**을 지원하려면 `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** 및 **DBSCHEMA\_PROVIDER\_TYPES**를 지원해야 합니다.  필요하면 다른 스키마 행 집합을 추가할 수 있습니다.  
  
 UpdatePV의 `CUpdateSessionTRSchemaRowset`과 같이 `Execute` 메서드를 사용하여 스키마 행 집합 클래스를 선언합니다.  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 `CUpdateSession`은 `IDBSchemaRowsetImpl`에서 상속하므로 모든 제한 처리 메서드를 갖고 있습니다.  `CSchemaRowsetImpl`을 사용하여 위의 스키마 맵에 나열된 세 자식 클래스인 `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset` 및 `CUpdateSessionPTSchemaRowset`을 선언합니다.  각 자식 클래스에는 각각의 제한 집합\(검색 조건\)을 처리하는 `Execute` 메서드가 있습니다.  각 `Execute` 메서드는 `cRestrictions`와 `rgRestrictions` 매개 변수의 값을 비교합니다.  이 매개 변수에 대한 설명은 [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)를 참조하십시오.  
  
 특정 스키마 행 집합에 해당하는 제한에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]의 *OLE DB Programmer's Reference*에서 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)의 스키마 행 집합 GUID 표를 참조하십시오.  
  
 예를 들어, `DBSCHEMA_TABLES`에서 **TABLE\_NAME** 제한을 지원할 경우에는 다음과 같이 하십시오.  
  
 먼저 `DBSCHEMA_TABLES`를 찾은 다음 다음 네 제한을 순서대로 지원하는지 확인합니다.  
  
|스키마 행 집합 제한|제한 값|  
|-----------------|----------|  
|**TABLE\_CATALOG**|0x1 \(이진 1\)|  
|**TABLE\_SCHEMA**|0x2 \(이진 10\)|  
|**TABLE\_NAME**|0x4 \(이진 100\)|  
|**TABLE\_TYPE**|0x8 \(이진 1000\)|  
  
 그런 다음 각 제한에 대해 1비트씩이 있는지 확인합니다.  **TABLE\_NAME**만 지원하기 때문에 `rgRestrictions` 요소에 0x4를 반환해야 합니다.  **TABLE\_CATALOG**와 **TABLE\_NAME**을 지원할 경우에는 0x5 \(이진 101\)를 반환합니다.  
  
 기본적으로 이 구현은 제한을 하나도 지원하지 않기 때문에 모든 요청에 대해 0을 반환합니다.  UpdatePV는 제한을 지원하는 공급자 예제입니다.  
  
### 예제  
 이 코드는 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플에서 가져온 것입니다.  UpdatePv는 `DBSCHEMA_TABLES`, **DBSCHEMA\_COLUMNS** 및 **DBSCHEMA\_PROVIDER\_TYPES**의 세 필수 스키마 행 집합을 지원합니다.  공급자에 스키마 지원을 구현하는 방법을 보여 주는 예제인 이 항목에서는 **DBSCHEMA\_TABLE** 행 집합을 구현합니다.  
  
> [!NOTE]
>  샘플 코드와 여기에 있는 코드가 다르면 샘플 코드가 더 최신 버전입니다.  
  
 스키마 지원을 추가하는 첫 번째 단계는 지원할 제한을 결정하는 것입니다.  사용자의 스키마 행 집합에 사용할 수 있는 제한을 결정하려면 OLE DB 사양에서 **IDBSchemaRowset** 정의 부분을 참조하십시오.  기본 정의를 참조하면 스키마 행 집합 이름, 제한 번호, 제한 열이 포함된 테이블을 볼 수 있습니다.  지원할 스키마 행 집합을 선택하고 제한 번호와 제한 열을 기록합니다.  예를 들어, `DBSCHEMA_TABLES`는 **TABLE\_CATALOG**, **TABLE\_SCHEMA**, **TABLE\_NAME** 및 **TABLE\_TYPE**의 네가지 제한을 지원합니다.  
  
```  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 비트는 각 제한 열을 나타냅니다.  제한을 지원하려면, 즉 제한을 사용하여 쿼리하려면 비트를 1로 설정하고,  제한을 지원하지 않으려면 0으로 설정합니다.  위의 코드에서 UpdatePV는 `DBSCHEMA_TABLES` 행 집합에서 **TABLE\_NAME**과 **TABLE\_TYPE** 제한을 지원합니다.  이는 세 번째\(비트 마스크 100\)와 네 번째\(비트 마스크 1000\) 제한입니다.  따라서 UpdatePv의 비트 마스크는 1100\(또는 0x0C\)입니다.  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 다음 `Execute` 함수는 일반 행 집합의 `Execute` 함수와 비슷합니다.  `pcRowsAffected`, `cRestrictions` 및 `rgRestrictions`의 세 인수가 있습니다.  `pcRowsAffected` 변수는 공급자가 스키마 행 집합에 행 개수를 반환할 수 있는 출력 매개 변수입니다.  `cRestrictions` 매개 변수는 소비자가 공급자에게 전달한 제한 번호가 포함된 입력 매개 변수입니다.  `rgRestrictions` 매개 변수는 제한 값이 포함된 **VARIANT** 값 배열입니다.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` 변수는 공급자가 제한을 지원하는지에 관계없이 스키마 행 집합의 총 제한 개수를 기반으로 합니다.  UpdatePv는 세 번째와 네 번째 제한을 지원하므로 이 코드는 3보다 크거나 같은 `cRestrictions` 값만 찾습니다.  
  
 **TABLE\_NAME** 제한의 값은 `rgRestrictions[2]`에 저장됩니다. 0부터 시작하는 배열에서는 세 번째 제한이 2가 됩니다.  실제로 제한을 지원하려면 제한이 `VT_EMPTY`가 아닌지 확인해야 합니다.  **VT\_NULL**은 `VT_EMPTY`와 다릅니다.  **VT\_NULL**은 유효한 제한 값을 지정합니다.  
  
 테이블 이름에 대한 UpdatePv 정의는 텍스트 파일에 대한 정규화된 경로 이름입니다.  제한 값을 추출한 다음 파일을 열어 파일이 실제로 있는지 확인합니다.  파일이 없으면 `S_OK`를 반환합니다.  약간 이상할 수도 있지만 실제로는 지정한 이름이 지원하는 테이블이 없음을 소비자에게 알리는 것입니다.  즉, `S_OK`가 반환되면 코드가 제대로 실행된 것입니다.  
  
```  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 네 번째 제한\(**TABLE\_TYPE**\)을 지원하는 것은 세 번째 제한을 지원하는 것과 비슷합니다.  값이 `VT_EMPTY`가 아닌지 확인합니다.  이 제한은 **TABLE** 테이블 형식만 반환합니다.  `DBSCHEMA_TABLES`에 대한 유효한 값을 확인하려면 **TABLES** 행 집합 단원에 있는 OLE DB Programmer's Reference의 부록 B를 참조하십시오.  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 여기에 행 집합에 대한 행 항목을 실제로 만듭니다.  `trData` 변수는 OLE DB 공급자 템플릿에 정의된 구조인 **CTABLESRow**에 해당합니다.  **CTABLESRow**는 OLE DB 사양의 부록 B에 있는 **TABLES** 행 집합 정의에 해당합니다.  한 번에 한 테이블만 지원할 수 있으므로 추가할 행을 하나만 갖게 됩니다.  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  
wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  
wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV는 **TABLE\_NAME**, **TABLE\_TYPE** 및 **DESCRIPTION** 세 열만 설정합니다.  `GetDBStatus`를 구현할 때 필요하므로 정보를 반환할 열을 기록해 두어야 합니다.  
  
```  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 `GetDBStatus` 함수는 스키마 행 집합이 제대로 작동하도록 하기 위한 아주 중요한 함수입니다.  **TABLES** 행 집합의 모든 열에 데이터를 반환하지는 않기 때문에 데이터를 반환할 열과 반환하지 않을 열을 지정해야 합니다.  
  
```  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 `Execute` 함수는 **TABLES** 행 집합의 **TABLE\_NAME**, **TABLE\_TYPE** 및 **DESCRIPTION** 필드에 대해 데이터를 반환하므로, OLE DB 사양의 부록 B에서 이 필드가 위에서부터 아래로 서수 3, 4, 6임을 확인할 수 있습니다.  이러한 각 열에 대해 **DBSTATUS\_S\_OK**를 반환합니다.  나머지 열에 대해서는 **DBSTATUS\_S\_ISNULL**을 반환합니다.  소비자는 사용자가 반환한 값이 **NULL**인지 아니면 다른 값인지를 알 수 없기 때문에 반드시 이 상태를 반환해야 합니다.  여기서도 마찬가지로 **NULL**은 비어 있는 것과는 다릅니다.  
  
 OLE DB 스키마 행 집합 인터페이스에 대한 자세한 내용은 OLE DB Programmer's Reference의 [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md)을 참조하십시오.  
  
 소비자가 **IDBSchemaRowset** 메서드를 사용하는 방법에 대한 자세한 내용은 [스키마 행 집합을 사용하여 메타데이터 구하기](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)를 참조하십시오.  
  
 스키마 행 집합을 지원하는 공급자 예제는 [UpdatePV](http://msdn.microsoft.com/ko-kr/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플을 참조하십시오.  
  
## 참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)