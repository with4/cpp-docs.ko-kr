---
title: "COM 인터페이스 항목 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76352cf2015661bc970b2987b9794f3bf023cc15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cominterfaceentry-macros"></a>COM_INTERFACE_ENTRY 매크로  
 이러한 매크로 입력 개체의 인터페이스가 COM 맵을에서 액세스할 수 있도록 `QueryInterface`합니다. COM 맵에서 항목의 순서는 짝이 되는 순서 인터페이스 확인 **IID** 중 `QueryInterface`합니다.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|COM 인터페이스 맵을에 인터페이스를 입력합니다.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|상속의 두 분기를이 매크로 사용 합니다.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|이 매크로 사용 하 여 COM 맵을에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|와 동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)를 제외한 다른 IID를 지정할 수 있습니다.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|와 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리, `punk`합니다.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|와 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우 제외 `punk` 은 **NULL**에서 설명 하는 집계를 자동으로 만듭니다는 `clsid`합니다.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|와 동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리, `punk`를 쓰고 `punk` 은 **NULL**을 자동으로 만듭니다는 에 설명 된 집계는 `clsid`합니다.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|하면 호출 프로그램 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) 지정된 된 인터페이스에 대 한 쿼리 되는 경우.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|분리 인터페이스를 노출합니다.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|처리 COM 맵에서에서이 항목에 도달 하면 기본 클래스의 COM 맵을 처리 합니다.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|와 동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)제외 하 고에 대 한 호출으로 인해 모든 IID에 대 한 쿼리, `func`합니다.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|반환 **E_NOINTERFACE** 종료에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리 합니다.|  

## <a name="requirements"></a>요구 사항
**헤더:** atlcom.h

## <a name="com_interface_entry"></a>COM_INTERFACE_ENTRY
COM 인터페이스 맵을에 인터페이스를 입력합니다.

### <a name="syntax"></a>구문

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>매개 변수

[in]는 인터페이스의 이름이 x 클래스 개체에서 파생 직접 됩니다.

### <a name="remarks"></a>설명
일반적으로 가장 자주 사용 하는 항목 형식입니다.

### <a name="example"></a>예
```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```
### <a name="requirements"></a>요구 사항
**헤더:** atlcom.h
  
##  <a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 상속의 두 분기를이 매크로 사용 합니다.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 개체에서 노출 하는 인터페이스의 이름입니다.  
  
 `x2`  
 [in] 상속 분기의 이름 *x* 노출 됩니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 두 개의 듀얼 인터페이스에서 클래스 개체를 파생 하는 경우 노출 `IDispatch` 를 사용 하 여 `COM_INTERFACE_ENTRY2` 이후 `IDispatch` 인터페이스 중 하나에서 얻을 수 있습니다.  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 이 매크로 사용 하 여 COM 맵을에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 노출 된 인터페이스의 GUID입니다.  
  
 *x*  
 [in] 해당 vtable로 식별 된 인터페이스로 노출 됩니다 클래스의 이름 `iid`합니다.  
  
 
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 와 동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)를 제외한 다른 IID를 지정할 수 있습니다.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 인터페이스에 대해 지정 하는 GUID입니다.  
  
 *x*  
 [in] 클래스 개체에서 직접 파생 되는 인터페이스의 이름입니다.  
  
 `x2`  
 [in] 클래스 개체에서 직접 파생 되는 다른 인터페이스의 이름입니다.  
  
