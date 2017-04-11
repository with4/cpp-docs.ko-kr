---
title: "CComObjectRootEx 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::CComObjectRootEx
- ATLCOM/ATL::InternalAddRef
- ATLCOM/ATL::InternalRelease
- ATLCOM/ATL::Lock
- ATLCOM/ATL::Unlock
- ATLCOM/ATL::FinalConstruct
- ATLCOM/ATL::FinalRelease
- ATLCOM/ATL::OuterAddRef
- ATLCOM/ATL::OuterQueryInterface
- ATLCOM/ATL::OuterRelease
- ATLCOM/ATL::InternalQueryInterface
- ATLCOM/ATL::ObjectMain
- ATLCOM/ATL::m_dwRef
- ATLCOM/ATL::m_pOuterUnknown
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: ff699c5d4620de01bd1f2ed1e3b87a4d77aa8396
ms.lasthandoff: 03/31/2017

---
# <a name="ccomobjectrootex-class"></a>CComObjectRootEx 클래스
이 클래스는 집계 되지 않은 원시 및 집계 개체에 대 한 개체 참조 개수 관리를 처리 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class ThreadModel>  
class CComObjectRootEx : public CComObjectRootBase
```  
  
#### <a name="parameters"></a>매개 변수  
 `ThreadModel`  
 해당 메서드가 필요한 스레딩 모델을 구현 하는 클래스입니다. 스레딩 모델을 설정 하 여 명시적으로 선택할 수 있습니다 `ThreadModel` 를 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), 또는 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)합니다. 설정 하 여 서버의 기본 스레드 모델을 그대로 사용할 수 있습니다 `ThreadModel` 를 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)합니다.  

  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CComObjectRootEx](#ccomobjectrootex)|생성자입니다.|  
|[InternalAddRef](#internaladdref)|집계 되지 않은 원시 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[InternalRelease](#internalrelease)|집계 되지 않은 원시 개체에 대 한 참조 횟수를 감소 시킵니다.|  
|[잠금](#lock)|스레드 모델 이면 다중 스레드 임계 영역 개체의 소유권을 가져오면 됩니다.|  
|[잠금 해제](#unlock)|스레드 모델 이면 다중 스레드 임계 영역 개체의 소유권을 해제 합니다.|  
  
### <a name="ccomobjectrootbase-methods"></a>CComObjectRootBase 메서드  
  
|||  
|-|-|  
|[FinalConstruct](#finalconstruct)|개체에 필요한 모든 초기화를 수행 하려면 클래스에서 재정의 합니다.|  
|[FinalRelease](#finalrelease)|개체에 필요한 정리 작업을 수행 하려면 클래스에서 재정의 합니다.|  
|[OuterAddRef](#outeraddref)|집계 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[OuterQueryInterface](#outerqueryinterface)|대리자에는 외부 **IUnknown** 집계 개체입니다.|  
|[OuterRelease](#outerrelease)|집계 개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
### <a name="static-functions"></a>정적 함수  
  
|||  
|-|-|  
|[InternalQueryInterface](#internalqueryinterface)|위임 된 **IUnknown** 집계 되지 않은 원시 개체의 합니다.|  
|[ObjectMain](#objectmain)|개체 맵의에 나열 된 파생된 클래스에 대 한 종료 및 모듈을 초기화 하는 동안 호출 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_dwRef](#m_dwref)|와 `m_pOuterUnknown`, 공용 구조체의 부분입니다. 개체의 참조 수를 보유 하는 집계 되지 않습니다 때 사용 되는 `AddRef` 및 **릴리스**합니다.|  
|[m_pOuterUnknown](#m_pouterunknown)|와 `m_dwRef`, 공용 구조체의 부분입니다. 개체가 집계 되는 알 수 없는 외부에 대 한 포인터를 저장할 때 사용 됩니다.|  
  
## <a name="remarks"></a>주의  
 `CComObjectRootEx`집계 되지 않은 원시 및 집계 개체에 대 한 개체 참조 개수 관리를 처리합니다. 개체가 집계 되는 개체가 집계 되는 경우 알 수 없는 외부에 포인터를 보유 하는 경우 개체 참조 횟수를 보유 합니다. 집계 개체에 대 한 `CComObjectRootEx` 내부 개체의 오류를 생성, 처리를 메서드를 사용할 수 있으며 내부 인터페이스 릴리스될 때 삭제 되지 않도록에서 외부 개체 또는 내부 개체를 보호 하기 위해 삭제 됩니다.  
  
 COM 서버를 구현 하는 클래스에서 상속 해야 `CComObjectRootEx` 또는 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)합니다.  
  
 클래스 정의 지정 하는 경우는 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable) ATL 매크로의 인스턴스를 만들고 **CComPolyObject\<CYourClass >** 때 **IClassFactory::CreateInstance** 호출 됩니다. 만드는 동안 알 수 없는 외부의 값이 확인 됩니다. 이 경우 **NULL**, **IUnknown** 집계 되지 않은 원시 개체에 대 한 구현 됩니다. 알 수 없는 외부 없으면 **NULL**, **IUnknown** 집계 개체에 대 한 구현 됩니다.  
  
 클래스를 지정 하지 않는 경우는 `DECLARE_POLY_AGGREGATABLE` ATL 매크로의 인스턴스를 만들고 **CAggComObject\<CYourClass >** 인스턴스 또는 집계 개체에 대 한 **CComObject\<CYourClass >** 집계 되지 않은 원시 개체에 대 한 합니다.  
  
 사용 시의 이점은 `CComPolyObject` 두는 것을 방지 하는 `CComAggObject` 및 `CComObject` 모듈 집계 및 집계 되지 않은 원시 경우를 처리 합니다. 단일 `CComPolyObject` 두 경우 모두 처리 하는 개체입니다. 따라서 vtable의 복사본이 한 개만 및 함수에의 한 복사본만 모듈에서 존재 합니다. Vtable이 큰 경우 모듈 크기가 상당히 줄어들 수 있습니다이 있습니다. 그러나 vtable 작으면를 사용 하 여 `CComPolyObject` 집계 또는 집계 되지 않은 원시 개체에 대해 최적화 되어 있지 않으므로 조금 더 큰 모듈 크기는 발생할 수 있습니다는 `CComAggObject` 및 `CComObject`합니다.  
  
 개체가 집계 되는, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 구현한 `CComAggObject` 또는 `CComPolyObject`합니다. 이러한 클래스에 위임 `QueryInterface`, `AddRef`, 및 **릴리스** 에 대 한 호출이 `CComObjectRootEx`의 `OuterQueryInterface`, `OuterAddRef`, 및 `OuterRelease` 알 수 없는 외부를 전달 해야 합니다. 일반적으로, 재정의 `CComObjectRootEx::FinalConstruct` 집계 된 모든 개체를 만들고 재정의 하려면 클래스에서 `CComObjectRootEx::FinalRelease` 를 해제 하기 위해 개체를 집계 합니다.  
  
 에 개체가 집계 되지 않은 경우 **IUnknown** 구현한 `CComObject` 또는 `CComPolyObject`합니다. 이 경우에 대 한 호출이 `QueryInterface`, `AddRef`, 및 **릴리스** 에 위임 되며 `CComObjectRootEx`의 `InternalQueryInterface`, `InternalAddRef`, 및 `InternalRelease` 실제 작업을 수행 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="ccomobjectrootex"></a>CComObjectRootEx::CComObjectRootEx  
 생성자를 참조 개수를 0으로 초기화합니다.  
  
```
CComObjectRootEx();
```  
  
##  <a name="finalconstruct"></a>CComObjectRootEx::FinalConstruct  
 파생된 클래스 개체에 필요한 초기화를 수행 하기에이 메서드를 재정의할 수 있습니다.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>반환 값  
 반환할 `S_OK` 성공 또는 표준 오류 중 하나에 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `CComObjectRootEx::FinalConstruct` 단순히 반환 `S_OK`합니다.  
  
 초기화를 수행 하는 이점이 있습니다 `FinalConstruct` 클래스의 생성자를 대신 합니다.  
  
-   생성자에서 상태 코드를 반환할 수 없습니다 되었지만 반환할 수 있습니다는 `HRESULT` 방법으로 `FinalConstruct`의 값을 반환 합니다. 클래스 개체를 생성 되는지 ATL에서 제공 하는 표준 클래스 팩터리를 사용 하는 경우 자세한 오류 정보를 제공 하는 수 있도록 COM 클라이언트에 반환 값이 전파 됩니다.  
  
-   클래스의 생성자에서 가상 함수 메커니즘을 통해 가상 함수를 호출할 수 없습니다. 상속 계층 구조에서 해당 시점에 정의 된 대로 정적으로 확인 된 함수 호출에서 발생 클래스의 생성자에서 가상 함수를 호출 합니다. 순수 가상 함수에 대 한 호출 링커 오류가 발생합니다.  
  
     클래스 상속 계층 구조에서 가장 많이 파생 된 클래스가 아닙니다.-일부 기능을 제공 하는 ATL에서 제공 하는 파생된 클래스에 의존 합니다. 프로그램 초기화 됩니다 (이 클래스 개체를 다른 개체를 집계 해야 하는 경우) 해당 클래스를 제공 하는 기능을 사용 해야 하는 경우가 있지만 클래스의 생성자에 이러한 기능에 액세스할 수 없습니다. 클래스에 대 한 구성 코드는 가장 많이 파생 된 클래스 완전히 생성 되기 전에 실행 됩니다.  
  
     그러나 `FinalConstruct` 클래스가 ATL.에서 제공 하는 참조 횟수 구현을 사용 하 고 가상 함수를 호출할 수 있도록 생성 완벽 하 게 될 가장 많이 파생 된 후 즉시 호출  
  
### <a name="example"></a>예제  
 파생 된 클래스에서이 메서드를 재정의 하는 일반적으로 `CComObjectRootEx` 을 만드는 개체를 집계 합니다. 예:  
  
 [!code-cpp[NVC_ATL_COM #40](../../atl/codesnippet/cpp/ccomobjectrootex-class_1.h)]  
  
 생성에 실패 하면 오류를 반환할 수 있습니다. 매크로 사용할 수도 있습니다 [DECLARE_PROTECT_FINAL_CONSTRUCT](aggregation-and-class-factory-macros.md#declare_protect_final_construct) 외부 개체를에서 보호 하기 위해, 만드는 동안 집계 된 내부 개체를 증가 시키는 경우 참조 횟수 다음 감소 개수를 0으로를 삭제 합니다.  
  
 집계를 만드는 일반적인 방법은 다음과 같습니다.  
  
-   추가 **IUnknown** 클래스에 대 한 포인터 개체를 초기화 하도록 **NULL** 생성자에서 합니다.  
  
-   재정의 `FinalConstruct` 집계를 만들려고 합니다.  
  
-   사용 하 여는 **IUnknown** 포인터에 대 한 매개 변수로 정의 [COM_INTERFACE_ENTRY_AGGREGATE](com-interface-entry-macros.md#com_interface_entry_aggregate) 매크로입니다.  
  
-   재정의 `FinalRelease` 를 해제 하는 **IUnknown** 포인터입니다.  
  
##  <a name="finalrelease"></a>CComObjectRootEx::FinalRelease  
 개체에 필요한 정리 작업을 수행 하려면 파생된 클래스에서이 메서드를 재정의할 수 있습니다.  
  
```
void FinalRelease();
```  
  
### <a name="remarks"></a>주의  
 기본적으로 `CComObjectRootEx::FinalRelease` 는 아무 작업도 수행 합니다.  
  
 에 정리를 수행 `FinalRelease` 개체가 여전히 완전 하 게 된 지점에서 생성 하므로 클래스의 소멸자에 코드를 추가 하는 것이 좋습니다 `FinalRelease` 라고 합니다. 이렇게 하면 가장 많이 파생 된 클래스에서 제공 하는 메서드를 안전 하 게 액세스할 수 있습니다. 이 집계 된 모든 개체를 삭제 하기 전에 해제에 대 한 특히 중요 합니다.  
  
##  <a name="internaladdref"></a>CComObjectRootEx::InternalAddRef  
 집계 되지 않은 원시 개체의 참조 횟수를 1 씩 증가 합니다.  
  
```
ULONG InternalAddRef();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 대 한 유용 하 고 테스트 될 수 있는 값입니다.  
  
