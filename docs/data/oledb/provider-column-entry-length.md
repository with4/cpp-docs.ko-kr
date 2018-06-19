---
title: PROVIDER_COLUMN_ENTRY_LENGTH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_LENGTH macro
ms.assetid: b4a67246-c049-4622-bb65-242cc8cae4be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2aaf2532bc63170940a3526bc34c0763ed0a4aa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106325"
---
# <a name="providercolumnentrylength"></a>PROVIDER_COLUMN_ENTRY_LENGTH
공급자에서 지 원하는 특정 열을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
PROVIDER_COLUMN_ENTRY_LENGTH(name  
, ordinal, size, member )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
 [in] 열 이름입니다.  
  
 `ordinal`  
 [in] 열 번호입니다. 열이 책갈피 열, 하지 않는 한 열 번호는 0 아니어야 합니다.  
  
 `size`  
 [in] 열 크기 (바이트)입니다.  
  
 `member`  
 [in] 멤버 변수 `dataClass` 열 데이터를 저장 하는 합니다.  
  
## <a name="remarks"></a>설명  
 열 크기를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 참조 [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)