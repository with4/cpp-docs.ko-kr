---
title: "CComPtrBase 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 28207e483b0bf56b9e3e98f487d174b8ae47e9e7
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptrbase-class"></a>CComPtrBase 클래스
이 클래스는 COM 기반 메모리 루틴을 사용 하 여 스마트 포인터 클래스에 대 한 기반을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 스마트 포인터에 의해 참조 되는 개체 유형입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtrBase::Advise](#advise)|간의 연결을 만들려면이 메서드를 호출 하 여 `CComPtrBase`의 연결 지점과 클라이언트의 싱크 합니다.|  
|[CComPtrBase::Attach](#attach)|이 메서드는 기존 포인터의 소유권을 호출 합니다.|  
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|지정 된 클래스 ID 또는 프로그램 id입니다. 연결 된 클래스의 개체를 생성 하도록이 메서드를 호출 합니다.|  
|[CComPtrBase::CopyTo](#copyto)|복사 하려면이 메서드를 호출 하는 `CComPtrBase` 다른 포인터 변수에 대 한 포인터입니다.|  
|[CComPtrBase::Detach](#detach)|포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.|  
|[CComPtrBase::IsEqualObject](#isequalobject)|경우를 확인 하려면이 메서드를 호출 합니다. 지정 된 **IUnknown** 와 관련 된 동일한 개체를 가리키는 `CComPtrBase` 개체입니다.|  
|[CComPtrBase::QueryInterface](#queryinterface)|지정된 된 인터페이스에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.|  
|[CComPtrBase::Release](#release)|인터페이스를 해제 하려면이 메서드를 호출 합니다.|  
|[CComPtrBase::SetSite](#setsite)|사이트를 설정 하려면이 메서드를 호출 하는 `CComPtrBase` 개체는 **IUnknown** 부모 개체의 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|캐스트 연산자입니다.|  
|[CComPtrBase::operator!](#operator_not)|NOT 연산자입니다.|  
|[CComPtrBase::operator / /](#operator_amp)|연산자 < /.|  
|[CComPtrBase::operator *](#operator_star)|* 연산자입니다.|  
|[CComPtrBase::operator](#ccomptrbase__operator lt)|작음-연산자입니다.|  
|[CComPtrBase::operator = =](#operator_eq_eq)|같음 연산자입니다.|  
|[-> CComPtrBase::operator](#operator_ptr)|멤버에 대 한 포인터 연산자입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComPtrBase::p](#p)|포인터 데이터 멤버 변수입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스와 같은 COM 메모리 관리 루틴을 사용 하는 다른 스마트 포인터에 대 한 기본 제공 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 및 [CComPtr](../../atl/reference/ccomptr-class.md)합니다. 파생된 클래스 생성자 및 연산자를 직접 추가 하지만에서 제공 하는 방법에 의존 `CComPtrBase`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  
  
##  <a name="advise"></a>CComPtrBase::Advise  
 간의 연결을 만들려면이 메서드를 호출 하 여 `CComPtrBase`의 연결 지점과 클라이언트의 싱크 합니다.  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnk*  
 클라이언트에 대 한 포인터 **IUnknown**합니다.  
  
 `iid`  
 연결점의 GUID입니다. 일반적으로 이것이 연결 지점에서 관리 되는 송신 인터페이스와 동일 합니다.  
  
 `pdw`  
 연결을 고유 하 게 식별 하는 쿠키에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 참조 [AtlAdvise](http://msdn.microsoft.com/library/625a2f03-6b7f-4761-be5d-d2871d1d3254) 에 대 한 자세한 내용은 합니다.  
  
##  <a name="attach"></a>CComPtrBase::Attach  
 이 메서드는 기존 포인터의 소유권을 호출 합니다.  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p2`  
 `CComPtrBase` 개체는이 포인터의 소유권을 갖게 됩니다.  
  
### <a name="remarks"></a>주의  
 **연결** 호출 [CComPtrBase::Release](#release) 기존 [CComPtrBase::p](#p) 멤버 변수에 할당 한 다음 `p2` 를 `CComPtrBase::p`합니다. 경우는 `CComPtrBase` 개체 포인터의 소유권을 갖습니다, 자동으로 호출 합니다 `Release` 포인터 및 삭제 하는 포인터에 할당 된 데이터 개체의 참조 횟수가 0이 되는 경우.  
  
##  <a name="dtor"></a>CComPtrBase:: ~ CComPtrBase  
 소멸자입니다.  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>주의  
 가 가리키는 인터페이스를 해제 `CComPtrBase`합니다.  
  
##  <a name="cocreateinstance"></a>CComPtrBase::CoCreateInstance  
 지정 된 클래스 ID 또는 프로그램 id입니다. 연결 된 클래스의 개체를 생성 하도록이 메서드를 호출 합니다.  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `szProgID`  
 ProgID, CLSID를 사용 하 여에 대 한 포인터입니다.  
  
 `pUnkOuter`  
 경우 **NULL**, 개체가 생성 되지 않도록 되 고 집계의 일부로 나타냅니다. 비- **NULL**, 집계 개체에 대 한 포인터 **IUnknown** 인터페이스 (제어용 **IUnknown**).  
  
 `dwClsContext`  
 컨텍스트를 새로 만든된 개체를 관리 하는 코드가 실행 됩니다.  
  
 `rclsid`  
 데이터 및 개체를 만드는 데 사용할 코드와 관련 된 CLSID입니다.  
  
### <a name="return-value"></a>반환 값  
 실패 시 성공 "또는" REGDB_E_CLASSNOTREG "," CLASS_E_NOAGGREGATION "," CO_E_CLASSSTRING "또는"은 E_NOINTERFACE에 S_OK를 반환합니다. 참조 [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) 및 [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) 에 대 한 설명은 이러한 오류입니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 형태는 메서드를 호출 하면 [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) CLSID를 복구 하는 데 사용 됩니다. 두 형태 모두 다음 호출 [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.  
  
 디버그 빌드에서 어설션 오류가 발생 하는 경우 발생 합니다 [CComPtrBase::p](#p) NULL 같지 않습니다.  
  
##  <a name="copyto"></a>CComPtrBase::CopyTo  
 복사 하려면이 메서드를 호출 하는 `CComPtrBase` 다른 포인터 변수에 대 한 포인터입니다.  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *ppT*  
 수신할 변수의 주소는 `CComPtrBase` 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공, 실패 시 E_POINTER S_OK를 반환합니다.  
  
### <a name="remarks"></a>주의  
 복사본은 `CComPtrBase` 에 대 한 포인터 *ppT*합니다. 참조 횟수는 [CComPtrBase::p](#p) 멤버 변수가 증가 합니다.  
  
 HRESULT 경우 반환 되는 오류 *ppT* NULL과 같습니다. 디버그 빌드에서 어설션 오류가 발생 하는 경우 발생 합니다 *ppT* NULL과 같습니다.  
  
##  <a name="detach"></a>CComPtrBase::Detach  
 포인터의 소유권을 해제 하려면이 메서드를 호출 합니다.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 포인터의 복사본을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 포인터의 소유권을 해제, 설정 된 [CComPtrBase::p](#p) 데이터 멤버 변수를 NULL, 포인터의 복사본을 반환 합니다.  
  
##  <a name="isequalobject"></a>CComPtrBase::IsEqualObject  
 경우를 확인 하려면이 메서드를 호출 합니다. 지정 된 **IUnknown** 와 관련 된 동일한 개체를 가리키는 `CComPtrBase` 개체입니다.  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pOther`  
 **IUnknown \* ** 을 비교 합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 개체는 동일한 false로 설정 하는 경우 true를 반환 합니다.  
  
##  <a name="operator_not"></a>CComPtrBase::operator!  
 NOT 연산자입니다.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 경우 true를 반환은 `CComHeapPtr` 포인터가 NULL이 고 같으면 false 그렇지 않은 경우.  
  
##  <a name="operator_amp"></a>CComPtrBase::operator&amp;  
 연산자 < /.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>반환 값  
 가 가리키는 개체의 주소를 반환 하는 `CComPtrBase` 개체입니다.  
  
##  <a name="operator_star"></a>CComPtrBase::operator *  
 * 연산자입니다.  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 값을 반환 [CComPtrBase::p](#p); 즉, 참조 하는 개체에 대 한 포인터는 `CComPtrBase` 개체입니다.  
  
 디버그 빌드 경우 어설션 오류가 발생 합니다 [CComPtrBase::p](#p) NULL 같지 않습니다.  
  
##  <a name="operator_eq_eq"></a>CComPtrBase::operator = =  
 같음 연산자입니다.  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pT*  
 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 true를 반환 `CComPtrBase` 및 *pT* 가리킨 동일한 개체를 false 그렇지 않은 경우.  
  
##  <a name="operator_ptr"></a>CComPtrBase::operator-&gt;  

 멤버 포인터 연산자입니다.  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 값을 반환 된 [CComPtrBase::p](#p) 데이터 멤버 변수입니다.  
  
### <a name="remarks"></a>주의  
 이 연산자를 사용 하 여 가리키는 클래스에서 메서드를 호출 하는 `CComPtrBase` 개체입니다. 디버그 빌드에서 경우 어설션 오류가 발생 합니다는 `CComPtrBase` 데이터 멤버는 NULL을 가리킵니다.  
  
##  <a name="operator_lt"></a>CComPtrBase::operator&lt;  
 작음-연산자입니다.  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pT*  
 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 개체에서 포인터를 관리 하는 경우 true를 반환을 사용 하면 비교 되는 포인터 보다 작습니다.  
  
##  <a name="operator_t_star"></a>CComPtrBase::operator T *  
 캐스트 연산자입니다.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>주의  
 클래스 템플릿에 정의 된 개체 데이터 형식에 대 한 포인터를 반환 합니다.  
  
##  <a name="p"></a>CComPtrBase::p  
 포인터 데이터 멤버 변수입니다.  
  
```
T* p;
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수는 포인터 정보를 보유합니다.  
  
##  <a name="queryinterface"></a>CComPtrBase::QueryInterface  
 지정된 된 인터페이스에 대 한 포인터를 반환 하려면이 메서드를 호출 합니다.  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `Q`  
 필요한 인터페이스 포인터가 해당 개체 유형입니다.  
  
 `pp`  
 요청 된 인터페이스 포인터를 받는 출력 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 실패 시은 E_NOINTERFACE 성공 시 S_OK를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [IUnknown::QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)합니다.  
  
 디버그 빌드에서 어설션 오류가 발생 하는 경우 발생 합니다 *pp* NULL 같지 않습니다.  
  
##  <a name="release"></a>CComPtrBase::Release  
 인터페이스를 해제 하려면이 메서드를 호출 합니다.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>주의  
 인터페이스는 해제 되 고 [CComPtrBase::p](#p) NULL로 설정 됩니다.  
  
##  <a name="setsite"></a>CComPtrBase::SetSite  
 사이트를 설정 하려면이 메서드를 호출 하는 `CComPtrBase` 개체는 **IUnknown** 부모 개체의 합니다.  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `punkParent`  
 에 대 한 포인터는 **IUnknown** 부모 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [AtlSetChildSite](http://msdn.microsoft.com/library/2a8ece19-6bfd-4e89-9d1d-e5a78f95e2df)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

