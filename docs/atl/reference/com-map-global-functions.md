---
title: "전역 함수를 COM 맵 | Microsoft 문서"
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
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
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
ms.openlocfilehash: c37f722267107ad06fb51dc78bd682603161a476
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-global-functions"></a>Com 전역 함수
이러한 함수는 COM 맵에 대 한 지원을 제공 **IUnknown** 구현 합니다.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|에 위임 하는 **IUnknown** 집계 되지 않은 원시 개체입니다.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|인터페이스에 대 한 비교를 위한 효율적인 코드 생성 **IUnknown**합니다.|  

  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="a-nameatlinternalqueryinterfacea--atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pThis`  
 [in] 에 노출 된 인터페이스의 COM 맵을 포함 하는 개체에 대 한 포인터 `QueryInterface`합니다.  
  
 `pEntries`  
 [in] 배열을 **_ATL_INTMAP_ENTRY** 사용할 수 있는 인터페이스의 지도 액세스 하는 구조입니다.  
  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 에 지정 된 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 `AtlInternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체를 집계 하는 경우 `AtlInternalQueryInterface` 알 수 없는 외부를 위임 하지 않습니다. 인터페이스를 COM 맵 테이블에 매크로 입력할 수 있습니다 [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) 또는 해당 변형 중 하나입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&94;](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="a-nameinlineisequaliunknowna--inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 에 대 한 테스트의 특수 한 경우가이 함수 호출 **IUnknown**합니다.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>매개 변수  
 *rguid1*  
 [in] 비교할 GUID **IID_IUnknown**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [COM 맵 매크로](../../atl/reference/com-map-macros.md)

