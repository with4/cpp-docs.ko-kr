---
title: "CComMultiThreadModelNoCS 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
caps.latest.revision: 18
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: dd14e5c941da5383dce19e9f7f539bfb9909759f
ms.lasthandoff: 02/28/2017

---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS 클래스
`CComMultiThreadModelNoCS`스레드로부터 안전한 메서드를 제공 증가 및 감소는 변수의 값 없이 임계 영역 잠금 또는 잠금 해제 기능입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|클래스를 참조 `CComFakeCriticalSection`합니다.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|클래스를 참조 `CComMultiThreadModelNoCS`합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(정적) 감소 스레드로부터 안전한 방식으로 지정 된 변수의 값입니다.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(정적) 스레드로부터 안전한 방식으로 지정 된 변수의 값을 증가 시킵니다.|  
  
## <a name="remarks"></a>주의  
 `CComMultiThreadModelNoCS`유사한 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 제공 한다는 점에서 스레드로부터 안전한 메서드 증가 및 감소에 대 한 변수입니다. 그러나 참조 하는 경우를 통해 중요 섹션 클래스 `CComMultiThreadModelNoCS`와 같은 메서드 `Lock` 및 `Unlock` 아무 작업도 하지 것입니다.  
  
 일반적으로 사용 `CComMultiThreadModelNoCS` 통해는 `ThreadModelNoCS` `typedef` 이름입니다. 이 `typedef` 에 정의 된 `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)합니다.  
  
> [!NOTE]
>  전역 `typedef` 이름 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 및 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) 참조 하지 않는 `CComMultiThreadModelNoCS`합니다.  
  
 외에 `ThreadModelNoCS`, `CComMultiThreadModelNoCS` 정의 `AutoCriticalSection` 및 `CriticalSection`합니다. 이러한 마지막 두 개의 `typedef` 이름이 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), 가져오기 및 해제는 임계 영역와 관련 된 빈 메서드를 제공 하는 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModelNoCS::AutoCriticalSection  
 사용 하는 경우 `CComMultiThreadModelNoCS`, `typedef` 이름 `AutoCriticalSection` 클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>주의  
 때문에 `CComFakeCriticalSection` 임계 영역을 제공 하지 않습니다 해당 메서드는 아무것도 수행 합니다.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에 대 한 정의 포함 `AutoCriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `AutoCriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 외에 `AutoCriticalSection`를 사용할 수는 `typedef` 이름 [CriticalSection](#criticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
##  <a name="criticalsection"></a>CComMultiThreadModelNoCS::CriticalSection  
 사용 하는 경우 `CComMultiThreadModelNoCS`, `typedef` 이름 `CriticalSection` 클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>주의  
 때문에 `CComFakeCriticalSection` 임계 영역을 제공 하지 않습니다 해당 메서드는 아무것도 수행 합니다.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에 대 한 정의 포함 `CriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `CriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 외에 `CriticalSection`를 사용할 수는 `typedef` 이름 `AutoCriticalSection`합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
##  <a name="decrement"></a>CComMultiThreadModelNoCS::Decrement  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)를 가리키는 변수의 값을 감소 시킵니다 `p`합니다.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 감소 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 감소의 결과 0, `Decrement` 0을 반환 합니다. 감소 시켜 결과&0;이 아니면 반환 값도&0;이 아닌 있지만 감소의 결과 일치 하지 않을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 **InterlockedDecrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="increment"></a>CComMultiThreadModelNoCS::Increment  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)를 가리키는 변수의 값이 증가 `p`합니다.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 증가 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 증가값의 결과 0, **증가** 0을 반환 합니다. 증가값의 결과 이면&0;이 아닌 반환 값도&0;이 아닌 있지만 증가값의 결과 일치 하지 않을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 **InterlockedIncrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModelNoCS::ThreadModelNoCS  
 사용 하는 경우 `CComMultiThreadModelNoCS`, `typedef` 이름 `ThreadModelNoCS` 참조 `CComMultiThreadModelNoCS`합니다.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>주의  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 에 대 한 정의 포함 `ThreadModelNoCS`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 클래스 간의 관계를 보여 줍니다. `ThreadModelNoCS`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 정의의 `ThreadModelNoCS` 에서 `CComMultiThreadModelNoCS` 에 대응 하 여 제공 `CComMultiThreadModel` 및 `CComSingleThreadModel`합니다. 예를 들어 샘플 코드에 `CComMultiThreadModel::AutoCriticalSection` 다음 선언 `typedef`:  
  
 [!code-cpp[#37 NVC_ATL_COM](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 에 대 한 지정 된 클래스에 관계 없이 `ThreadModel` (예: `CComMultiThreadModelNoCS`), `_ThreadModel` 적절 하 게 확인 합니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
