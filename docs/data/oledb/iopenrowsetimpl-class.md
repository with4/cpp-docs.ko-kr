---
title: "IOpenRowsetImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67f457b4a56d57f33a18473e987fa00b6c10b0df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl 클래스
에 대 한 구현을 제공는 `IOpenRowset` 인터페이스입니다.  
  
## <a name="syntax"></a>구문

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>매개 변수  
 `SessionClass`  
 파생 된 클래스에 `IOpenRowsetImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|행 집합 개체를 만듭니다. 사용자가 직접 호출 되지 않습니다.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|페이지를 열고 단일 기본 테이블 또는 인덱스에서 모든 행을 포함 하는 행 집합을 반환 합니다. (ATLDB에 없음. H)|  
  
## <a name="remarks"></a>설명  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) 인터페이스는 세션 개체에 대 한 필수입니다. 열리고 단일 기본 테이블 또는 인덱스에서 모든 행을 포함 하는 행 집합을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)