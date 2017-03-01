---
title: "_ATL_WIN_MODULE70 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 383384c8f08b98592f92b5d38850137c1c0c6d54
ms.lasthandoff: 02/24/2017

---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 구조
기간 이동 코드 ATL.에 의해 사용 되는  
  
## <a name="syntax"></a>구문  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>멤버  
 `cbSize`  
 버전 관리에 사용 되는 구조체의 크기입니다.  
  
 `m_csWindowCreate`  
 등록 코드 창에 대 한 액세스를 serialize 하는 데 사용 합니다. ATL.에서 내부적으로 사용  
  
 **m_pCreateWndList**  
 해당 개체에 windows를 바인딩하는 데 사용 합니다. ATL.에서 내부적으로 사용  
  
 **m_rgWindowClassAtoms**  
 종료 시 제대로 등록 되지 될 수 있도록 창 클래스 등록을 추적 하는 데 사용 합니다. ATL.에서 내부적으로 사용  
  
## <a name="remarks"></a>주의  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) 의 typedef 정의 `_ATL_WIN_MODULE70`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체](../../atl/reference/atl-structures.md)






