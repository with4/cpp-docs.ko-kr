---
title: "ISpecifyPropertyPagesImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4d5f74de2ec6569527221cf94df6f7921f4bb4c9
ms.lasthandoff: 02/24/2017

---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl 클래스
이 클래스는 구현 **IUnknown** 의 기본 구현을 제공 하 고는 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `ISpecifyPropertyPagesImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID 배열 계산 값을 채웁니다. 각 UUID 개체의 속성 시트에 표시 될 수 있는 속성 페이지 중 하나에 대 한 CLSID에 해당 합니다.|  
  
## <a name="remarks"></a>주의  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) 인터페이스는 클라이언트 개체에 의해 지원 되는 속성 페이지에 대 한 Clsid의 목록을 가져올 수 있습니다. 클래스 `ISpecifyPropertyPagesImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
> [!NOTE]
>  노출 하지 마십시오.는 **ISpecifyPropertyPages** 개체 속성 페이지를 지원 하지 않는 경우 인터페이스입니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages  
 배열을 채우는 [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) 개체의 속성 시트에 표시 될 수 있는 속성 페이지에 대 한 clsid가 포함 된 구조입니다.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>주의  
 ATL 개체의 속성 매핑이 사용 하 여 각 CLSID를 검색 합니다.  
  
 참조 [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