##  <a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `punk` 매개 변수는 알 수 없는 내부 또는의 집계를 가리키도록 간주 됩니다 **NULL**,이 경우 항목은 무시 됩니다. 일반적으로 **CoCreate** 집계에 `FinalConstruct`합니다.  
  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 와 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리, `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>설명  
 인터페이스 쿼리 실패를 COM 맵 처리가 계속 됩니다.  
  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 와 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우 제외 `punk` 은 **NULL**에서 설명 하는 집계를 자동으로 만듭니다는 `clsid`합니다.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다.  
  
 `clsid`  
 [in] 경우 생성 되는 집계 식별자 `punk` 은 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 와 동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리, `punk`를 쓰고 `punk` 은 **NULL**을 자동으로 만듭니다는 에 설명 된 집계는 `clsid`합니다.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>매개 변수  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다.  
  
 `clsid`  
 [in] 경우 생성 되는 집계 식별자 `punk` 은 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 인터페이스 쿼리 실패를 COM 맵 처리가 계속 됩니다.  
  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 하면 호출 프로그램 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) 지정된 된 인터페이스에 대 한 쿼리 되는 경우.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스 식별자 생성에 사용 되는 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 IID를 추가 하 여 생성 될 인터페이스 *x* 를 `IID_`합니다. 예를 들어 경우 *x* 은 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 분리 인터페이스의 GUID입니다.  
  
 *x*  
 [in] 인터페이스를 구현 하는 클래스의 이름입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다. 초기화 해야 **NULL** 클래스 개체의 생성자에 있습니다.  
  
### <a name="remarks"></a>설명  
 인터페이스를 사용 하지 않으면이 개체의 전체 인스턴스 크기를 통해 줄어듭니다.  
  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 분리 인터페이스를 노출합니다.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 분리 인터페이스의 GUID입니다.  
  
 *x*  
 [in] 인터페이스를 구현 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 분리 인터페이스를 나타내는 인터페이스 때마다 인스턴스화되는 별도 개체를 쿼리 하는 대로 구현 됩니다. 일반적으로 주요 개체의 모든 인스턴스에 vtable 포인터를 저장이 있으므로 인터페이스를 거의 사용 하는 경우는 분리로 인터페이스에 빌드합니다. 참조 횟수가 0 인 경우는 분리 삭제 됩니다. 분리를 구현 하는 클래스에서 파생 되는 `CComTearOffObjectBase` COM 맵을 있고 합니다.  
  
  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 처리 COM 맵에서에서이 항목에 도달 하면 기본 클래스의 COM 맵을 처리 합니다.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>매개 변수  
 *classname*  
 [in] 현재 개체의 기본 클래스입니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 다음 코드는  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 참고 COM 맵에서 첫 번째 항목은 COM 맵을 포함 하는 개체의 인터페이스를 이어야 합니다. 와 COM 맵 항목을 시작할 수 없습니다 따라서 `COM_INTERFACE_ENTRY_CHAIN`, 검색 지점에서 대상으로 다른 개체의 COM 맵을 때문에 여기서 **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** 개체의 COM 지도에 표시 됩니다. 다른 개체의 COM 맵을 먼저 검색 하려는 경우 추가 대 한 인터페이스 항목 **IUnknown** COM 지도 개체의 COM 맵에서 다음 연결 합니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 노출 된 인터페이스의 GUID입니다.  
  
 `dw`  
 [in] 매개 변수를 통해 전달 된 `func`합니다.  
  
 `func`  
 [in] 반환 하는 함수 포인터 `iid`합니다.  
  
### <a name="remarks"></a>설명  
 경우 *iid* 에 지정 된 함수를 쿼리 하는 인터페이스의 IID와 일치 `func` 호출 됩니다. 함수에 대 한 선언 해야 합니다.  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 함수를 호출할 때 `pv` 클래스 개체를 가리킵니다. `riid` 매개 변수를 쿼리 하는 인터페이스를 참조 `ppv` 함수는 인터페이스에 대 한 포인터를 저장 해야 하는 위치에 대 한 포인터 및 `dw` 항목에 지정 된 매개 변수입니다. 함수를 설정 해야 \* `ppv` 를 **NULL** 다음 다시 돌아와 **E_NOINTERFACE** 또는 **S_FALSE** 를 인터페이스를 반환 하지 않도록 선택 합니다. 와 **E_NOINTERFACE**를 COM 맵 처리가 종료 됩니다. 와 **S_FALSE**, 인터페이스 포인터가 반환 된 경우에 COM 맵 처리가 계속 됩니다. 함수 반환 인터페이스 포인터를 반환 해야 `S_OK`합니다.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 와 동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)제외 하 고에 대 한 호출으로 인해 모든 IID에 대 한 쿼리, `func`합니다.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>매개 변수  
 `dw`  
 [in] 매개 변수를 통해 전달 된 `func`합니다.  
  
 `func`  
 [in] 이 항목 COM 맵에서 처리 될 때 호출 되는 함수입니다.  
  
### <a name="remarks"></a>설명  
 모든 오류 처리를 COM 맵에서 계속 발생 합니다. 함수 반환 인터페이스 포인터를 반환 해야 `S_OK`합니다.  
  
  
##  <a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 반환 **E_NOINTERFACE** 종료에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리 합니다.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스 식별자 생성에 사용 되는 텍스트입니다.  
  
### <a name="remarks"></a>설명  
 인터페이스는 특정 한 경우에 사용 되지 않도록 방지 하기 위해이 매크로 사용할 수 있습니다. 예를 들어 사용자 COM에이 매크로 삽입할 수 있습니다 바로 전 까지의 매핑할 `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` 인터페이스에 대 한 쿼리를 알 수 없는 내부는 집계에 전달 되 고 하지 못하도록 합니다.  
  
 IID를 추가 하 여 생성 될 인터페이스 *x* 를 `IID_`합니다. 예를 들어 경우 *x* 은 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.  
  
  