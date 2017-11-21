---
title: "CComMultiThreadModel 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs: C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7aad1856f28a1d76b53b983e63f36cf5fd4a7cfe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel 클래스
`CComMultiThreadModel`변수 값 증가 및 감소에 대 한 스레드 안전 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|클래스를 참조 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)합니다.|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|클래스를 참조 [클래스](../../atl/reference/ccomcriticalsection-class.md)합니다.|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|클래스를 참조 [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(정적) 감소 스레드로부터 안전한 방식으로 지정 된 변수의 값입니다.|  
|[CComMultiThreadModel::Increment](#increment)|(정적) 스레드로부터 안전한 방식으로 지정 된 변수의 값을 증가 시킵니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 사용 `CComMultiThreadModel` 2 중 하나를 통해 `typedef` 이름, [CComObjectThreadModel] (atl-typedefs.md #ccomobjectthreadmodel 또는 [CComGlobalsThreadModel] (atl-typedefs.md #ccomglobalsthreadmodel 합니다. 각에서 참조 하는 클래스 `typedef` 다음 표에 나와 있는 것 처럼을 사용 하는 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`세 개의 정의 자체 `typedef` 이름입니다. `AutoCriticalSection`및 `CriticalSection` 가져오는 임계의 소유권을 해제 하기 위한 메서드를 제공 하는 클래스를 참조 합니다. `ThreadModelNoCS`참조 클래스 [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md) 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `AutoCriticalSection` 클래스를 참조 [CComAutoCriticalSection](ccomautocriticalsection-class.md), 가져오기을 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 하는 합니다.  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>설명  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에 대 한 정의 포함 `AutoCriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 임계 클래스 간의 관계를 보여 줍니다. `AutoCriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `AutoCriticalSection`를 사용할 수 있습니다는 `typedef` 이름 [CriticalSection](#criticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` 전역 개체 또는 정적 클래스 멤버는 CRT 시작 코드를 제거 하려는 경우.  
  
### <a name="example"></a>예제  
 다음 코드는 기반으로 모델링 [CComObjectRootEx](ccomobjectrootex-class.md), 보여줍니다 `AutoCriticalSection` 스레딩 환경에서 사용 되 고 있습니다.  
  

```cpp  
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);   
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```  
  
 다음 표에서 결과 보여 줍니다.는 `InternalAddRef` 및 `Lock` 에 따라 메서드는 **ThreadModel** 템플릿 매개 변수 및 응용 프로그램에서 사용 되는 스레딩 모델:  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel CComObjectThreadModel =  
  
|메서드|단일 컴퓨터 또는 아파트 스레딩|자유 스레딩|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|증가값이 스레드로부터 안전 하지 않습니다.|증가값은 스레드로부터 안전 합니다.|  
|`Lock`|만 수행 합니다. 중요 한 구역이 잠글 수 없기 때문입니다.|임계 영역 잠겨 있습니다.|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel CComObjectThreadModel::ThreadModelNoCS =  
  
|메서드|단일 컴퓨터 또는 아파트 스레딩|자유 스레딩|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|증가값이 스레드로부터 안전 하지 않습니다.|증가값은 스레드로부터 안전 합니다.|  
|`Lock`|만 수행 합니다. 중요 한 구역이 잠글 수 없기 때문입니다.|만 수행 합니다. 중요 한 구역이 잠글 수 없기 때문입니다.|  
  
##  <a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `CriticalSection` 클래스를 참조 [클래스](ccomcriticalsection-class.md), 가져오기을 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 하는 합니다.  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>설명  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에 대 한 정의 포함 `CriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 임계 클래스 간의 관계를 보여 줍니다. `CriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `CriticalSection`를 사용할 수 있습니다는 `typedef` 이름 [AutoCriticalSection](#autocriticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` 전역 개체 또는 정적 클래스 멤버는 CRT 시작 코드를 제거 하려는 경우.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)합니다.  
  
##  <a name="decrement"></a>CComMultiThreadModel::Decrement  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), 가리키는 변수의 값을 감소 `p`합니다.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 감소 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 감소의 결과 0, `Decrement` 0을 반환 합니다. 감소 시켜 결과 0이 아닌 경우 반환 값도 0이 아닌 이지만 감소 시켜 결과 같지 않을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 **InterlockedDecrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="increment"></a>CComMultiThreadModel::Increment  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)를 가리키는 변수의 값이 증가 `p`합니다.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 증가 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 한 증가값의 결과 0, **증분** 0을 반환 합니다. 증가값의 결과 0이 아닌 경우 반환 값도 0이 아닌 이지만 한 증가값의 결과 같지 않을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 **InterlockedIncrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `ThreadModelNoCS` 클래스를 참조 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)합니다.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>설명  
 `CComMultiThreadModelNoCS`증가 및 감소 변수;에 대해 스레드로부터 안전한 메서드를 제공합니다. 그러나 임계를 제공 하지 않습니다.  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 `CComMultiThreadModelNoCS` 에 대 한 정의 포함 `ThreadModelNoCS`합니다. 다음 표에서 스레딩 모델 클래스에서 참조 하는 클래스와의 관계를 보여 줍니다. `ThreadModelNoCS`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComSingleThreadModel 클래스](ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection 클래스](ccomautocriticalsection-class.md)   
 [클래스 클래스](ccomcriticalsection-class.md)   
 [클래스 개요](../atl-class-overview.md)
