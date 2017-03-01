---
title: "CComMultiThreadModel 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATL.CComMultiThreadModel
- ATL::CComMultiThreadModel
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6dbfb33a717b23e8252c9bcb2fc11b4a6e420280
ms.lasthandoff: 02/24/2017

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
  
## <a name="remarks"></a>주의  
 일반적으로 사용 `CComMultiThreadModel` 두 가지 중 하나를 통해 `typedef` 이름, [CComObjectThreadModel] (atl-typedefs.md #ccomobjectthreadmodel 또는 [CComGlobalsThreadModel] (atl-typedefs.md #ccomglobalsthreadmodel 합니다. 각각 사용 하 여 참조 하는 클래스 `typedef` 는 다음 표에 나와 있는 것 처럼 사용 하 고 스레딩 모델에 따라 달라 집니다.  
  
|형식 정의|단일 스레딩|아파트 스레딩|자유 스레딩|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`세 가지 정의 자체 `typedef` 이름입니다. `AutoCriticalSection`및 `CriticalSection` 얻기을 중요 섹션의 소유권을 해제 하기 위한 메서드를 제공 하는 클래스를 참조 합니다. `ThreadModelNoCS`참조 클래스 [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md) 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `AutoCriticalSection` 클래스를 참조 [CComAutoCriticalSection](ccomautocriticalsection-class.md), 얻는 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 하는 합니다.  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>주의  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에 대 한 정의 포함 `AutoCriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `AutoCriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `AutoCriticalSection`를 사용할 수는 `typedef` 이름 [CriticalSection](#criticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 다음 코드는 기반으로 모델링 [CComObjectRootEx](ccomobjectrootex-class.md)를 보여 줍니다 `AutoCriticalSection` 스레딩 환경에서 사용 되 고 있습니다.  
  

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
  
|메서드|단일 또는 아파트 스레딩|자유 스레딩|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|증가값이 스레드로부터 안전 하지 않습니다.|증가값은 스레드로부터 안전 합니다.|  
|`Lock`|없습니다. 중요 한 구역이 잠글 수 없기 때문입니다.|중요 한 섹션이 잠겨 있습니다.|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel CComObjectThreadModel::ThreadModelNoCS =  
  
|메서드|단일 또는 아파트 스레딩|자유 스레딩|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|증가값이 스레드로부터 안전 하지 않습니다.|증가값은 스레드로부터 안전 합니다.|  
|`Lock`|없습니다. 중요 한 구역이 잠글 수 없기 때문입니다.|없습니다. 중요 한 구역이 잠글 수 없기 때문입니다.|  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `CriticalSection` 클래스를 참조 [클래스](ccomcriticalsection-class.md), 얻는 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 하는 합니다.  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>주의  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) 에 대 한 정의 포함 `CriticalSection`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 중요 섹션 클래스 간의 관계를 보여 줍니다. `CriticalSection`:  
  
|에 정의 된 클래스|참조 클래스|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 외에 `CriticalSection`를 사용할 수는 `typedef` 이름 [AutoCriticalSection](#autocriticalsection)합니다. 지정 하지 않아야 `AutoCriticalSection` CRT 시작 코드를 제거 하려는 경우에 정적 클래스 멤버 또는 전역 개체입니다.  
  
### <a name="example"></a>예제  
 참조 [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)합니다.  
  
##  <a name="a-namedecrementa--ccommultithreadmodeldecrement"></a><a name="decrement"></a>CComMultiThreadModel::Decrement  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)를 가리키는 변수의 값을 감소 시킵니다 `p`합니다.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 감소 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 감소의 결과 0, `Decrement` 0을 반환 합니다. 감소 시켜 결과&0;이 아니면 반환 값도&0;이 아닌 있지만 감소의 결과 일치 하지 않을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 **InterlockedDecrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="a-nameincrementa--ccommultithreadmodelincrement"></a><a name="increment"></a>CComMultiThreadModel::Increment  
 Win32 함수를 호출 하는이 정적 함수 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)를 가리키는 변수의 값이 증가 `p`합니다.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 증가 시킬 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 증가값의 결과 0, **증가** 0을 반환 합니다. 증가값의 결과 이면&0;이 아닌 반환 값도&0;이 아닌 있지만 증가값의 결과 일치 하지 않을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 **InterlockedIncrement** 둘 이상의 스레드가 동시에이 변수를 사용 하는 것을 방지 합니다.  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 사용 하는 경우 `CComMultiThreadModel`, `typedef` 이름 `ThreadModelNoCS` 클래스를 참조 [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)합니다.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>주의  
 `CComMultiThreadModelNoCS`증가 및 감소 변수;에 대해 스레드로부터 안전한 메서드를 제공합니다. 그러나 임계를 제공 하지 않습니다.  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) 및 `CComMultiThreadModelNoCS` 에 대 한 정의 포함 `ThreadModelNoCS`합니다. 다음 표에서 스레딩 모델 클래스와 참조 하는 클래스 간의 관계를 보여 줍니다. `ThreadModelNoCS`:  
  
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

