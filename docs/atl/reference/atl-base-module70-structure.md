---
title: "_ATL_BASE_MODULE70 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
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
ms.sourcegitcommit: 347e7bf7cd9173fb2815f44fc052ec23ab4055a6
ms.openlocfilehash: 7456d441d7b3fb74f404f29c893c492feab10ed9
ms.lasthandoff: 02/24/2017

---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 구조
ATL.를 사용 하 여 모든 프로젝트에서 사용  
  
## <a name="syntax"></a>구문  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>멤버  
 `cbSize`  
 버전 관리에 사용 되는 구조체의 크기입니다.  
  
 `m_hInst`  
 **hInstance** 이 모듈 (exe 또는 dll)입니다.  
  
 `m_hInstResource`  
 기본 인스턴스 리소스 핸들입니다.  
  
 **m_bNT5orWin98**  
 운영 체제 버전 정보입니다. ATL.에서 내부적으로 사용  
  
 **dwAtlBuildVer**  
 ATL.의 버전을 저장 현재 0x0700 합니다.  
  
 **pguidVer**  
 ATL의 내부 GUID입니다.  
  
 **m_csResource**  
 에 대 한 액세스를 동기화 하는 데는 **m_rgResourceInstance** 배열입니다. ATL.에서 내부적으로 사용  
  
 **m_rgResourceInstance**  
 ATL 인식 되어 있는 모든 리소스 인스턴스에서 리소스를 검색 하는 데 사용 하는 배열입니다. ATL.에서 내부적으로 사용  
  
## <a name="remarks"></a>주의  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) 의 typedef로 정의 된 `_ATL_BASE_MODULE70`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체](../../atl/reference/atl-structures.md)






