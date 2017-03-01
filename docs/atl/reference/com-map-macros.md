---
title: "COM 맵 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79658b6ac22719af7172c9d2848675faf2a23a0c
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-macros"></a>COM 맵 매크로
이러한 매크로 COM 인터페이스 맵 정의합니다.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM 인터페이스 맵 항목의 시작을 표시 합니다.|  
|[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)|COM 인터페이스 맵에 인터페이스를 입력합니다.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|상속의 두 분기를이 매크로 사용 합니다.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|이 매크로 사용 하 여 COM 맵을에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)를 제외한 다른 IID를 지정할 수 있습니다.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)점을 제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리 `punk`합니다.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우 제외 `punk` 는 **NULL**에서 설명 하는 집계를 자동으로 만듭니다는 `clsid`합니다.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|와 동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)점을 제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리 `punk`, 경우에 `punk` 는 **NULL**, 자동으로 만들기에서 설명 하는 집계는 `clsid`합니다.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|하면 호출 프로그램 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) 지정된 된 인터페이스에 대 한 쿼리 되는 경우.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|모든 인스턴스에 대 한 인터페이스 관련 데이터를 저장합니다.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|분리 인터페이스를 노출합니다.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|처리에는이 COM 맵의이 항목에 도달할 때 기본 클래스의 COM 지도 처리 합니다.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)점을 제외 하 고 호출에서 결과 모든 IID를 쿼리하면 `func`합니다.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|반환 **은 E_NOINTERFACE** 에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리를 종료 합니다.|  
|[END_COM_MAP](#end_com_map)|COM 인터페이스 맵 항목의 끝을 표시 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="a-namebegincommapa--begincommap"></a><a name="begin_com_map"></a>BEGIN_COM_MAP  
 COM에서 개체를 통해 클라이언트에 대 한 인터페이스를 노출 하는 메커니즘은 `QueryInterface`합니다.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스에서 제공 하는 클래스 개체의 이름입니다.  
  
### <a name="remarks"></a>주의  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 만 COM 맵에서 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스 맵을 시작한는 `BEGIN_COM_MAP` 매크로와 인터페이스의 각 항목을 추가 [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) 매크로 또는 해당 변형 중 하나를 사용 하 여 맵을 완료는 [END_COM_MAP](#end_com_map) 매크로 합니다.  

  
### <a name="example"></a>예제  
 ATL에서 [호출기](../../visual-cpp-samples.md) 샘플:  
  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrymacrosa--cominterfaceentry-macros"></a><a name="com_interface_entry_macros"></a>COM_INTERFACE_ENTRY 매크로  
 이러한 매크로에서 액세스할 수 있도록 개체의 인터페이스를 쿼리하면 COM 맵을에 입력할 `QueryInterface`합니다. COM 맵에서 항목의 순서는 짝이 되는 순서 인터페이스 확인 **IID** 중 `QueryInterface`합니다.  
  
##  <a name="a-namecominterfaceentry2x2a--cominterfaceentry2"></a><a name="com_interface_entry2_x2"></a>COM_INTERFACE_ENTRY2  
 상속의 두 분기를이 매크로 사용 합니다.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 개체에서 노출 하는 인터페이스의 이름입니다.  
  
 `x2`  
 [in] 상속 분기의 이름을 *x* 노출 됩니다.  
  
### <a name="remarks"></a>주의  
 예를 들어 두 이중 인터페이스에서 클래스 개체를 파생 하는 경우 노출 `IDispatch` 를 사용 하 여 `COM_INTERFACE_ENTRY2` 이후 `IDispatch` 인터페이스 중 하나에서 가져올 수 있습니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryiida--cominterfaceentryiid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 이 매크로 사용 하 여 COM 맵을에 인터페이스를 입력 하 고 해당 IID를 지정 합니다.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 표시 되는 인터페이스의 GUID입니다.  
  
 *x*  
 [in] 로 식별 되는 인터페이스와 해당 vtable 노출 될 클래스의 이름을 `iid`합니다.  
  
### <a name="remarks"></a>주의  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&117;](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="a-namecominterfaceentry2iida--cominterfaceentry2iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 동일 [COM_INTERFACE_ENTRY2](#com_interface_entry2)를 제외한 다른 IID를 지정할 수 있습니다.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 인터페이스를 지정 하는 GUID입니다.  
  
 *x*  
 [in] 클래스 개체에서 직접 파생 되는 인터페이스의 이름입니다.  
  
 `x2`  
 [in] 클래스 개체에서 직접 파생 되는 다른 인터페이스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentry2a--cominterfaceentry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 상속의 두 분기를이 매크로 사용 합니다.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 개체에서 노출 하는 인터페이스의 이름입니다.  
  
 `x2`  
 [in] 상속 분기의 이름을 *x* 노출 됩니다.  
  
### <a name="remarks"></a>주의  
 예를 들어 두 이중 인터페이스에서 클래스 개체를 파생 하는 경우 노출 `IDispatch` 를 사용 하 여 `COM_INTERFACE_ENTRY2` 이후 `IDispatch` 인터페이스 중 하나에서 가져올 수 있습니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryaggregate2a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate2"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `punk` 매개 변수는 알 수 없는 내부 또는의 집계를 가리키도록 간주 됩니다 **NULL**,이 경우 항목은 무시 됩니다. 일반적으로 **CoCreate** 집계에 `FinalConstruct`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryaggregateblinda--cominterfaceentryaggregateblind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)점을 제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리 `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 COM 맵 처리 하는 경우 인터페이스 쿼리가 실패 하면 계속 합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&113;](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  
##  <a name="a-namecominterfaceentryaggregate3a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate3"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `punk` 매개 변수는 알 수 없는 내부 또는의 집계를 가리키도록 간주 됩니다 **NULL**,이 경우 항목은 무시 됩니다. 일반적으로 **CoCreate** 집계에 `FinalConstruct`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregatea--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우 제외 `punk` 는 **NULL**에서 설명 하는 집계를 자동으로 만듭니다는 `clsid`합니다.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다.  
  
 `clsid`  
 [in] 경우에 작성 되는 집계의 식별자 `punk` 는 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentryaggregatea--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 때로 식별 되는 인터페이스 `iid` 쿼리 하는, `COM_INTERFACE_ENTRY_AGGREGATE` 전달 `punk`합니다.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다.  
  
### <a name="remarks"></a>주의  
 `punk` 매개 변수는 알 수 없는 내부 또는의 집계를 가리키도록 간주 됩니다 **NULL**,이 경우 항목은 무시 됩니다. 일반적으로 **CoCreate** 집계에 `FinalConstruct`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregateblinda--cominterfaceentryautoaggregateblind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 와 동일 [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)점을 제외 하 고 쿼리를 전달 하면 모든 IID에 대 한 쿼리 `punk`, 경우에 `punk` 는 **NULL**, 자동으로 만들기에서 설명 하는 집계는 `clsid`합니다.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>매개 변수  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다.  
  
 `clsid`  
 [in] 경우에 작성 되는 집계의 식별자 `punk` 는 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 COM 맵 처리 하는 경우 인터페이스 쿼리가 실패 하면 계속 합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&115;](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregate2a--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate2"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 동일 [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), 경우 제외 `punk` 는 **NULL**에서 설명 하는 집계를 자동으로 만듭니다는 `clsid`합니다.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 에 대 한 쿼리 인터페이스의 GUID입니다.  
  
 `punk`  
 [in] 이름을 **IUnknown** 포인터입니다. COM 맵을 포함 하는 클래스의 멤버 여야 합니다.  
  
 `clsid`  
 [in] 경우에 작성 되는 집계의 식별자 `punk` 는 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentrybreaka--cominterfaceentrybreak"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 하면 호출 프로그램 [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) 지정된 된 인터페이스에 대 한 쿼리 되는 경우.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스 식별자를 생성 하는 데 사용 하는 텍스트입니다.  
  
### <a name="remarks"></a>주의  
 IID가 추가 하 여 생성 되는 인터페이스 *x* 를 `IID_`합니다. 예를 들어 경우 *x* 는 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentrycachedtearoffa--cominterfaceentrycachedtearoff"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
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
  
### <a name="remarks"></a>주의  
 인터페이스를 사용 하지 않으면이 개체의 전체 인스턴스 크기를 줄입니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#54;](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="a-namecominterfaceentrytearoffa--cominterfaceentrytearoff"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 분리 인터페이스를 노출합니다.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 분리 인터페이스의 GUID입니다.  
  
 *x*  
 [in] 인터페이스를 구현 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>주의  
 분리 인터페이스를 나타내는 인터페이스 때마다 인스턴스화되는 별도 개체를 쿼리 하는 대로 구현 됩니다. 일반적으로 인터페이스는 거의 사용 되므로 기본 개체의 모든 인스턴스에 대 한 vtable 포인터를 저장이 경우는 분리로 인터페이스 빌드할. 참조 횟수가&0; 인 경우는 분리 삭제 됩니다. 구현에서 분리 하는 클래스에서 파생 되는 `CComTearOffObjectBase` 있고 고유한 COM 맵.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrychaina--cominterfaceentrychain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 처리에는이 COM 맵의이 항목에 도달할 때 기본 클래스의 COM 지도 처리 합니다.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>매개 변수  
 *응용 프로그램 이름*  
 [in] 현재 개체의 기본 클래스입니다.  
  
### <a name="remarks"></a>주의  
 예를 들어 다음 코드는에서  
  
 [!code-cpp[NVC_ATL_Windowing&116;](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 COM의 첫 번째 항목에 매핑하는 COM 맵을 포함 하는 개체에 인터페이스 여야 합니다. 사용 하면 COM 맵 엔트리를 시작할 수 없습니다 따라서 `COM_INTERFACE_ENTRY_CHAIN`, 지점에서 검색 될 다른 개체의 COM 맵을 이르게 여기서 **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** 개체의 COM 지도에 표시 합니다. 다른 개체의 COM 맵을 먼저 검색 하려는 경우에 대 한 인터페이스 항목을 추가 합니다. **IUnknown** COM 지도 개체의 COM 맵을 다음 연결 합니다. 예:  
  
 [!code-cpp[NVC_ATL_Windowing #&111;](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentryfunc2a--cominterfaceentryfunc"></a><a name="com_interface_entry_func2"></a>COM_INTERFACE_ENTRY_FUNC  
 ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 표시 되는 인터페이스의 GUID입니다.  
  
 `dw`  
 [in] 매개 변수를 통해 전달 된 `func`합니다.  
  
 `func`  
 [in] 반환 되는 함수 포인터 `iid`합니다.  
  
### <a name="remarks"></a>주의  
 경우 *iid* 에 지정 된 함수를 쿼리 하는 인터페이스의 IID와 일치 `func` 호출 됩니다. 함수에 대해 선언 되어야 합니다.  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 함수를 호출할 때 `pv` 클래스 개체를 가리킵니다. `riid` 매개 변수를 쿼리 하는 인터페이스를 참조 `ppv` 함수는 인터페이스에 대 한 포인터를 저장 해야 하는 위치에 대 한 포인터 및 `dw` 항목에 지정 된 매개 변수입니다. 함수를 설정 해야 \* `ppv` 를 **NULL** 반환 **은 E_NOINTERFACE** 또는 **S_FALSE** 를 인터페이스를 반환 하지 않도록 선택 하는 경우. 와 **은 E_NOINTERFACE**를 COM 맵 처리를 종료 합니다. 와 **S_FALSE**, 인터페이스 포인터가 반환 된 경우에 COM 맵 처리가 계속 됩니다. 함수 반환 인터페이스 포인터를 반환 해야 `S_OK`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentryfuncblinda--cominterfaceentryfuncblind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 동일 [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)점을 제외 하 고 호출에서 결과 모든 IID를 쿼리하면 `func`합니다.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>매개 변수  
 `dw`  
 [in] 매개 변수를 통해 전달 된 `func`합니다.  
  
 `func`  
 [in] 이 COM 맵의이 항목을 처리할 때 호출 되는 함수입니다.  
  
### <a name="remarks"></a>주의  
 모든 오류 처리를 COM 맵에 계속 하면 됩니다. 함수 반환 인터페이스 포인터를 반환 해야 `S_OK`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentryfunca--cominterfaceentryfunc"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 ATL의에 연결 하는 일반 메커니즘 `QueryInterface` 논리입니다.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 표시 되는 인터페이스의 GUID입니다.  
  
 `dw`  
 [in] 매개 변수를 통해 전달 된 `func`합니다.  
  
 `func`  
 [in] 반환 되는 함수 포인터 `iid`합니다.  
  
### <a name="remarks"></a>주의  
 경우 *iid* 에 지정 된 함수를 쿼리 하는 인터페이스의 IID와 일치 `func` 호출 됩니다. 함수에 대해 선언 되어야 합니다.  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 함수를 호출할 때 `pv` 클래스 개체를 가리킵니다. `riid` 매개 변수를 쿼리 하는 인터페이스를 참조 `ppv` 함수는 인터페이스에 대 한 포인터를 저장 해야 하는 위치에 대 한 포인터 및 `dw` 항목에 지정 된 매개 변수입니다. 함수를 설정 해야 \* `ppv` 를 **NULL** 반환 **은 E_NOINTERFACE** 또는 **S_FALSE** 를 인터페이스를 반환 하지 않도록 선택 하는 경우. 와 **은 E_NOINTERFACE**를 COM 맵 처리를 종료 합니다. 와 **S_FALSE**, 인터페이스 포인터가 반환 된 경우에 COM 맵 처리가 계속 됩니다. 함수 반환 인터페이스 포인터를 반환 해야 `S_OK`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-namecominterfaceentrynointerfacea--cominterfaceentrynointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 반환 **은 E_NOINTERFACE** 에 대 한 지정된 된 인터페이스를 쿼리하면 COM 맵을 처리를 종료 합니다.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 인터페이스 식별자를 생성 하는 데 사용 하는 텍스트입니다.  
  
### <a name="remarks"></a>주의  
 인터페이스는 특정 한 경우에 사용 되지 않도록 방지 하기 위해이 매크로 사용할 수 있습니다. 예를 들어 사용자 COM에이 매크로 삽입할 수 있습니다 바로 앞에 매핑할 `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` 인터페이스에 대 한 쿼리를 알 수 없는 내부 집계의에 전달 되 고 하지 못하도록 합니다.  
  
 IID가 추가 하 여 생성 되는 인터페이스 *x* 를 `IID_`합니다. 예를 들어 경우 *x* 는 `IPersistStorage`, IID 됩니다 `IID_IPersistStorage`합니다.  
  
 참조 [COM_INTERFACE_ENTRY 매크로](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) COM에 대 한 설명에 대 한 항목을 매핑해야 합니다.  
  
##  <a name="a-nameendcommapa--endcommap"></a><a name="end_com_map"></a>END_COM_MAP  
 COM 인터페이스 맵의 정의 종료합니다.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)   
 [Com 전역 함수](../../atl/reference/com-map-global-functions.md)

