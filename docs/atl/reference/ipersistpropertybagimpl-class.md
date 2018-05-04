---
title: IPersistPropertyBagImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41d26b84fd4c113120afefd572caed8ab27214c8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl 클래스
이 클래스는 구현 **IUnknown** 하 고 클라이언트에서 제공한 속성 모음에 해당 속성을 저장 하는 개체를 허용 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPersistPropertyBagImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|새로 만든된 개체를 초기화합니다. ATL 구현은 `S_OK`합니다.|  
|[IPersistPropertyBagImpl::Load](#load)|클라이언트에서 제공한 propertybag에서 해당 개체의 속성을 로드합니다.|  
|[IPersistPropertyBagImpl::Save](#save)|클라이언트에서 제공한 속성 모음에 해당 개체의 속성을 저장합니다.|  
  
## <a name="remarks"></a>설명  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) 인터페이스는 클라이언트에서 제공한 propertybag에 해당 속성을 저장 하는 개체를 사용 합니다. 클래스 `IPersistPropertyBagImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **IPersistPropertyBag** 와 함께 작동 [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) 및 [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)합니다. 클라이언트에서 두 번째 인터페이스를 구현 합니다. 통해 `IPropertyBag`, 클라이언트는 저장 및 해당 개체의 개별 속성을 로드 합니다. 통해 **IErrorLog**, 개체와 클라이언트 모두에서 발생 한 오류를 보고할 수 있습니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID  
 개체의 CLSID를 검색합니다.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>설명  
 참조 [:: Getclassid](http://msdn.microsoft.com/library/windows/desktop/ms688664) in the Windows SDK입니다.  
  
##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew  
 새로 만든된 개체를 초기화합니다.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) in the Windows SDK입니다.  
  
##  <a name="load"></a>  IPersistPropertyBagImpl::Load  
 클라이언트에서 제공한 propertybag에서 해당 개체의 속성을 로드합니다.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>설명  
 ATL 개체의 속성 매핑이 두를 사용 하 여이 정보를 검색 합니다.  
  
 참조 [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) in the Windows SDK입니다.  
  
##  <a name="save"></a>  IPersistPropertyBagImpl::Save  
 클라이언트에서 제공한 속성 모음에 해당 개체의 속성을 저장합니다.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>설명  
 ATL 개체의 속성 매핑이 두를 사용 하 여이 정보를 저장 합니다. 기본적으로이 메서드는 값에 관계 없이 모든 속성을 저장 *fSaveAllProperties*합니다.  
  
 참조 [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [클래스 개요](../../atl/atl-class-overview.md)
