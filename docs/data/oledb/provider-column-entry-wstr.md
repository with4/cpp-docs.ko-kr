---
title: PROVIDER_COLUMN_ENTRY_WSTR | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_WSTR
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_WSTR macro
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: faa6630d8821065d056e922dbf4790265d2497f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104076"
---
# <a name="providercolumnentrywstr"></a>PROVIDER_COLUMN_ENTRY_WSTR
공급자에서 지 원하는 특정 열을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
PROVIDER_COLUMN_ENTRY_WSTR(name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
 [in] 열 이름입니다.  
  
 `ordinal`  
 [in] 열 번호입니다. 열이 책갈피 열, 하지 않는 한 열 번호는 0 아니어야 합니다.  
  
 `member`  
 [in] 데이터를 저장 하는 데이터 클래스의 멤버 변수입니다.  
  
## <a name="remarks"></a>설명  
 열 데이터가 null 종료 유니코드 문자열 데이터 인 경우이 매크로 사용 하 여 [DBTYPE_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)