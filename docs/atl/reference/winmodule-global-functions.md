---
title: "전역 함수 WinModule | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c477f4500bd4fe78f21f04c58b02d1b493f72c01
ms.lasthandoff: 02/24/2017

---
# <a name="winmodule-global-functions"></a>WinModule 전역 함수
이러한 함수에 대 한 지원을 제공 `_AtlCreateWndData` 작업을 구성 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.|  
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  `            
##  <a name="a-nameatlwinmoduleaddcreatewnddataa--atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData  
 이 함수는 `_AtlCreateWndData` 구조를 초기화하고 추가하는 데 사용됩니다.  
   
```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWinModule`  
 모듈의에 대 한 포인터 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조입니다.  
  
 `pData`  
 에 대 한 포인터는 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조를 초기화 하 고 현재 모듈에 추가 합니다.  
  
 `pObject`  
 개체의 포인터 **이** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 초기화는 `_AtlCreateWndData` 구조를 저장 하는 데 사용 되는 **이** 포인터가 클래스 인스턴스를 참조 하는 데 사용 하 고 모듈의 참조 목록에 추가 `_ATL_WIN_MODULE70` 구조입니다. 에 의해 호출 [CAtlWinModule::AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)합니다.  
  
##  <a name="a-nameatlwinmoduleextractcreatewnddataa--atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData  
 기존 `_AtlCreateWndData` 구조를 추출하려면 이 함수를 호출합니다.  
 
```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWinModule`  
 모듈의에 대 한 포인터 [_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 된 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md) 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 기존 추출 `_AtlCreateWndData` 모듈의 참조 목록에서 구조 `_ATL_WIN_MODULE70` 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