### <a name="remarks"></a>설명  
 스레드 모델은 다중 스레드, 경우 **InterlockedIncrement** 여러 스레드에서 동시에 참조 횟수를 변경 하지 못하도록 하는 데 사용 됩니다.  
  
##  <a name="internalqueryinterface"></a>CComObjectRootEx::InternalQueryInterface  
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
 [in] 에 대 한 포인터는 **_ATL_INTMAP_ENTRY** 맵을 사용할 수 있는 인터페이스에 액세스 하는 구조입니다.  
  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 에 지정 된 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 `InternalQueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다. 개체를 집계 하는 경우 `InternalQueryInterface` 알 수 없는 외부를 위임 하지 않습니다. 인터페이스에서는 COM 맵 테이블에 매크로 입력할 수 [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) 또는 해당 변형 중 하나입니다.  
  
##  <a name="internalrelease"></a>CComObjectRootEx::InternalRelease  
 참조 횟수를 줄입니다 집계 되지 않은 원시 개체의 1입니다.  
  
```
ULONG InternalRelease();
```  
  
### <a name="return-value"></a>반환 값  
 둘 다 비디버그 및 디버그 빌드를이 함수는 진단에 대 한 유용한 또는 테스트 값을 반환 합니다. 참조 횟수 수, 정확한 값 반환을 사용 하는 운영 체제와 같은 많은 요인에 따라, 수도 있고 없을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 스레드 모델은 다중 스레드, 경우 **InterlockedDecrement** 여러 스레드에서 동시에 참조 횟수를 변경 하지 못하도록 하는 데 사용 됩니다.  
  
##  <a name="lock"></a>CComObjectRootEx::Lock  
 이 메서드는 Win32 API 함수를 호출 스레드 모델 이면 다중 스레드 [유용](http://msdn.microsoft.com/library/windows/desktop/ms682608), 스레드가 임계 영역 개체의 소유권을 가져올 수 있습니다 때까지 대기는 전용 데이터 멤버를 통해 얻은 합니다.  
  
```
void Lock();
```  
  
### <a name="remarks"></a>설명  
 보호 되는 코드 실행이 끝나면 스레드를 호출 해야 `Unlock` 임계 영역 소유권을 해제 하려면.  
  
 단일 스레드 스레드 모델 있으면이 메서드는 아무 작업도 수행 하지 않습니다.  
  
##  <a name="m_dwref"></a>CComObjectRootEx::m_dwRef  
 4 바이트의 메모리에 액세스 하는 공용 구조체의 일부입니다.  
  
```
long m_dwRef;
```  
  
### <a name="remarks"></a>주의  
 와 `m_pOuterUnknown`, 공용 구조체의 일부:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 참조 횟수에서 액세스 하는 개체가 집계 되지 않은 경우 `AddRef` 및 **릴리스** 에 저장 된 `m_dwRef`합니다. 개체가 집계 되 고 포인터를 알 수 없는 외부에 저장 됩니다 [m_pOuterUnknown](#m_pouterunknown)합니다.  
  
##  <a name="m_pouterunknown"></a>CComObjectRootEx::m_pOuterUnknown  
 4 바이트의 메모리에 액세스 하는 공용 구조체의 일부입니다.  
  
```
IUnknown*
    m_pOuterUnknown;
