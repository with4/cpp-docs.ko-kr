---
title: "CComClassFactory2 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
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
ms.openlocfilehash: 3787214d5479e1cd57295c9c25335e87651a16bb
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory2-class"></a>CComClassFactory2 클래스
이 클래스를 구현 하는 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>매개 변수  
 *라이선스*  
 다음과 같은 정적 함수를 구현 하는 클래스:  
  
- **정적 BOOL VerifyLicenseKey (BSTR** `bstr` **);**  
  
- **정적 BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **);**  
  
- **정적 BOOL IsLicenseValid ();**  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|라이선스 키를 지정 된 개체에 지정된 된 CLSID 만듭니다.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|클래스 팩터리의 라이센스 기능을 설명 하는 정보를 검색 합니다.|  
|[CComClassFactory2::LockServer](#lockserver)|메모리에서 클래스 팩터리를 잠급니다.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|만들고 라이선스 키를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `CComClassFactory2`구현 하는 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) 확장 인터페이스의 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)합니다. **IClassFactory2** 컨트롤 개체는 라이선스를 통해 생성 됩니다. 클래스 팩터리를 실행 하는 사용이 허가 된 컴퓨터에서 런타임 라이선스 키를 제공할 수 있습니다. 이 라이선스 키에는 응용을 프로그램을 전체 컴퓨터 라이선스 존재 하지 않을 경우 개체를 인스턴스화할 수 있습니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로가 포함 [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4)를 선언 하 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하 여 `CComClassFactory2`, 지정는 [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, 템플릿 매개 변수를 `CComClassFactory2`, 정적 함수를 구현 해야 `VerifyLicenseKey`, `GetLicenseKey`, 및 `IsLicenseValid`합니다. 다음은 간단한 라이선스 클래스의 예입니다.  
  
 [!code-cpp[NVC_ATL_COM&#3;](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`둘 다에서 파생 되며 **CComClassFactory2Base** 및 *라이선스*합니다. **CComClassFactory2Base**에서 파생 됩니다, **IClassFactory2** 및 **CComObjectRootEx\< CComGlobalsThreadModel >**합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory2::CreateInstance  
 지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkOuter`  
 [in] 개체를 만드는 경우 집계의 일부로 다음 `pUnkOuter` 알 수 없는 외부 이어야 합니다. 그렇지 않으면 `pUnkOuter` 해야 **NULL**합니다.  
  
 `riid`  
 [in] 요청된 된 인터페이스의 IID입니다. 경우 `pUnkOuter` 이 아닌 **NULL**, `riid` 해야 **IID_IUnknown**합니다.  
  
 `ppvObj`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppvObj` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 완벽 하 게 사용 허가 받아야 하는 컴퓨터가 필요 합니다. 전체 컴퓨터 라이선스 존재 하지 않는 경우에 호출 [CreateInstanceLic](#createinstancelic)합니다.  
  
##  <a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic  
 유사한 [CreateInstance](#createinstance)점을 제외 하 고 `CreateInstanceLic` 라이선스 키가 필요 합니다.  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkOuter`  
 [in] 개체를 만드는 경우 집계의 일부로 다음 `pUnkOuter` 알 수 없는 외부 이어야 합니다. 그렇지 않으면 `pUnkOuter` 해야 **NULL**합니다.  
  
 *pUnkReserved*  
 [in] 사용 되지 않습니다. 해야 **NULL**합니다.  
  
 `riid`  
 [in] 요청된 된 인터페이스의 IID입니다. 경우 `pUnkOuter` 이 아닌 **NULL**, `riid` 해야 **IID_IUnknown**합니다.  
  
 `bstrKey`  
 [in] 런타임 라이선스 키에 대 한 호출에서 이전에 가져온 `RequestLicKey`합니다. 이 키는 개체를 만드는 데 필요 합니다.  
  
 `ppvObject`  
 [out] 지정 된 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppvObject` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 라이선스 키를 사용 하 여 가져올 수 있습니다 [RequestLicKey](#requestlickey)합니다. 허가 되지 않은 컴퓨터에서 개체를 만들기 위해를 호출 해야 `CreateInstanceLic`합니다.  
  
##  <a name="getlicinfo"></a>CComClassFactory2::GetLicInfo  
 채우기는 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) 클래스 팩터리를 설명 하는 정보가 포함 된 구조체의 기능 라이선스.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pLicInfo*  
 [out] 에 대 한 포인터는 **LICINFO** 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 `fRuntimeKeyAvail` 이 구조체의 멤버 수 있는지 여부를, 라이선스 키를 매개 변수로 받아 클래스 팩터리 개체를 허가 되지 않은 컴퓨터에서 만들 수를 나타냅니다. *fLicVerified* 멤버는 전체 컴퓨터 라이선스 있는지 여부를 나타냅니다.  
  
##  <a name="lockserver"></a>CComClassFactory2::LockServer  
 증가 하 고 호출 하 여 모듈 잠금 횟수를 감소 **_Module::Lock** 및 **_Module::Unlock**각각.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>매개 변수  
 `fLock`  
 [in] 경우 **TRUE**, 잠금 횟수가 증가 하 고, 그렇지 않으면, 잠금 수가 감소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 **_Module** 의 전역 인스턴스를 가리키며 [CComModule](../../atl/reference/ccommodule-class.md) 에서 파생 된 클래스 또는 합니다.  
  
 호출 `LockServer` 클라이언트가 여러 개체를 신속 하 게 만들 수 있도록 클래스 팩터리를 점유 하는 데 사용 합니다.  
  
##  <a name="requestlickey"></a>CComClassFactory2::RequestLicKey  
 만들고 제공 하는 라이선스 키를 반환는 `fRuntimeKeyAvail` 의 멤버는 [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) 구조는 **TRUE**합니다.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwReserved`  
 [in] 사용 되지 않습니다. 0이어야 합니다.  
  
 `pbstrKey`  
 [out] 라이선스 키에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 라이선스 키가 호출 하는 데 필요한 [CreateInstanceLic](#createinstancelic) 않은 시스템에서 개체를 만들려고 합니다. 경우 `fRuntimeKeyAvail` 는 **FALSE**, 다음 개체는 사용 허가 받은 컴퓨터에만 만들 수 있습니다.  
  
 호출 [만들도록](#getlicinfo) 의 값을 검색 `fRuntimeKeyAvail`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComClassFactoryAutoThread 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [클래스 개요](../../atl/atl-class-overview.md)

