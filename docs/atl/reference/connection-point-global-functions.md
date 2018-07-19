---
title: 연결 지점 전역 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b85da5991357f1b67c6d2249d854e6084ee48c23
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884063"
---
# <a name="connection-point-global-functions"></a>연결 지점 전역 함수
이러한 함수는 연결 지점에 대 한 지원을 제공 하 고 maps 싱크 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|개체의 연결 지점과 클라이언트의 싱크 간에 연결을 만듭니다.|  
|[AtlUnadvise](#atlunadvise)|통해 설정 된 연결을 종료 `AtlAdvise`합니다.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|제안 또는 항목에서 이벤트 싱크 맵과 unadvises 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
   
##  <a name="atladvise"></a>  AtlAdvise  
 개체의 연결 지점과 클라이언트의 싱크 간에 연결을 만듭니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkCP*  
 [in] 에 대 한 포인터를 `IUnknown` 개체의 클라이언트가 연결 하려고 합니다.  
  
 *pUnk*  
 [in] 클라이언트에 대 한 포인터 `IUnknown`합니다.  
  
 *iid*  
 [in] 연결 지점의 GUID입니다. 일반적으로 이것이 연결 지점에서 관리 되는 송신 인터페이스와 동일 합니다.  
  
 *pdw*  
 [out] 연결을 고유 하 게 식별 하는 쿠키에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 싱크는 연결점은에서 지원 되는 송신 인터페이스를 구현 합니다. 클라이언트가 사용 하는 *pdw* 전달 하 여 연결을 제거 하는 쿠키 [AtlUnadvise](#atlunadvise)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>  AtlUnadvise  
 통해 설정 된 연결을 종료 [AtlAdvise](#atladvise)합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkCP*  
 [in] 에 대 한 포인터를 `IUnknown` 클라이언트와 연결 된 개체입니다.  
  
 *iid*  
 [in] 연결 지점의 GUID입니다. 일반적으로 이것이 연결 지점에서 관리 되는 송신 인터페이스와 동일 합니다.  
  
 *dw*  
 [in] 연결을 고유 하 게 식별 하는 쿠키입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap  
 개체의 싱크 이벤트 맵에서 모든 항목을 advise하거나 unadvise하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>매개 변수  
 *(태평양 표준시)*  
 [in] 싱크 맵이 포함 된 개체에 대 한 포인터입니다.  
  
 *bAdvise*  
 [in] 모든 경우에 TRUE 싱크 항목이 알림을 받을 수 있습니다. 권장 되지 싱크 항목이 모든 경우에 FALSE입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [연결 지점 매크로](../../atl/reference/connection-point-macros.md)
