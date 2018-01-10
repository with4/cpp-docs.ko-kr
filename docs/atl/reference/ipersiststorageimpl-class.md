---
title: "IPersistStorageImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
dev_langs: C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0bb02425c906a9d468d53691469dd7e418afcad3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl 클래스
이 클래스가 구현 하는 [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IPersistStorageImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|개체의 CLSID를 검색합니다.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|개체를 모든 저장소 개체를 해제 하 고 HandsOff 모드로 전환 하도록 지시 합니다. ATL 구현은 `S_OK`합니다.|  
|[IPersistStorageImpl::InitNew](#initnew)|새 저장소를 초기화합니다.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|개체의 데이터를 마지막으로 저장 후 변경 되었는지 여부를 확인 합니다.|  
|[IPersistStorageImpl::Load](#load)|지정된 된 저장소에서 해당 개체의 속성을 로드합니다.|  
|[IPersistStorageImpl::Save](#save)|개체의 속성을 지정된 된 저장소에 저장 합니다.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|해당 저장소 개체에 쓸 수 있는 표준 모드를 반환할 수 있는 개체를 알립니다. ATL 구현은 `S_OK`합니다.|  
  
## <a name="remarks"></a>설명  
 `IPersistStorageImpl`구현 하는 [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) 인터페이스, 개체 부하를 요청할 클라이언트 수 있는 하 고 자체 영구 데이터 저장소를 사용 하 여 저장 합니다.  
  
 이 클래스의 구현에 클래스 필요 `T` 의 구현할 수 있도록는 `IPersistStreamInit` 를 통해 사용할 수 있는 인터페이스 `QueryInterface`합니다. 해당 클래스 즉, 일반적으로 `T` 에서 파생 되어야 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)에 대 한 항목이 제공 `IPersistStreamInit` 에 [COM 맵](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333), 사용 및는 [속성 매핑이 두](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) 를 클래스의 영구 데이터에 설명 합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistStorageImpl::GetClassID  
 개체의 CLSID를 검색합니다.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>설명  
 참조 [:: Getclassid](http://msdn.microsoft.com/library/windows/desktop/ms688664) in the Windows SDK입니다.  
  
##  <a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage  
 개체를 모든 저장소 개체를 해제 하 고 HandsOff 모드로 전환 하도록 지시 합니다.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) in the Windows SDK입니다.  
  
##  <a name="initnew"></a>IPersistStorageImpl::InitNew  
 새 저장소를 초기화합니다.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>설명  
 ATL 구현에 위임 된 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) 인터페이스입니다.  
  
 참조 [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) in the Windows SDK입니다.  
  
##  <a name="isdirty"></a>IPersistStorageImpl::IsDirty  
 개체의 데이터를 마지막으로 저장 후 변경 되었는지 여부를 확인 합니다.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>설명  
 ATL 구현에 위임 된 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) 인터페이스입니다.  
  
 참조 [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) in the Windows SDK입니다.  
  
##  <a name="load"></a>IPersistStorageImpl::Load  
 지정된 된 저장소에서 해당 개체의 속성을 로드합니다.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>설명  
 ATL 구현에 위임 된 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) 인터페이스입니다. **부하** "콘텐츠" 라는 스트림을 사용 하 여 개체의 데이터를 검색 합니다. [저장](#save) 메서드는 원래이 스트림을 만듭니다.  
  
 참조 [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) in the Windows SDK입니다.  
  
##  <a name="save"></a>IPersistStorageImpl::Save  
 개체의 속성을 지정된 된 저장소에 저장 합니다.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>설명  
 ATL 구현에 위임 된 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) 인터페이스입니다. 때 **저장** 첫 번째는 지정 된 저장소에서 "콘텐츠" 이라는 스트림을 만듭니다를 호출 합니다. 이 스트림은 이후 호출에 사용 되는 다음 **저장** 호출 [부하](#load)합니다.  
  
 참조 [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) in the Windows SDK입니다.  
  
##  <a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted  
 해당 저장소 개체에 쓸 수 있는 표준 모드를 반환할 수 있는 개체를 알립니다.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 참조 [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) in the Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [저장소 및 스트림을](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl 클래스](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl 클래스](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
