---
title: "_ATL_MODULE70 구조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a759306e4218d36f2a4d250209f67b1d181c483
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70 구조
모든 ATL 모듈에 의해 사용 되는 데이터를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>멤버  
 `cbSize`  
 버전 관리에 사용 되는 구조체의 크기입니다.  
  
 `m_nLockCnt`  
 모듈을 활성 상태로 남아 해야 기간 결정 하기 위한 참조 횟수입니다.  
  
 **m_pTermFuncs**  
 ATL 종료 될 때 호출 될에 등록 된 트랙 함수입니다.  
  
 **m_csStaticDataInitAndTypeInfo**  
 다중 스레드 상황에서 내부 데이터에 대 한 액세스를 조정 하는 데 사용 합니다.  
  
## <a name="remarks"></a>설명  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) 의 typedef로 정의 된 `_ATL_MODULE70`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체](../../atl/reference/atl-structures.md)







