---
title: 스키마 행 집합 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c0468a9df7b79e79b3e20074c43fc1621058d71
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339707"
---
# <a name="supporting-schema-rowsets"></a>스키마 행 집합 지원
스키마 행 집합에는 소비자가 해당 기본 구조 또는 스키마를 몰라도 데이터 저장소에 대 한 정보를 얻을 수 있습니다. 예를 들어, 데이터 저장소를 읽는 것 외에 스키마를 알 수 없기 때문에 사용자 정의 계층을 구성 하는 테이블이 있을 수 있습니다. (또 다른 예로, note는 Visual c + + 마법사 사용 하 여 스키마 행 집합 생성 소비자는 접근자입니다.) 이 작업을 수행 하기 위해 소비자를 허용 하려면 공급자의 세션 개체에 메서드를 노출 합니다 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) 인터페이스입니다. Visual c + + 응용 프로그램을 사용 하 여 합니다 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) 구현 하는 클래스 `IDBSchemaRowset`합니다.  
  
 `IDBSchemaRowsetImpl` 다음 메서드를 지원합니다.  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) 스키마 행 집합에 대해 제한의 유효성을 검사 합니다.  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) 템플릿 매개 변수로 지정 된 개체에 대 한 COM 개체 작성자 함수를 구현 합니다.  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) 특정 스키마 행 집합에서 지원 되는 제한을 지정 합니다.  
  
-   [Idbschemarowset:: Getrowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) (인터페이스에서 상속) 스키마 행 집합을 반환 합니다.  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) 스키마 행 집합 목록을 액세스할 반환 `IDBSchemaRowsetImpl::GetRowset` (인터페이스에서 상속).  
  
## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB 공급자 마법사 지원  
 ATL OLE DB 공급자 마법사 세션 헤더 파일에 세 개의 스키마 클래스를 만듭니다.  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 이러한 클래스는 스키마 정보에 대 한 소비자 요청에 응답 OLE DB 사양에 이러한 세 개의 스키마 행 집합 지원 될 수는 note:  
  
-   **C** *ShortName* **SessionTRSchemaRowset** 테이블 정보에 대 한 요청 처리 (의 `DBSCHEMA_TABLES` 스키마 행 집합).  
  
-   **C** *ShortName* **SessionColSchemaRowset** 열 정보에 대 한 요청 처리 (의 `DBSCHEMA_COLUMNS` 스키마 행 집합). 마법사는 DOS 공급자에 대 한 스키마 정보를 반환 하는 이러한 클래스에 대 한 샘플 구현을 제공 합니다.  
  
-   **C** *ShortName* **SessionPTSchemaRowset** 공급자 유형에 대 한 스키마 정보에 대 한 요청 처리 (의 `DBSCHEMA_PROVIDER_TYPES` 스키마 행 집합). 마법사에서 제공 하는 기본 구현은 반환 `S_OK`합니다.  
  
 이러한 클래스를 공급자에 게 적절 한 스키마 정보를 처리를 사용자 지정할 수 있습니다.  
  
-   **C***ShortName***SessionTRSchemaRowset**, 카탈로그, 테이블 및 설명 필드를 작성 해야 (`trData.m_szType`를 `trData.m_szTable`, 및 `trData.m_szDesc`). 마법사에서 생성 된 예제는 하나의 행 (테이블)를 사용합니다. 다른 공급자는 둘 이상의 테이블을 반환할 수 있습니다.  
  
-   **C***ShortName***SessionColSchemaRowset**, 테이블의 이름을 전달는 `DBID`합니다.  
  
