---
title: "CComCoClass 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCoClass
- ATL.CComCoClass
- ATL::CComCoClass
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6201051a38ac65788086dcf7ee4c3f3441988e71
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcoclass-class"></a>CComCoClass 클래스
이 클래스는 클래스의 인스턴스를 만들고 해당 속성을 가져오는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `CComCoClass`합니다.  
  
 *pclsid*  
 개체의 CLSID에 대 한 포인터입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(정적) 클래스 및 인터페이스에 대 한 쿼리 인스턴스를 만듭니다.|  
|[CComCoClass::Error](#error)|(정적) 클라이언트에 자세한 오류 정보를 반환합니다.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(정적) 개체의 클래스 식별자를 반환합니다.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(정적) 개체의 설명을 반환 하려면 재정의 합니다.|  
  
## <a name="remarks"></a>주의  
 `CComCoClass`개체의 CLSID를 검색, 오류 정보를 설정 및 클래스의 인스턴스를 만드는 메서드를 제공 합니다. 에 등록 된 모든 클래스는 [개체 맵의](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) 에서 파생 되는 `CComCoClass`합니다.  
  
 `CComCoClass`또한 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 정의합니다. `CComCoClass`다음 두 매크로 사용합니다.  
  
- [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4) 되도록 클래스 팩터리 선언 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)합니다.  
  
- [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab) 개체를 집계할 수 있도록 선언 합니다.  
  
 클래스 정의에 다른 매크로 지정 하 여 이러한 기본값 중 하나를 재정의할 수 있습니다. 예를 들어, 사용 하 여 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) 대신 `CComClassFactory`, 지정 된 [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) 매크로:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomcoclasscreateinstance"></a><a name="createinstance"></a>CComCoClass::CreateInstance  
 이 사용 하 여 `CreateInstance` 는 COM의 인스턴스를 만드는 함수 개체를 COM API를 사용 하지 않고 인터페이스 포인터를 검색 합니다.  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `Q`  
 COM 인터페이스를 통해 반환 되는 `pp`합니다.  
  
 *punkOuter*  
 [in] 알 수 없는 외부 또는 집계의 제어 알 수 있습니다.  
  
 `pp`  
 [out] 만들기가 성공 하는 경우 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다. 참조 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 설명은 가능한 반환 값입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 첫 번째 오버 로드를 사용 하 여 일반적인 개체를 생성 합니다. 생성 되는 개체를 집계 해야 하는 경우에 두 번째 오버 로드를 사용 합니다.  
  
 필요한 COM 개체를 구현 하는 ATL 클래스 (첫 번째 템플릿 매개 변수로 사용 되는 클래스, 즉 [CComCoClass](../../atl/reference/ccomcoclass-class.md)) 호출 하는 코드와 동일한 프로젝트에 있어야 합니다. COM 개체의 생성이 ATL 클래스에 대해 등록 된 클래스 팩터리를 통해 수행 됩니다.  
  
 이러한 함수를 사용 하 여 외부에서 만들 수 없도록 하지 않도록 하는 개체를 만드는 데 도움이 되는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1) 매크로입니다. 효율성을 위해 COM API를 방지 하려는 경우에도 유용 합니다.  
  
 인터페이스 `Q` 를 사용 하 여 검색할 수 있는 IID 연결 되어 있어야 합니다.는 [__uuidof](../../cpp/uuidof-operator.md) 연산자입니다.  
  
