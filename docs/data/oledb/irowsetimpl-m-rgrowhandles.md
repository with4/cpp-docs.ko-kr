---
title: 'Irowsetimpl:: M_rgrowhandles | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs:
- C++
helpviewer_keywords:
- m_rgRowHandles
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f97536a5ce984004bf7009584de679d19520a9f1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplmrgrowhandles"></a>IRowsetImpl::m_rgRowHandles
현재 공급자에 대 한 응답에서에 포함 된 행 핸들의 지도 `GetNextRows`합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
MapClass  
 m_rgRowHandles;  
  
```  
  
## <a name="remarks"></a>설명  
 행 핸들은 호출 하 여 제거 `ReleaseRows`합니다. 참조는 [IRowsetImpl 개요](../../data/oledb/irowsetimpl-class.md) 의 정의 대 한 *MapClass*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)