```     
  
### <a name="remarks"></a>주의  
 와 `m_dwRef`, 공용 구조체의 일부:  
  
 `union`  
  
 `{`  
  
 `long m_dwRef;`  
  
 `IUnknown* m_pOuterUnknown;`  
  
 `};`  
  
 개체가 집계 되 고 포인터를 알 수 없는 외부에 저장 됩니다 `m_pOuterUnknown`합니다. 참조 횟수에서 액세스 하는 개체가 집계 되지 않은 경우 `AddRef` 및 **릴리스** 에 저장 된 [m_dwRef](#m_dwref)합니다.  
  
##  <a name="objectmain"></a>CComObjectRootEx::ObjectMain  
 에 나열 된 각 클래스에 대 한는 [개체 맵의](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f),이 함수는 모듈을 초기화 하는 경우 한 번 호출 됩니다 종료 시간에 다시 고 합니다.  
  
```
static void WINAPI ObjectMain(bool bStarting);
```  
  
### <a name="parameters"></a>매개 변수  
 `bStarting`  
 [out] 값은 **true** 클래스 고, 그렇지 않으면 초기화 되 고 있으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 값은 `bStarting` 매개 변수는 모듈은 되 고 있는지 여부를 나타냅니다. 초기화 되거나 종료 합니다. 기본 구현은 `ObjectMain` 아무 것도 수행 하지만 배열을 초기화 하거나 할당할 클래스에 대 한 리소스를 정리 하려면 클래스에서이 함수를 재정의할 수 있습니다. `ObjectMain` 클래스 인스턴스의 모든 요청 전에 호출 됩니다.  
  
 `ObjectMain`진입점 함수가 수행할 수 있는 작업의 형식을 제한 되어 있으므로 해당 DLL의 진입점에서 호출 됩니다. 이러한 제한 사항에 대 한 자세한 내용은 참조 하십시오. [런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 및 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM #41](../../atl/codesnippet/cpp/ccomobjectrootex-class_2.h)]  
  
##  <a name="outeraddref"></a>CComObjectRootEx::OuterAddRef  
 집계의 알 수 없는 외부의 참조 횟수를 증가 시킵니다.  
  
```
ULONG OuterAddRef();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 대 한 유용 하 고 테스트 될 수 있는 값입니다.  
  