### <a name="example"></a>예제  
 다음 예에서 `CDocument` ATL 마법사에서 생성 된 클래스에서 파생 `CComCoClass` 구현 하는 **IDocument** 인터페이스입니다. 클래스는 개체 맵의으로 등록 됩니다는 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` 클라이언트가 사용 하 여 문서 인스턴스를 만들 수 있도록 매크로 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다. `CApplication`문서 클래스의 인스턴스를 만드는 COM 인터페이스 중 하나에서 메서드를 제공 하는 CoClass가입니다. 얼마나 쉬운지 아래 코드를 사용 하 여 문서 클래스의 인스턴스를 만듭니다는 `CreateInstance` 에서 상속 된 멤버는 `CComCoClass` 기본 클래스입니다.  
  
 [!code-cpp[NVC_ATL_COM&#11;](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="a-nameerrora--ccomcoclasserror"></a><a name="error"></a>CComCoClass::Error  
 설정 하는 정적이 함수는 `IErrorInfo` 인터페이스를 클라이언트에 오류 정보를 제공 합니다.  
  
```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszDesc`  
 [in] 오류를 설명 하는 문자열입니다. 유니코드 버전 `Error` 지정 `lpszDesc` 형식의 **LPCOLESTR**; ANSI 버전의 형식을 지정 `LPCSTR`합니다.  
  
 `iid`  
 [in] 이 오류를 정의 하는 인터페이스의 IID 또는 `GUID_NULL` (기본값) 오류는 운영 체제에 의해 정의 된 경우.  
  
 `hRes`  
 [in] `HRESULT` 원하는, 호출자에 게 반환 합니다. 기본값은 0입니다. 에 대 한 자세한 내용은 `hRes`, 설명을 참조 하십시오.  
  
 `nID`  
 [in] 오류 설명 문자열 저장 된 리소스 식별자입니다. 이 값 까지의 0x0200 사이의 0xFFFF 내 해야 합니다. 디버그 빌드에서 **ASSERT** 경우 발생 합니다 `nID` 는 유효한 문자열 인덱싱되지 않습니다. 릴리스 빌드에서 오류 설명 문자열 "알 수 없는 오류가 발생 했습니다."로 설정 됩니다.  
  
 `dwHelpID`  
 [in] 오류에 대 한 도움말 컨텍스트 식별자입니다.  
  
 `lpszHelpFile`  
 [in] 경로 오류를 설명 하는 도움말 파일의 이름입니다.  
  
 `hInst`  
 [in] 리소스에 대 한 핸들입니다. 이 매개 변수는 기본적으로 **_AtlModule::GetResourceInstance**여기서 **_AtlModule** 의 인스턴스인 전역 [CAtlModule](../../atl/reference/catlmodule-class.md)합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다. 자세한 내용은 설명을 참조하세요.  
  
### <a name="remarks"></a>주의  
 호출 `Error`, 개체를 구현 해야는 `ISupportErrorInfo Interface` 인터페이스입니다.  
  
 하는 경우는 `hRes` 매개 변수는 다음&0;이 아니면 `Error` 의 값을 반환 `hRes`합니다. 경우 `hRes` 가&0;이 아니면 처음&4; 개 버전의 `Error` 반환 `DISP_E_EXCEPTION`합니다. 매크로의 결과 반환 하는 마지막 두 버전 **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**합니다.  
  
##  <a name="a-namegetobjectclsida--ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a>CComCoClass::GetObjectCLSID  
 개체의 CLSID를 검색 하는 일관 된 방법을 제공 합니다.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>반환 값  
 개체의 클래스 식별자입니다.  
  
##  <a name="a-namegetobjectdescriptiona--ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a>CComCoClass::GetObjectDescription  
 이 정적 함수에는 클래스 개체에 대 한 텍스트 설명을 가져옵니다.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>반환 값  
 클래스 개체의 설명입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 반환 **NULL**합니다. 이 메서드를 재정의할 수는 [DECLARE_OBJECT_DESCRIPTION](http://msdn.microsoft.com/library/32ac881c-97b1-44e2-a017-0e23eb99ac93) 매크로입니다. 예:  
  
 [!code-cpp[NVC_ATL_COM&#12;](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription`에 의해 호출 됩니다 **IComponentRegistrar::GetComponents**합니다. **IComponentRegistrar** 자동화 하는 인터페이스로 등록 하 고 개별 구성 요소 DLL의 등록을 취소할 수 있습니다. ATL 프로젝트 마법사와 구성 요소 관리자 개체를 만들 때 마법사는 자동으로 구현 된 **IComponentRegistrar** 인터페이스입니다. **IComponentRegistrar** Microsoft Transaction Server에서 주로 사용 됩니다.  
  
 ATL 프로젝트 마법사에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

