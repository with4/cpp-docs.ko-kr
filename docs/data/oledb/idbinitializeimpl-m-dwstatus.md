---
title: 'Idbinitializeimpl:: M_dwstatus | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
dev_langs:
- C++
helpviewer_keywords:
- m_dwStatus
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 69c591b797908879f349945d49e6033763707592
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="idbinitializeimplmdwstatus"></a>IDBInitializeImpl::m_dwStatus
데이터 원본 플래그입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
DWORD m_dwStatus;  
  
```  
  
## <a name="remarks"></a>설명  
 이러한 플래그를 지정 하거나 데이터 원본 개체에 대 한 다양 한 특성의 상태를 나타냅니다. 다음 중 하나 이상 포함 `enum` 값:  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|**DSF_MASK_INIT**|초기화 되지 않은 상태로의 복원을 사용할 수 있도록 하는 마스크입니다.|  
|**DSF_PERSIST_DIRTY**|데이터 원본 개체 (즉, 경우 변경 내용이) 지 속성을 요구 하는 경우 설정 합니다.|  
|**DSF_INITIALIZED**|데이터 원본이 초기화 하는 경우 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IDBInitializeImpl 클래스](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)