##  <a name="outerqueryinterface"></a>CComObjectRootEx::OuterQueryInterface  
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
 표준 중 하나 `HRESULT` 값입니다.  
  
##  <a name="outerrelease"></a>CComObjectRootEx::OuterRelease  
 집계의 알 수 없는 외부의 참조 횟수를 줄입니다.  
  
```
ULONG OuterRelease();
```  
  
### <a name="return-value"></a>반환 값  
 디버그가 아닌 빌드에서 항상 0을 반환합니다. 디버그 빌드에 진단에 대 한 유용 하거나 테스트 일 수 있는 값을 반환 합니다.  
  
##  <a name="unlock"></a>CComObjectRootEx::Unlock  
 이 메서드는 Win32 API 함수를 호출 스레드 모델 이면 다중 스레드 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), 어떤 릴리스 소유권 임계 영역 개체의 전용 데이터 멤버를 통해 얻은 합니다.  
  
```
void Unlock();
```  
  
### <a name="remarks"></a>주의  
 소유권을 획득 하는 스레드에서 호출 해야 `Lock`합니다. 호출할 때마다 `Lock` 해당 호출을 `Unlock` 임계 영역 소유권을 해제 하려면.  
  
 단일 스레드 스레드 모델 있으면이 메서드는 아무 작업도 수행 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

