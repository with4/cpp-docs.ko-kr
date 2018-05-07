---
title: 'Iopenrowsetimpl:: Openrowset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- OpenRowset method
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84bd34786dd87e92d70ad28d0f0a961cb01c1e48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iopenrowsetimplopenrowset"></a>IOpenRowsetImpl::OpenRowset
페이지를 열고 단일 기본 테이블 또는 인덱스에서 모든 행을 포함 하는 행 집합을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [iopenrowset:: Openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 ATLDB에서 찾을 수 없습니다. 8. 공급자를 만들 때 ATL 개체 마법사가 생성 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IOpenRowsetImpl 클래스](../../data/oledb/iopenrowsetimpl-class.md)