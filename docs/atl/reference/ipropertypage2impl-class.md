---
title: "IPropertyPage2Impl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17773bdd07d4ae25b33bc104d46d607b5069f78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl 클래스
이 클래스는 구현 **IUnknown** 의 기본 구현을 상속 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPropertyPage2Impl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|속성 컨트롤에서 속성 페이지를 활성화할 때 포커스를 수신 하도록 지정 합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>설명  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) 확장 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 추가 하 여는 `EditProperty` 메서드. 이 메서드는 클라이언트가 속성 페이지 개체에서 특정 속성을 선택 하는 데 사용 합니다.  
  
 클래스 `IPropertyPage2Impl` 단순히 반환 **E_NOTIMPL** 에 대 한 **IPropertyPage2::EditProperty**합니다. 하지만 기본 구현을 상속 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 클래스에서 파생 된 일반적으로 속성 페이지를 만들 때 `IPropertyPageImpl`합니다. 추가 지원을 제공 하기 위해 **IPropertyPage2**, 클래스 정의 수정 하 고 재정의 `EditProperty` 메서드.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 속성 컨트롤에서 속성 페이지를 활성화할 때 포커스를 수신 하도록 지정 합니다.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
