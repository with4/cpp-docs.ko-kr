---
title: CXMLAccessor 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f25d02b5b8b86a70f63dc2b0ca8d2ba9cb60066b
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233420"
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor 클래스
데이터 저장소의 스키마 (내부 구조)에 대 한 지식이 없는 경우 문자열 데이터로 데이터 원본에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  

## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetXMLColumnData](#getxmlcolumndata)|열 정보를 검색합니다.|  
|[GetXMLRowData](#getxmlrowdata)|행을 기준으로 테이블의 전체 콘텐츠를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 그러나 `CXMLAccessor` 에서 다른 `CDynamicStringAccessorW` (태그가 지정 된) 데이터를 XML 형식으로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 하는 합니다. 출력 XML 인식 웹 페이지에 특히 유용합니다. XML 태그 이름에는 최대한 가깝게 데이터 저장소의 열 이름과 일치 됩니다.  
  
 사용 하 여 `CDynamicAccessor` 열 정보를 가져오는 방법입니다. 이 열 정보를 사용 하 여 접근자를 런타임에 동적으로 만듭니다.  
  
 열 정보를 만들고이 클래스에 의해 관리 되는 버퍼에 저장 됩니다. 사용 하 여 열 정보를 가져올 [GetXMLColumnData](#getxmlcolumndata) 하거나 사용 하 여 행에서 열 데이터를 가져오는 [GetXMLRowData](#getxmlrowdata)합니다.  
  
## <a name="example"></a>예  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  

## <a name="getxmlcolumndata"></a> Cxmlaccessor:: Getxmlcolumndata
열을 기준으로 XML 형식의 문자열 데이터를 테이블의 열 형식 정보를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *strOutput*  
 [out] 검색할 열 형식 정보를 포함 하는 문자열 버퍼에 대 한 참조입니다. 문자열은 데이터 저장소의 열 이름과 일치 하는 XML 태그 이름의 형식은입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 다음 열 형식 정보는 XML에서 형식 지정 하는 방법을 보여 줍니다. `type` 열의 데이터 형식을 지정합니다. 데이터 형식은 OLE DB 데이터 형식 액세스 중인 데이터베이스의 해당 하지 기반한 note 합니다.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>` 

## <a name="getxmlrowdata"></a> Cxmlaccessor:: Getxmlrowdata
행으로 XML 형식의 문자열 데이터로 테이블의 전체 콘텐츠를 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput,   
   bool bAppend = false) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *strOutput*  
 [out] 검색할 테이블 데이터를 포함 하는 버퍼에 대 한 참조입니다. 데이터 형식은 데이터 저장소의 열 이름과 일치 하는 XML 태그 이름의 문자열 데이터는입니다.  
  
 *bAppend*  
 [in] 출력 데이터의 끝에 문자열을 추가할지 여부를 지정 하는 부울 값입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 다음 XML에서 행 데이터를 포맷 하는 방법을 보여 줍니다. `DATA` 아래 행 데이터를 표시 합니다. 사용 하 여 원하는 행으로 이동 하는 메서드를 이동 합니다.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`   
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA 클래스](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW 클래스](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)