---
title: ISpecifyPropertyPagesImpl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b54b8e4fdfbbfd282475ed0ca6e221d826953cad
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879574"
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl 클래스
이 클래스는 구현 `IUnknown` 의 기본 구현을 제공 합니다 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 클래스에서 파생 된 `ISpecifyPropertyPagesImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID의 배열 계산 값을 채웁니다. 각 UUID 개체의 속성 시트에 표시 될 수 있는 속성 페이지 중 하나에 대 한 CLSID에 해당 합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) 인터페이스를 사용 하면 클라이언트는 개체에서 지 원하는 속성 페이지에 대 한 Clsid 목록을 가져올 수 있습니다. 클래스 `ISpecifyPropertyPagesImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 `IUnknown` 장치에서 디버그 덤프에 정보를 전송 하 여 작성 합니다.  
  
> [!NOTE]
>  노출 하지 마십시오는 `ISpecifyPropertyPages` 개체 속성 페이지를 지원 하지 않는 경우 인터페이스.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 배열을 채웁니다 합니다 [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) 개체의 속성 시트에 표시 될 수 있는 속성 페이지에 대 한 clsid가 포함 된 구조입니다.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>설명  
 ATL 개체의 속성 맵에 사용 하 여 각 CLSID를 검색 합니다.  
  
 참조 [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) Windows SDK에에서 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyPageImpl 클래스](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
