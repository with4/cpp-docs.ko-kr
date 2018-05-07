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
dev_langs:
- C++
helpviewer_keywords:
- CXMLAccessor class
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 916e9dbe4e142192e4e716f57f97d5bd6865c709
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cxmlaccessor-class"></a>CXMLAccessor 클래스
데이터 저장소의 스키마 (기본 구조)에 대해 알지 못합니다 때 문자열 데이터로 데이터 소스에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문

```cpp
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|열 정보를 검색합니다.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|행으로 테이블의 전체 내용을 검색합니다.|  
  
## <a name="remarks"></a>설명  
 그러나 `CXMLAccessor` 에서 다른 `CDynamicStringAccessorW` (태그 있음된) 데이터를 XML 형식으로 데이터 저장소에서 액세스 하는 모든 데이터를 변환 한다는 점에서 합니다. 출력 XML 인식 웹 페이지에 특히 유용합니다. XML 태그 이름은는 가능한 데이터 저장소의 열 이름과 일치 합니다.  
  
 사용 하 여 `CDynamicAccessor` 열 정보를 가져오는 방법입니다. 이 열 정보를 사용 하 여 접근자를 런타임에 동적으로 만듭니다.  
  
 열 정보는이 클래스에서 만들고 관리 하는 버퍼에 저장 됩니다. 사용 하 여 열 정보를 가져올 [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) 사용 하 여 행에서 열 데이터를 얻는 [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
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