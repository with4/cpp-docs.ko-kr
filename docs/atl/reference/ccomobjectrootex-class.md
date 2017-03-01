---
title: "CComObjectRootEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComObjectRootEx
- ATL::CComObjectRootEx<ThreadModel>
- CComObjectRootEx
- ATL::CComObjectRootEx
- ATL.CComObjectRootEx<ThreadModel>
dev_langs:
- C++
helpviewer_keywords:
- reference counting
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
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
ms.openlocfilehash: f3a6d26ddb4f612824f959ca3046531dc3bbf2a9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx 클래스
이 클래스는 집계 및 집계 된 개체에 대 한 개체 참조 개수 관리를 처리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>매개 변수  
 `ThreadModel`  
 필요한 스레딩 모델을 구현 하는 메서드는 클래스입니다. 스레딩 모델을 설정 하 여 명시적으로 선택할 수 있습니다 `ThreadModel` 를 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), 또는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)합니다. 서버의 기본 스레드 모델을 설정 하 여 그대로 `ThreadModel` 를 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)합니다.  

  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|생성자입니다.|  
|[InternalAddRef](#internaladdref)|집계 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[InternalRelease](#internalrelease)|집계 개체에 대 한 참조 횟수를 감소 시킵니다.|  
|[잠금](#lock)|스레드 모델 이면 다중 스레드 임계 영역 개체의 소유권을 가져오면 됩니다.|  
|[잠금 해제](#unlock)|스레드 모델은 다중 스레드, 임계 영역 개체의 소유권을 해제 합니다.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase 메서드  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|개체에 필요한 초기화를 수행 하려면 클래스에서 재정의 합니다.|  
|[FinalRelease](#finalrelease)|개체에 필요한 정리를 수행 하려면 클래스에서 재정의 합니다.|  
|[OuterAddRef](#outeraddref)|집계 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[OuterQueryInterface](#outerqueryinterface)|대리자에는 외부 **IUnknown** 집합체입니다.|  
|[OuterRelease](#outerrelease)|집계 개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
### <a name="static-functions"></a>정적 함수  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|에 위임 하는 **IUnknown** 집계 되지 않은 원시 개체입니다.|  
|[ObjectMain](#objectmain)|모듈을 초기화 및 개체 맵의에 나열 된 파생된 클래스에 대 한 종료 하는 동안 호출 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|와 `m_pOuterUnknown`, 공용 구조체의 일부입니다. 개체의 참조 횟수를 보관 하는 집계 되지 않은 경우 사용 `AddRef` 및 **릴리스**합니다.|  
|[m_pOuterUnknown](#m_pouterunknown)|와 `m_dwRef`, 공용 구조체의 일부입니다. 알 수 없는 외부에 대 한 포인터를 보유 하는 개체 집계 되는 경우 사용 합니다.|  
  
## <a name="remarks"></a>주의  
 `CComObjectRootEx`집계 및 집계 된 개체에 대 한 개체 참조 개수 관리를 처리합니다. 개체가 집계 되는 개체를 집계 하는 경우 알 수 없는 외부에 포인터를 보유 하는 경우 개체 참조 횟수를 보유 합니다. 집계 개체에 대 한 `CComObjectRootEx` 메서드는 내부 개체를 생성 하는 오류 처리를 사용할 수 있습니다 하 고 내부 인터페이스 릴리스될 때 삭제 되지 않도록에서 외부 개체 또는 내부 개체를 보호 하기 위해 삭제 됩니다.  
  
 COM 서버를 구현 하는 클래스에서 상속 해야 `CComObjectRootEx` 또는 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)합니다.  
  
 클래스 정의 지정 하는 경우는 [DECLARE_POLY_AGGREGATABLE](http://msdn.microsoft.com/library/7569e738-cfbc-4404-ba1d-78dcefa3bdb3) ATL 매크로의 인스턴스를 만들고 **CComPolyObject\<CYourClass >** 때 **IClassFactory::CreateInstance** 호출 됩니다. 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 있으면 **NULL**, **IUnknown** 집계 개체에 대 한 구현 됩니다. 알 수 없는 외부 없으면 **NULL**, **IUnknown** 집계 개체에 대해 구현 됩니다.  
  
 클래스를 지정 하지 않은 경우는 `DECLARE_POLY_AGGREGATABLE` ATL 매크로의 인스턴스를 만들고 **CAggComObject\<CYourClass >** 인스턴스 또는 집계 된 개체에 대 한 **CComObject\<CYourClass >** 집계 개체에 대 한 합니다.  
  
 사용 `CComPolyObject` 모두 가진 벗어날 `CComAggObject` 및 `CComObject` 집계 및 집계 되지 않은 원시 사례를 처리 하 여 모듈에 있습니다. 단일 `CComPolyObject` 개체에는 두 경우 모두 처리 합니다. 따라서 vtable의 복사본이 한 개만 및 함수 중 하나의 모듈에 존재 합니다. Vtable 큰 경우 모듈 크기가 상당히 줄어들 수 있습니다이 있습니다. 그러나 vtable 작을 경우 사용 하 여 `CComPolyObject` 집계 되거나 집계 개체에 대해 최적화 되어 있지 않으므로 약간 더 큰 모듈 크기 될 수는 `CComAggObject` 및 `CComObject`.  
  
 개체를 집계 하는 경우 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 구현한 `CComAggObject` 또는 `CComPolyObject`합니다. 이러한 클래스에 위임 `QueryInterface`, `AddRef`, 및 **릴리스** 에 대 한 호출이 `CComObjectRootEx`의 `OuterQueryInterface`, `OuterAddRef`, 및 `OuterRelease` 를 알 수 없는 외부에 전달 합니다. 재정의 하는 일반적으로 `CComObjectRootEx::FinalConstruct` 집계 된 모든 개체를 만들고 재정의 하려면 클래스에서 `CComObjectRootEx::FinalRelease` 를 해제 하려면 개체를 집계 합니다.  
  
 개체가 집계 되지 않은 경우 **IUnknown** 구현한 `CComObject` 또는 `CComPolyObject`합니다. 이 경우에 대 한 호출이 `QueryInterface`, `AddRef`, 및 **릴리스** 에 위임 되며 `CComObjectRootEx`의 `InternalQueryInterface`, `InternalAddRef`, 및 `InternalRelease` 실제 작업을 수행 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-nameccomobjectrootexa--ccomobjectrootexccomobjectrootex"></a><a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 생성자는 참조 개수를 0으로 초기화합니다.  
  
```
CComObjectRootEx();
```  
  
##  <a name="a-namefinalconstructa--ccomobjectrootexfinalconstruct"></a><a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 개체에 필요한 초기화를 수행 하려면 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>반환 값  
 반환할 `S_OK` 성공 또는 표준 오류 중 하나에서 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 `CComObjectRootEx::FinalConstruct` 반환 `S_OK`합니다.  
  
 초기화를 수행 하 여 `FinalConstruct` 클래스의 생성자를 대신 합니다.  
  
-   경우에 생성자에서 상태 코드를 반환할 수 없습니다 되었지만 반환할 수는 `HRESULT` 방법으로 `FinalConstruct`의 값을 반환 합니다. 클래스 개체를 ATL에서 제공 하는 표준 클래스 팩터리를 사용 하 여 생성 되는 자세한 오류 정보를 제공 하는 수 있도록 COM 클라이언트에 다시 반환 값이 전파 됩니다.  
  
-   클래스의 생성자에서 가상 함수 메커니즘을 통해 가상 함수를 호출할 수 없습니다. 상속 계층 구조에서 해당 지점에서 정의 된 대로 정적으로 확인 된 함수 호출에서 결과 클래스의 생성자에서 가상 함수를 호출 합니다. 순수 가상 함수에 대 한 호출 링커 오류가 발생합니다.  
  
     클래스 상속 계층 구조에서 가장 많이 파생 된 클래스가 아닙니다. 등의 일부 기능이 제공 하는 ATL에서 제공 하는 파생된 클래스에 의존 합니다. 프로그램 초기화 됩니다 (이것은 분명 사실 클래스 개체를 다른 개체를 집계 해야 하는 경우) 해당 클래스를 제공 하는 기능을 사용 해야 하는 경우일 있지만 클래스의 생성자는 이러한 기능에 액세스할 수 없습니다. 클래스에 대 한 생성 코드는 완전히 가장 많이 파생 된 클래스를 생성 하기 전에 실행 됩니다.  
  
     그러나 `FinalConstruct` 후 가장 많이 파생 된 클래스 완전히 생성 된 가상 함수를 호출 하 고 ATL.에서 제공 하는 참조 카운팅 구현을 사용 하 여 수 있도록 하는 즉시 호출 됩니다  
  
### <a name="example"></a>예제  
 파생 된 클래스에서이 메서드를 재정의 하는 일반적으로 `CComObjectRootEx` 만들 개체를 집계 합니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#40;](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 생성 실패 하면 오류를 반환할 수 있습니다. 매크로 사용할 수도 있습니다 [DECLARE_PROTECT_FINAL_CONSTRUCT](http://msdn.microsoft.com/library/2d2e5ddc-057a-43ca-87c8-d3477a8193a0) 외부 개체를에서 보호 하기 위해,를 만드는 동안 집계 된 내부 개체를 증가 시키는 경우 참조 횟수 후 감소 개수를 0으로 삭제 합니다.  
  
 집계를 만들 하는 일반적인 방법은 다음과 같습니다.  
  
-   추가 **IUnknown** 클래스에 대 한 포인터 개체를 초기화 하도록 **NULL** 생성자에 있습니다.  
  
-   재정의 `FinalConstruct` 집계를 만들려고 합니다.  
  
-   사용 하는 **IUnknown** 에 대 한 매개 변수로 정의 된 포인터는 [COM_INTERFACE_ENTRY_AGGREGATE](http://msdn.microsoft.com/library/c671fa40-a57b-4797-ae88-c9762dabd4dc) 매크로입니다.  
  
-   재정의 `FinalRelease` 해제 하는 **IUnknown** 포인터입니다.  
  
##  <a name="a-namefinalreleasea--ccomobjectrootexfinalrelease"></a><a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 개체에 필요한 정리를 수행 하려면 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>주의  
 기본적으로 `CComObjectRootEx::FinalRelease` 는 아무 작업도 수행 합니다.  
  
 에 정리를 수행 `FinalRelease` 는 시점에 개체가 완전히 생성 되므로 클래스의 소멸자에 코드를 추가 하는 것이 좋습니다 `FinalRelease` 라고 합니다. 이렇게 하면 가장 많이 파생 된 클래스에서 제공 하는 메서드를 안전 하 게 액세스할 수 있습니다. 이것은 집계 된 모든 개체를 삭제 하기 전에 해제에 대 한 특히 중요 합니다.  
  
##  <a name="a-nameinternaladdrefa--ccomobjectrootexinternaladdref"></a><a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 집계 개체의 참조 횟수가 1 씩 늘립니다.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하 고 테스트 될 수 있는 값입니다.  
  
### <a name="remarks"></a>주의  
 스레드 모델 요소가 다중 스레드가 경우 **InterlockedIncrement** 둘 이상의 스레드가 동시에 참조 횟수를 변경 하지 못하도록 하는 데 사용 됩니다.  
  
##  <a name="a-nameinternalqueryinterfacea--ccomobjectrootexinternalqueryinterface"></a><a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
static HRESULT InternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pThis`  
 [in] 에 노출 된 인터페이스의 COM 맵을 포함 하는 개체에 대 한 포인터 `QueryInterface`합니다.  
  
 `pEntries`  
 [in] 에 대 한 포인터는 **_ATL_INTMAP_ENTRY** 사용할 수 있는 인터페이스의 지도 액세스 하는 구조입니다.  
  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 에 지정 된 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 하나는 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 `InternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체를 집계 하는 경우 `InternalQueryInterface` 알 수 없는 외부를 위임 하지 않습니다. 인터페이스를 COM 맵 테이블에 매크로 입력할 수 있습니다 [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) 또는 해당 변형 중 하나입니다.  
  
##  <a name="a-nameinternalreleasea--ccomobjectrootexinternalrelease"></a><a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 참조 횟수를 감소 집계 개체의 1입니다.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>반환 값  
 모두 비디버그 및 디버그 빌드를이 함수는 진단에 유용 또는 테스트 값을 반환 합니다. 참조 횟수가 수, 정확한 값 반환 사용, 운영 체제와 같은 많은 요인에 따라, 수도 있고 없을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 스레드 모델 요소가 다중 스레드가 경우 **InterlockedDecrement** 둘 이상의 스레드가 동시에 참조 횟수를 변경 하지 못하도록 하는 데 사용 됩니다.  
  
##  <a name="a-namelocka--ccomobjectrootexlock"></a><a name="lock"></a>CComObjectRootEx::Lock  
 스레드 모델 다중 스레드 이면이 메서드는 Win32 API 함수를 호출 하는 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), 전용 데이터 멤버를 통해 얻은 스레드가 임계 영역 개체의 소유권을 가져올 수 될 때까지 어떤 대기 합니다.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>주의  
 보호 되는 코드 실행이 끝나면 스레드가 호출 해야 `Unlock` 중요 섹션의 소유권을 해제 하려면.  
  
 단일 스레드 스레드 모델 있으면이 메서드는 아무것도 수행 하지 않습니다.  
  
##  <a name="a-namemdwrefa--ccomobjectrootexmdwref"></a><a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 4 바이트의 메모리에 액세스 하는 공용 구조체의 일부입니다.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>주의  
 와 `m_pOuterUnknown`공용 구조체의 일부인:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 개체가 집계 되지 않은 경우가 참조 횟수에 액세스할 `AddRef` 및 **릴리스** 에 저장 된 `m_dwRef`합니다. 개체를 집계 하는 경우 알 수 없는 외부에 대 한 포인터에 저장 됩니다 [m_pOuterUnknown](#m_pouterunknown)합니다.  
  
##  <a name="a-namempouterunknowna--ccomobjectrootexmpouterunknown"></a><a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 4 바이트의 메모리에 액세스 하는 공용 구조체의 일부입니다.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>주의  
 와 `m_dwRef`공용 구조체의 일부인:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 개체를 집계 하는 경우 알 수 없는 외부에 대 한 포인터에 저장 됩니다 `m_pOuterUnknown`합니다. 개체가 집계 되지 않은 경우가 참조 횟수에 액세스할 `AddRef` 및 **릴리스** 에 저장 된 [m_dwRef](#m_dwref)합니다.  
  
##  <a name="a-nameobjectmaina--ccomobjectrootexobjectmain"></a><a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 에 나열 된 각 클래스에 대해는 [개체 맵의](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f), 모듈을 초기화 하는 경우 한 후이 함수를 호출 및 종료 시간에 다시 합니다.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>매개 변수  
 `bStarting`  
 [out] 값은 **true** 클래스 초기화 하 고, 그렇지 않으면 되 고 있으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 값은 `bStarting` 매개 변수는 모듈 되 고 있는지 여부를 나타냅니다. 초기화 되거나 종료 합니다. 기본 구현은 `ObjectMain` 아무 것도 수행 하지만 초기화 하거나 클래스에 대 한 할당 하려는 리소스를 정리 하려면 클래스에서이 함수를 재정의할 수 있습니다. `ObjectMain` 클래스의 인스턴스를 모두 요청 되기 전에 호출 됩니다.  
  
 `ObjectMain`진입점 함수가 수행할 수 있는 작업의 형식을 제한 되어 있으므로 해당 DLL의 진입점에서 호출 됩니다. 이러한 제한 사항에 대 한 자세한 내용은 참조 하십시오. [런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 및 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#41;](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="a-nameouteraddrefa--ccomobjectrootexouteraddref"></a><a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 집계의 알 수 없는 외부의 참조 횟수를 증가 시킵니다.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하 고 테스트 될 수 있는 값입니다.  
  
##  <a name="a-nameouterqueryinterfacea--ccomobjectrootexouterqueryinterface"></a><a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
 요청된 된 인터페이스에 대 한 간접 포인터를 검색합니다.  
  
```
HRESULT OuterQueryInterface(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 에 지정 된 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 집계 인터페이스를 지원 하지 않는 경우.  
  
### <a name="return-value"></a>반환 값  
 하나는 표준 `HRESULT` 값입니다.  
  
##  <a name="a-nameouterreleasea--ccomobjectrootexouterrelease"></a><a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 집계의 알 수 없는 외부의 참조 횟수를 감소 시킵니다.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>반환 값  
 비-디버그 빌드에서만에서 항상 0을 반환 합니다. 디버그 빌드에서 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다.  
  
##  <a name="a-nameunlocka--ccomobjectrootexunlock"></a><a name="unlock"></a>CComObjectRootEx::Unlock  
 스레드 모델 다중 스레드 이면이 메서드는 Win32 API 함수를 호출 하는 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), 어떤 릴리스 소유권 임계 영역 개체의 전용 데이터 멤버를 통해 얻은 합니다.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>주의  
 소유권을 획득 하는 스레드에서 호출 해야 `Lock`합니다. 호출할 때마다 `Lock` 해당 호출 해야 `Unlock` 중요 섹션의 소유권을 해제 하려면.  
  
 단일 스레드 스레드 모델 있으면이 메서드는 아무것도 수행 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

