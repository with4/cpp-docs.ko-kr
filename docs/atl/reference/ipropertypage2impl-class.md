---
title: "IPropertyPage2Impl 클래스 | Microsoft 문서"
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 43680d12febbd94137009f66242198129d4b3630
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl 클래스
이 클래스는 구현 **IUnknown** 의 기본 구현을 상속 하 고 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
|[IPropertyPage2Impl::EditProperty](#editproperty)|속성 페이지를 활성화할 때 어떤 속성 컨트롤에서 포커스를 받을지 지정 합니다. ATL 구현은 **E_NOTIMPL**합니다.|  
  
## <a name="remarks"></a>주의  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) 인터페이스를 확장 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 추가 하 여는 `EditProperty` 메서드. 이 메서드는 클라이언트가 속성 페이지 개체에서 특정 속성을 선택 하는 데 사용 합니다.  
  
 클래스 `IPropertyPage2Impl` 반환 **E_NOTIMPL** 에 대 한 **IPropertyPage2::EditProperty**합니다. 하지만 기본 구현 상속 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 클래스에서 파생 된 일반적으로 속성 페이지를 만들 때 `IPropertyPageImpl`합니다. 추가 지원을 제공 하기 위해 **IPropertyPage2**, 클래스 정의 수정 하 고 재정의 `EditProperty` 메서드.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 속성 페이지를 활성화할 때 어떤 속성 컨트롤에서 포커스를 받을지 지정 합니다.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