## <a name="setting-restrictions"></a>제한 설정  
 스키마 행 집합 지원에서 중요 한 개념은 설정 하는 사용 하 여 작업을 수행할 있습니다 `SetRestrictions`합니다. 제한을 통해 소비자는 일치하는 행만 페치할 수 있습니다. 예를 들어 "MyTable" 테이블의 모든 열을 찾을 수 있습니다. 제한은 선택 사항이므로 지원되는 제한이 없는 경우(기본값) 항상 모든 데이터가 반환됩니다. 에서는 제한 사항을 지원 하는 공급자의 예제를 참조 합니다 [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플입니다.  
  
## <a name="setting-up-the-schema-map"></a>스키마 맵 설정  
 UpdatePV에서 Session.h에서이 이와 같은 스키마 맵을 설정 합니다.  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 지원 하기 위해 `IDBSchemaRowset`를 지원 해야 `DBSCHEMA_TABLES`를 `DBSCHEMA_COLUMNS`, 및 `DBSCHEMA_PROVIDER_TYPES`합니다. 판단에 따라 추가 스키마 행 집합을 추가할 수 있습니다.  
  
 사용 하 여 스키마 행 집합 클래스를 선언를 `Execute` 메서드와 같은 `CUpdateSessionTRSchemaRowset` UpdatePV에서:  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 사실은 `CUpdateSession` 에서 상속 `IDBSchemaRowsetImpl`모든 제한 메서드를 처리 하므로, 합니다. 사용 하 여 `CSchemaRowsetImpl`합니다 (위의 스키마 구조의 나열 됨) 하는 세 개의 자식 클래스를 선언: `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, 및 `CUpdateSessionPTSchemaRowset`합니다. 각 자식 클래스에는 `Execute` 해당 집합이 제한 (검색 조건)를 처리 하는 메서드. 각 `Execute` 메서드 값을 비교 합니다 `cRestrictions` 고 `rgRestrictions` 매개 변수입니다. 이러한 매개 변수 설명을 참조 [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)합니다.  
  
 특정 스키마 행 집합으로 해당 제한 사항에 대 한 자세한 내용은 스키마 행 집합 Guid 표를 참조에서 [IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* 에 Windows SDK입니다.  
  
 예를 들어 지원 하는 **TABLE_NAME** 에 대 한 제한 `DBSCHEMA_TABLES`, 다음을 수행 합니다.  
  
 먼저 조회 `DBSCHEMA_TABLES` 순서 대로 4 개의 제한을 지원 하는지 확인 합니다.  
  
|스키마 행 집합 제한|제한 값|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0x1 (이진 1)|  
|**TABLE_SCHEMA**|0x2 (이진 10)|  
|**TABLE_NAME**|0x4 (이진 100)|  
|**TABLE_TYPE**|0x8 (이진 1000)|  
  
 다음으로, 각 제한에 대 한 1 비트는 note 합니다. 지원 하려는 **TABLE_NAME** 0x4에만 반환 합니다 `rgRestrictions` 요소. 지원 하면 **TABLE_CATALOG** 하 고 **TABLE_NAME**, 0x5 (이진 101)를 반환 합니다.  
  
 기본적으로 구현은 모든 요청에 대 한 (제한이 지원 하지 않습니다) 하는 0을 반환 합니다. UpdatePV은 예에서는 제한 사항을 지원 하는 공급자입니다.  
  
### <a name="example"></a>예  
 이 코드에서 수행 되는 [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플입니다. UpdatePv 세 가지 필수 스키마 행 집합을 지원 합니다. `DBSCHEMA_TABLES`, `DBSCHEMA_COLUMNS`, 및 `DBSCHEMA_PROVIDER_TYPES`합니다. 공급자에서 지 원하는 스키마를 구현 하는 방법의 예를 들어,이 항목에서는 구현 된 `DBSCHEMA_TABLE` 행 집합입니다.  
  
> [!NOTE]
>  샘플 코드입니다; 여기에 표시 된 것과 다를 수 있습니다. 샘플 코드를 좀 더 최신 버전으로 간주 해야 합니다.  
  
 첫 번째 단계에서 지 원하는 스키마 추가 되는 제한을 지원 하려는 결정 하는 것입니다. 정의 대 한 OLE DB 사양에 표시 되는 제한을 스키마 행 집합 수를 확인 하려면 `IDBSchemaRowset`합니다. 기본 정의 다음 스키마 행 집합 이름, 제한 사항 수가 제한 열이 포함 된 테이블을 참조 하세요. 지원 제한 사항 및 제한 열 수가 적어 하려는 스키마 행 집합을 선택 합니다. 예를 들어 `DBSCHEMA_TABLES` 4 개의 제한이 지원 (**TABLE_CATALOG**를 **TABLE_SCHEMA**를 **TABLE_NAME**, 및 **TABLE_TYPE** ):  
  
```cpp  
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
  
 잠시 각 제한 열을 나타냅니다. 지원 제한 하려는 경우 (즉, 쿼리할 수 있습니다 하), 해당 비트를 1로 설정 합니다. 제한을 지원 하지 않을 경우 해당 비트를 0으로 설정 합니다. 위 코드의 줄 UpdatePV 지원 합니다 **TABLE_NAME** 및 **TABLE_TYPE** 에 대 한 제한은 `DBSCHEMA_TABLES` 행 집합. 이 세 번째 (비트 마스크 100)와 네 번째 (비트 마스크 1000) 제한 합니다. 따라서 UpdatePv에 대 한 비트 마스크는 1100 (또는 0x0C):  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 다음 `Execute` 함수는 일반 행 집합의 경우와 비슷합니다. 세 가지 인수가 있는: *pcRowsAffected*를 *cRestrictions*, 및 *rgRestrictions*합니다. 합니다 *pcRowsAffected* 변수가 출력 매개 변수 공급자가 스키마 행 집합에서의 행 수를 반환할 수 있습니다. 합니다 *cRestrictions* 매개 변수는 공급자에는 소비자가 전달한 제한 수를 포함 하는 입력된 매개 변수입니다. 합니다 *rgRestrictions* 매개 변수는 배열이 `VARIANT` 제한 값을 포함 하는 값입니다.  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` 변수 공급자를 지원 하는지 여부에 관계 없이 스키마 행 집합에 대 한 제한의 총 수를 기반으로 합니다. UpdatePv 두 가지 제한은 (세 번째 및 네 번째)를 지원 하므로이 코드 검색을 `cRestrictions` 값 보다 크거나 같은 세 가지입니다.  
  
 에 대 한 값을 **TABLE_NAME** 제한에 저장 된 `rgRestrictions[2]` (첫 번째 열에서 세 번째 제한 역시 2). 실제로 지원 하도록 VT_EMPTY 되어 있지 않은지 확인 해야 합니다. 참고 VT_NULL VT_EMPTY와 같지 않습니다. VT_NULL 유효한 제한 값을 지정 합니다.  
  
 테이블 이름의 UpdatePv 정의는 텍스트 파일에 정규화 된 경로 이름입니다. 제한 값을 추출 하 고 파일에 실제로 존재 하는지 확인 하려면 파일을 열려고 시도 합니다. 파일이 없으면 S_OK를 반환 합니다. 약간 이상 해 보이지만이 이지만 코드는 소비자를 알리는 실제로 지정 된 이름으로 지원 되는 테이블이 되었습니다. S_OK가 반환 되 면 코드가 올바르게 실행을 의미 합니다.  
  
```cpp  
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
  
 네 번째 제한 지원 (**TABLE_TYPE**) 세 번째 제한 하는 것과 비슷합니다. 값을 VT_EMPTY 아닌지 확인 합니다. 이 제한은 테이블 형식을 반환 **테이블**합니다. 에 대 한 유효한 값을 결정 하는 `DBSCHEMA_TABLES`, 부록 B를 찾는 위치를 *OLE DB Programmer's Reference* 에 **테이블** 행 집합 섹션.  
  
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
  
 이 실제로 행 집합에 대 한 행 항목을 만듭니다. 변수의 `trData` 에 해당 `CTABLESRow`, OLE DB 공급자 템플릿에 정의 된 구조체입니다. `CTABLESRow` 에 해당 하는 **테이블** OLE DB 사양의 부록 B에 행 집합을 정의 합니다. 한 번에 하나의 테이블만 지원할 수 있기 때문에 추가할 하나의 행을 하나만 있습니다.  
  
```cpp  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV 세 개의 열으로 설정 합니다. **TABLE_NAME**, **TABLE_TYPE**, 및 **설명**합니다. 구현 하는 경우이 정보를 필요 하기 때문에 정보를 반환할 열의 참고 해야 `GetDBStatus`:  
  
```cpp  
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
  
 `GetDBStatus` 함수는 스키마 행 집합의 올바른 작동에 매우 중요 합니다. 모든 열에 대 한 데이터를 반환 하지 않는 것 때문에 합니다 **테이블** 열에 대 한 데이터 및 돌아갈 하지 않을 지정 해야 하는 행 집합입니다.  
  
```cpp  
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
  
 때문에 `Execute` 함수에 대 한 데이터를 반환 합니다 **TABLE_NAME**, **TABLE_TYPE**, 및 **설명** 에서 필드를 **테이블**행 집합, OLE DB 사양의 부록 B를 확인 하 고 확인할 수 (세어 위에서) 3, 4 및 6의 서 수는 있습니다. 각 열에 대해 DBSTATUS_S_OK를 반환 합니다. 다른 모든 열에는 DBSTATUS_S_ISNULL을 반환 합니다. 소비자 사용자가 반환한 값이 NULL 또는 다른 요소는 것을 알 수 없기 때문에 것이 상태를 반환 해야 합니다. NULL은 빈에 해당 하는 참고 다시 합니다.  
  
 OLE DB 스키마 행 집합 인터페이스에 대 한 자세한 내용은 참조는 [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) OLE DB 프로그래머 참조에서 인터페이스입니다.  
  
 소비자가 사용 하 여 방법에 대 한 자세한 `IDBSchemaRowset` 메서드를 참조 하세요 [스키마 행 집합을 사용 하 여 메타 데이터 구하기](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)합니다.  
  
 스키마 행 집합을 지 원하는 공급자의 예제를 참조 합니다 [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f) 샘플입니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)