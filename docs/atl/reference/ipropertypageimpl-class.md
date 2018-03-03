---
title: "IPropertyPageImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbc62bd72ee5a639e8df0ada365cd7baac7d0c31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl 클래스
이 클래스는 구현 **IUnknown** 의 기본 구현을 제공 하 고는 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPropertyPageImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPropertyPageImpl::Activate](#activate)|속성 페이지에 대 한 대화 상자 창을 만듭니다.|  
|[IPropertyPageImpl::Apply](#apply)|현재 속성 페이지 값을 통해 지정 된 기본 개체에 적용 됩니다. `SetObjects`합니다. ATL 구현은 `S_OK`합니다.|  
|[IPropertyPageImpl::Deactivate](#deactivate)|창을 사용 하 여 만든 **Activate**합니다.|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|속성 페이지에 대 한 정보를 검색합니다.|  
|[IPropertyPageImpl::Help](#help)|속성 페이지에 대 한 Windows 도움말을 호출합니다.|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|속성 페이지를 활성화 된 후 변경 되었는지 여부를 나타냅니다.|  
|[IPropertyPageImpl::Move](#move)|배치 하 고 속성 페이지 대화 상자 크기를 조정 합니다.|  
|[IPropertyPageImpl::SetDirty](#setdirty)|속성 페이지의 상태 변경 또는 변경 되지 않은으로 플래그 지정합니다.|  
|[IPropertyPageImpl::SetObjects](#setobjects)|배열을 제공 **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다. 이러한 개체를 호출 하 여 현재 속성 페이지 값 수신 **적용**합니다.|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|제공 된 속성 페이지는 `IPropertyPageSite` 속성 페이지 속성 프레임와 통신 하는 포인터입니다.|  
|[IPropertyPageImpl::Show](#show)|표시 하거나 숨길 속성 페이지 대화 상자를 만듭니다.|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|지정 된 키 입력을 처리합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|속성 페이지의 상태가 변경 되었는지 여부를 지정 합니다.|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|속성 페이지를 설명 하는 텍스트 문자열로 연결 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|속성 페이지와 관련 된 도움말 항목에 대 한 컨텍스트 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|속성 페이지를 설명 하는 도움말 파일의 이름과 연결 된 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|속성 페이지에 대 한 탭에 표시 되는 텍스트 문자열로 연결 리소스 식별자를 저장 합니다.|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|속성 페이지와 관련 된 개체의 수를 저장 합니다.|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|가리키는 `IPropertyPageSite` 속성 페이지 속성 프레임와 통신 하는 인터페이스입니다.|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|배열을 가리키는 **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다.|  
|[IPropertyPageImpl::m_size](#m_size)|속성 페이지 대화 상자의 너비와 높이 (픽셀)에서로 저장합니다.|  
  
## <a name="remarks"></a>설명  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) 인터페이스 속성 시트 내에서 특정 속성 페이지를 관리 하는 개체를 사용 합니다. 클래스 `IPropertyPageImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 **IUnknown** 디버그에서 장치 정보 덤프를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="activate"></a>IPropertyPageImpl::Activate  
 속성 페이지에 대 한 대화 상자 창을 만듭니다.  
  
```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```  
  
### <a name="remarks"></a>설명  
 기본적으로 대화 상자는 항상 모덜리스의 값에 관계 없이 *bModal* 매개 변수입니다.  
  
 참조 [IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) in the Windows SDK입니다.  
  
##  <a name="apply"></a>IPropertyPageImpl::Apply  
 현재 속성 페이지 값을 통해 지정 된 기본 개체에 적용 됩니다. `SetObjects`합니다.  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) in the Windows SDK입니다.  
  
##  <a name="deactivate"></a>IPropertyPageImpl::Deactivate  
 대화 상자 창을 사용 하 여 만든 [Activate](#activate)합니다.  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) in the Windows SDK입니다.  
  
##  <a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo  
 채웁니다는 *pPageInfo* 데이터 멤버에 포함 된 정보로 구조체입니다.  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>설명  
 `GetPageInfo`와 연결 된 문자열 리소스를 로드 [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile), 및 [m_dwTitle](#m_dwtitle)합니다.  
  
 참조 [IPropertyPage::GetPageInfo](http://msdn.microsoft.com/library/windows/desktop/ms680714) in the Windows SDK입니다.  
  
##  <a name="help"></a>IPropertyPageImpl::Help  
 속성 페이지에 대 한 Windows 도움말을 호출합니다.  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) in the Windows SDK입니다.  
  
##  <a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl  
 생성자입니다.  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 초기화합니다.  
  
##  <a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty  
 속성 페이지를 활성화 된 후 변경 되었는지 여부를 나타냅니다.  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>설명  
 `IsPageDirty`반환 `S_OK` 페이지가 활성화 된 후 변경 하는 경우.  
  
##  <a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty  
 속성 페이지의 상태가 변경 되었는지 여부를 지정 합니다.  
  
```
BOOL m_bDirty;
```  
  
##  <a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects  
 속성 페이지와 관련 된 개체의 수를 저장 합니다.  
  
```
ULONG m_nObjects;
```  
  
##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext  
 속성 페이지와 관련 된 도움말 항목에 대 한 컨텍스트 식별자를 저장 합니다.  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString  
 속성 페이지를 설명 하는 텍스트 문자열로 연결 리소스 식별자를 저장 합니다.  
  
```
UINT m_dwDocString;
```  
  
##  <a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile  
 속성 페이지를 설명 하는 도움말 파일의 이름과 연결 된 리소스 식별자를 저장 합니다.  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle  
 속성 페이지에 대 한 탭에 표시 되는 텍스트 문자열로 연결 리소스 식별자를 저장 합니다.  
  
```
UINT m_dwTitle;
```  
  
##  <a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite  
 가리키는 [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) 속성 페이지 속성 프레임와 통신 하는 인터페이스입니다.  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk  
 배열을 가리키는 **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다.  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="m_size"></a>IPropertyPageImpl::m_size  
 속성 페이지 대화 상자의 너비와 높이 (픽셀)에서로 저장합니다.  
  
```
SIZE m_size;
```  
  
##  <a name="move"></a>IPropertyPageImpl::Move  
 배치 하 고 속성 페이지 대화 상자 크기를 조정 합니다.  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) in the Windows SDK입니다.  
  
##  <a name="setdirty"></a>IPropertyPageImpl::SetDirty  
 속성 페이지의 상태 변경 또는 값에 따라 변경 되지 않은으로 플래그 지정 `bDirty`합니다.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDirty`  
 [in] 경우 **TRUE**, 속성 페이지의 상태가 변경 된 것으로 표시 됩니다. 으로 표시 되어 있으면으로 변경 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 `SetDirty` 프레임 속성 페이지 변경 되었음을 알립니다.  
  
##  <a name="setobjects"></a>IPropertyPageImpl::SetObjects  
 배열을 제공 **IUnknown** 속성 페이지와 관련 된 개체에 대 한 포인터입니다.  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) in the Windows SDK입니다.  
  
##  <a name="setpagesite"></a>IPropertyPageImpl::SetPageSite  
 제공 된 속성 페이지는 [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) 속성 페이지 속성 프레임와 통신 하는 포인터입니다.  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) in the Windows SDK입니다.  
  
##  <a name="show"></a>IPropertyPageImpl::Show  
 표시 하거나 숨길 속성 페이지 대화 상자를 만듭니다.  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) in the Windows SDK입니다.  
  
##  <a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator  
 에 지정 된 키 입력을 처리 `pMsg`합니다.  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>설명  
 참조 [IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IPropertyPage2Impl 클래스](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl 클래스](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl 클래스](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
