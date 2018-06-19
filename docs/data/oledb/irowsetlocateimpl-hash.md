---
title: 'Irowsetlocateimpl:: Hash | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
dev_langs:
- C++
helpviewer_keywords:
- Hash method
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 42076453cc8f32b56bfe354eaa2b883650d0f4f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101190"
---
# <a name="irowsetlocateimplhash"></a>IRowsetLocateImpl::Hash
지정 된 책갈피에 대 한 값을 해시 하는 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
      STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hReserved`  
 [in] 에 해당 `hChapter` 매개 변수를 [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)합니다.  
  
 다른 매개 변수를 참조 하십시오. [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)