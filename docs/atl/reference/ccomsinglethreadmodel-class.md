---
title: "CComSingleThreadModel 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: ff5d8d2ced1d6fe0196888d8c746844ace8307f8
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel 클래스
이 클래스 메서드를 제공 증가 및 감소에 대 한 변수 값입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|클래스를 참조 `CComFakeCriticalSection`합니다.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|참조 `CComSingleThreadModel`합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|감소 지정 된 변수의 값입니다. 이 구현은 스레드로부터 안전 하지 않습니다.|  
|[CComSingleThreadModel::Increment](#increment)|지정 된 변수의 값을 증가 시킵니다. 이 구현은 스레드로부터 안전 하지 않습니다.|  
  
## <a name="remarks"></a>주의  
 `CComSingleThreadModel`변수 값 증가 및 감소에 대 한 메서드를 제공 합니다. 와 달리 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), 이러한 메서드는 스레드로부터 안전 하지 않습니다.  

 일반적으로 사용 `CComSingleThreadModel` 두 가지 중 하나를 통해 `typedef` 이름, 하거나 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 또는 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)합니다. 각각 사용 하 여 참조 하는 클래스 `typedef` 는 다음 표에 나와 있는 것 처럼 사용 하 고 스레딩 모델에 따라 달라 집니다.  

  
|형식 정의|단일 스레딩 모델|아파트 스레딩 모델|자유 스레딩 모델|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`세 가지 정의 자체 `typedef` 이름입니다. `ThreadModelNoCS`참조 `CComSingleThreadModel`합니다. `AutoCriticalSection`및 `CriticalSection` 클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), 가져오기 및 중요 섹션의 소유권을 해제와 관련 된 빈 메서드를 제공 하는 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 사용 하는 경우 `CComSingleThreadModel`, `typedef` 이름 `AutoCriticalSection` 클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>주의  
 때문에 `CComFakeCriticalSection` 임계 영역을 제공 하지 않습니다 해당 메서드는 아무것도 수행 합니다.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) 에 대 한 정의가 `AutoCriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `AutoCriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `AutoCriticalSection`를 사용할 수는 `typedef` 이름 [CriticalSection](#criticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
##  <a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 사용 하는 경우 `CComSingleThreadModel`, `typedef` 이름 `CriticalSection` 클래스를 참조 [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)합니다.  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>주의  
 때문에 `CComFakeCriticalSection` 임계 영역을 제공 하지 않습니다 해당 메서드는 아무것도 수행 합니다.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) 에 대 한 정의가 `CriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `CriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `CriticalSection`를 사용할 수는 `typedef` 이름 [AutoCriticalSection](#autocriticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
##  <a name="decrement"></a>CComSingleThreadModel::Decrement  
 이 정적 함수 감소는 변수 값을 가리키는 `p`합니다.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 감소 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 결과 감소입니다.  
  
##  <a name="increment"></a>CComSingleThreadModel::Increment  
 이 정적 함수 감소는 변수 값을 가리키는 `p`합니다.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 증가 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 결과 증가값입니다.  
  
##  <a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 사용 하는 경우 `CComSingleThreadModel`, `typedef` 이름 `ThreadModelNoCS` 참조 `CComSingleThreadModel`합니다.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>주의  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 및 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) 에 대 한 정의가 `ThreadModelNoCS`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 클래스 간의 관계를 보여 줍니다. `ThreadModelNoCS`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

