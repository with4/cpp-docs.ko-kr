---
title: 'Irowsetlocateimpl:: Compare | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9eaa0aaecd1ff30e51416aaaccebcc8fe6746222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
두 개의 책갈피를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="remarks"></a>설명  
 중 하나는 책갈피 표준 수 OLE DB에서 정의 된 [표준 책갈피](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST**, **DBBMK_LAST**, 또는 **DBBMK_INVALID**) 합니다. 반환 된 값 `pComparison` 두 책갈피 간의 관계를 나타냅니다.  
  
-   **DBCOMPARE_LT** (`cbBookmark1` 앞 `cbBookmark2`.)  
  
-   **DBCOMPARE_EQ** (`cbBookmark1` 같으면 `cbBookmark2`.)  
  
-   **DBCOMPARE_GT** (`cbBookmark1` 후 `cbBookmark2`.)  
  
-   **DBCOMPARE_NE** (책갈피는 같음 및 정렬 되지 않습니다.)  
  
-   **DBCOMPARE_NOTCOMPARABLE** (책갈피를 비교할 수 없습니다.)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetLocateImpl 클래스](../../data/oledb/irowsetlocateimpl-class.md)