---
title: PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_GN
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_GN macro
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: be0cfa80b0d2a18d04dd329feda6547b5d89e6e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109978"
---
# <a name="providercolumnentrygn"></a>PROVIDER_COLUMN_ENTRY_GN
공급자에서 지 원하는 특정 열을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
 [in] 열 이름입니다.  
  
 `ordinal`  
 [in] 열 번호입니다. 열이 책갈피 열, 하지 않는 한 열 번호는 0 아니어야 합니다.  
  
 `flags`  
 [in] 데이터 반환 되는 방법을 지정 합니다. 참조는 `dwFlags` 에 설명을 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)합니다.  
  
 *colSize*  
 [in] 열 크기입니다.  
  
 `dbtype`  
 [in] 값의 데이터 형식을 나타냅니다. 참조는 **wType** 에 설명을 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)합니다.  
  
 *precision*  
 [in] 사용할 경우 데이터를 가져올 때 전체 자릿수를 나타내는 *dbType* 은 `DBTYPE_NUMERIC` 또는 **DBTYPE_DECIMAL**합니다. 참조는 **bPrecision** 에 설명을 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)합니다.  
  
 `scale`  
 [in] DbType이 데이터를 가져올 때 사용할 소수 자릿수를 나타냅니다 `DBTYPE_NUMERIC` 또는 **DBTYPE_DECIMAL**합니다. 참조는 **bScale** 에 설명을 [DBBINDING 구조](https://msdn.microsoft.com/en-us/library/ms716845.aspx)합니다.  
  
 `guid`  
 스키마 행 집합 GUID입니다. 참조 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) 에 *OLE DB Programmer's Reference* 스키마 행 집합 및 Guid 목록에 대 한 합니다.  
  
## <a name="remarks"></a>설명  
 열의 크기, 데이터 형식, 정밀도, 배율 및 스키마 행 집합 GUID 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)