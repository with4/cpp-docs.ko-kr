---
title: 'Irowsetupdateimpl:: Isupdateallowed | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4744e6f5be9c9b535c7359b615a5195c6da33fd9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
보안을 업데이트 하기 전에 등의 무결성을 확인 하려면이 메서드를 재정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *status*  
 [in] 보류 중인 행에는 작업의 상태입니다.  
  
 *hRowUpdate*  
 [in] 사용자가을 업데이트할 행에 대 한 핸들입니다.  
  
 *pRowStatus*  
 [out] 사용자에 게 반환 하는 상태입니다.  
  
## <a name="remarks"></a>설명  
 업데이트 수 있어야 함을 확인 한 경우 반환 `S_OK`; 그렇지 않으면 반환 **E_FAIL**합니다. 업데이트를 허용 하면도 설정 해야는 **DBROWSTATUS** 에 [irowsetupdateimpl:: Update](../../data/oledb/irowsetupdateimpl-update.md) 를 적절 한 [행 상태](https://msdn.microsoft.com/en-us/library/ms722752.aspx)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetUpdateImpl 클래스](../../data/oledb/irowsetupdateimpl-class.md)