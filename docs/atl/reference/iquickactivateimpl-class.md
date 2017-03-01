---
title: "IQuickActivateImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IQuickActivateImpl
- ATL::IQuickActivateImpl<T>
- ATL.IQuickActivateImpl
- ATL.IQuickActivateImpl<T>
- IQuickActivateImpl
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4f6b75da64efa12e43fa160c57da4291acae03ca
ms.lasthandoff: 02/24/2017

---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl 클래스
이 클래스는 컨테이너의 컨트롤 초기화를 단일 호출으로 결합합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IQuickActivateImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|실행 중인 컨트롤에 대 한 현재 화면 크기를 검색합니다.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|로드 되 고 컨트롤의 빠른 초기화를 수행 합니다.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|컨테이너에 할당 된 디스플레이 공간의 양을 컨트롤을 알립니다.|  
  
## <a name="remarks"></a>주의  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) 인터페이스 초기화 한 번의 호출을 결합 하 여 컨트롤을 로드할 때 지연 되지 않도록 하는 컨테이너는 데 도움이 됩니다. `QuickActivate` 메서드를 사용 하면 컨테이너에 대 한 포인터를 전달 하는 [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) 컨트롤의 모든 인터페이스에 대 한 포인터를 보유 하는 구조 필요 합니다. 반환 시 컨트롤 다시 전달에 대 한 포인터는 [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) 컨테이너에서 사용 되는 자체 인터페이스에 대 한 포인터를 보유 하는 구조입니다. 클래스 `IQuickActivateImpl` 의 기본 구현을 제공 **IQuickActivate** 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="a-namegetcontentextenta--iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 실행 중인 컨트롤에 대 한 현재 화면 크기를 검색합니다.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>주의  
 크기는 컨트롤의 전체 렌더링 되며 HIMETRIC 단위에 지정 됩니다.  
  
 참조 [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namequickactivatea--iquickactivateimplquickactivate"></a><a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 로드 되 고 컨트롤의 빠른 초기화를 수행 합니다.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>주의  
 구조는 일부 앰비언트 속성의 값과 컨트롤에 필요한 인터페이스에 대 한 포인터를 포함 합니다. 반환 시 컨트롤에 대 한 포인터를 전달 된 [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) 컨테이너에서 필요로 하는 고유한 인터페이스와 추가 상태 정보에 대 한 포인터를 포함 하는 구조입니다.  
  
 참조 [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetcontentextenta--iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 컨테이너에 할당 된 디스플레이 공간의 양을 컨트롤을 알립니다.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>주의  
 HIMETRIC 단위에서 크기 지정 됩니다.  
  
 참조 [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

