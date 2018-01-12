---
title: "CDynamicAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
dev_langs: C++
helpviewer_keywords: CDynamicAccessor class
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f88c3eff9c8160a0e322c93dacf6985dc7b8a20b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor 클래스
데이터베이스 스키마(데이터베이스의 내부 구조)에 대해 모를 때 데이터 소스에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDynamicAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cdynamicaccessor-addbindentry.md)|기본 접근자를 재정의 하는 경우 출력 열에 바인딩 항목을 추가 합니다.|  
|[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)|인스턴스화하고 초기화는 `CDynamicAccessor` 개체입니다.|  
|[닫기](../../data/oledb/cdynamicaccessor-close.md)|모든 열을 바인딩 해제, 할당된 된 메모리를 해제 하 고 해제는 [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) 클래스에 인터페이스 포인터입니다.|  
|[GetBookmark](../../data/oledb/cdynamicaccessor-getbookmark.md)|현재 행에 대 한 책갈피를 검색합니다.|  
|[GetBlobHandling](../../data/oledb/cdynamicaccessor-getblobhandling.md)|현재 행에 대 한 값을 처리 하는 BLOB를 검색 합니다.|  
|[GetBlobSizeLimit](../../data/oledb/cdynamicaccessor-getblobsizelimit.md)|최대 BLOB 크기 (바이트) 검색합니다.|  
|[GetColumnCount](../../data/oledb/cdynamicaccessor-getcolumncount.md)|행 집합의 열 수를 검색 합니다.|  
|[GetColumnFlags](../../data/oledb/cdynamicaccessor-getcolumnflags.md)|열 특징을 검색합니다.|  
|[GetColumnInfo](../../data/oledb/cdynamicaccessor-getcolumninfo.md)|열 메타 데이터를 검색합니다.|  
|[GetColumnName](../../data/oledb/cdynamicaccessor-getcolumnname.md)|지정 된 열의 이름을 검색합니다.|  
|[GetColumnType](../../data/oledb/cdynamicaccessor-getcolumntype.md)|지정 된 열의 데이터 형식을 검색합니다.|  
|[GetLength](../../data/oledb/cdynamicaccessor-getlength.md)|바이트에 있는 열의 최대 허용 길이 검색합니다.|  
|[GetOrdinal](../../data/oledb/cdynamicaccessor-getordinal.md)|열 이름이 지정 된 열 인덱스를 검색 합니다.|  
|[GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)|지정 된 열의 상태를 검색합니다.|  
|[GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)|버퍼에서 데이터를 검색 합니다.|  
|[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)|현재 행에 대 한 값을 처리 하는 BLOB를 설정 합니다.|  
|[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)|최대 BLOB 크기를 바이트 단위로 설정 합니다.|  
|[SetLength](../../data/oledb/cdynamicaccessor-setlength.md)|열의 길이 바이트 단위로 설정 합니다.|  
|[SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)|지정 된 열의 상태를 설정합니다.|  
|[SetValue](../../data/oledb/cdynamicaccessor-setvalue.md)|버퍼에 데이터를 저장합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 `CDynamicAccessor` 열 이름, 열 수, 데이터 형식 등의 열 정보를 가져오는 방법입니다. 그런 다음 실행 시 접근자를 동적으로 만들려면이 열 정보를 사용 합니다.  
  
 열 정보를 만들고이 클래스에서 관리 하는 버퍼에 저장 됩니다. 사용 하 여 버퍼에서 데이터를 가져올 [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)합니다.  
  
 에 대 한 설명 및 동적 접근자 클래스 사용 예제를 참조 하세요. [동적 접근자 사용](../../data/oledb/using-dynamic-accessors.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더**: atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)