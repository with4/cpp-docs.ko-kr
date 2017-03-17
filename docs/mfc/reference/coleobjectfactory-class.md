---
title: "COleObjectFactory 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
dev_langs:
- C++
helpviewer_keywords:
- OLE, class factory
- OLE class factory
- COleObjectFactory class
- objects [C++], creating OLE
- OLE objects
- object creation, OLE objects
- class factories, COleObjectFactory class
- OLE objects, creating
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 643d17ccdefb60b561e7e5488753a6dbf778c69f
ms.lasthandoff: 02/24/2017

---
# <a name="coleobjectfactory-class"></a>COleObjectFactory 클래스
서버, 자동화 개체, 문서와 같은 OLE 개체를 만드는 OLE 클래스 팩터리를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|`COleObjectFactory` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|반환 OLE 클래스이 팩터리가 만드는 개체의 ID입니다.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|컨트롤의 라이선스 유효 인지 여부를 확인 합니다.|  
|[COleObjectFactory::IsRegistered](#isregistered)|개체 팩터리 OLE 시스템 Dll으로 등록 되었는지 여부를 나타냅니다.|  
|[COleObjectFactory::Register](#register)|OLE 시스템 Dll이 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::RegisterAll](#registerall)|OLE 시스템 Dll 모든 응용 프로그램의 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::Revoke](#revoke)|이 개체 팩터리를 OLE 시스템 Dll 사용이 등록을 취소합니다.|  
|[COleObjectFactory::RevokeAll](#revokeall)|OLE 시스템 Dll에 있는 응용 프로그램의 개체 팩터리 등록을 취소합니다.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|OLE 시스템 레지스트리를이 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|OLE 시스템 레지스트리에 있는 모든 응용 프로그램의 개체 팩터리를 등록합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|컨트롤의 DLL에서 고유 키를 요청합니다.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|이 팩터리의 형식의 새 개체를 만드는 프레임 워크에 의해 호출 됩니다.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|컨트롤에 포함 되는 키 컨테이너에 포함 된 키와 일치 하는지 확인 합니다.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|컨트롤은 디자인 타임 사용에 대 한 라이선스를 갖고 있는지 확인 합니다.|  
  
## <a name="remarks"></a>주의  
 `COleObjectFactory` 클래스에는 다음과 같은 기능을 수행 하기 위한 멤버 함수:  
  
-   개체의 등록을 관리 합니다.  
  
-   에 게 알리고 OLE 개체가 실행 하는 메시지를 받을 준비가 런타임에 등록 뿐만 아니라 OLE 시스템 레지스터를 업데이트 합니다.  
  
-   디자인 타임에 사용이 허가 된 개발자에 게 있으며 런타임 시 사용이 허가 된 응용 프로그램에 컨트롤의 사용을 제한 하 여 라이선스를 적용 합니다.  
  
-   OLE 시스템 레지스트리를 컨트롤 개체 팩터리를 등록합니다.  
  
 개체를 만드는 방법에 대 한 자세한 내용은 문서를 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md) 및 [데이터 개체 및 데이터 소스: 생성 및 소멸](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)합니다. 등록에 대 한 자세한 문서를 참조 [등록](../../mfc/registration.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>COleObjectFactory::COleObjectFactory  
 생성 된 `COleObjectFactory` 팩터리의 목록에 추가 하는 개체를 등록 되지 않은 개체 팩터리로 초기화 합니다.  
  
```  
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    LPCTSTR lpszProgID);

 
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    int nFlags,  
    LPCTSTR lpszProgID);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 이 개체 팩터리를 나타내는 OLE 클래스 ID에 대 한 참조입니다.  
  
 `pRuntimeClass`  
 이 팩터리를 만들 수 있는 c + + 개체의 런타임 클래스에 대 한 포인터입니다.  
  
 `bMultiInstance`  
 단일 인스턴스 응용 프로그램의 여러 인스턴스를 지원할 수 있는지를 나타냅니다. 경우 **TRUE**, 개체를 만들 각 요청에 대 한 응용 프로그램의 여러 인스턴스가 시작 됩니다.  
  
 `nFlags`  
 다음 플래그 중 하나 이상을 포함 되어 있습니다.  
  
- **afxRegDefault** 스레딩 모델 ThreadingModel을 설정 하는 아파트 =.  
  
- **afxRegInsertable** 통해에 표시 되도록 컨트롤의 **개체 삽입** OLE 개체에 대 한 대화 상자입니다.  
  
- `afxRegApartmentThreading`스레딩 모델 레지스트리에 ThreadingModel 설정 하는 아파트 =.  
  
- **afxRegFreeThreading** 스레딩 모델 레지스트리에 ThreadingModel 설정 하는 무료 =.  
  
     두 개의 플래그를 결합할 수 `afxRegApartmentThreading` 및 `afxRegFreeThreading` ThreadingModel를 설정 하려면 = 둘 다. 참조 [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 스레딩 모델 등록에 대 한 자세한 내용은 합니다.  
  
 `lpszProgID`  
 "Microsoft Excel입니다."와 같은 일반 텍스트 프로그램 식별자를 포함 하는 문자열에 대 한 포인터  
  
### <a name="remarks"></a>주의  
 그러나 개체를 사용 하려면 등록 해야 합니다.  
  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getclassid"></a>COleObjectFactory::GetClassID  
 이 팩터리를 나타내는 OLE 클래스 ID에 대 한 참조를 반환 합니다.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 팩터리 OLE 클래스 ID에 대 한 참조를 나타냅니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getlicensekey"></a>COleObjectFactory::GetLicenseKey  
 컨트롤의 DLL에서 고유한 라이선스 키를 요청 하 고에 저장 된 `BSTR` 가리키는 `pbstrKey`합니다.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwReserved`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `pbstrKey`  
 에 대 한 포인터는 `BSTR` 하는 라이선스 키를 저장 합니다.  
  
### <a name="return-value"></a>반환 값  
 라이선스 키 문자열이 아닌 경우 0이 아닌 **NULL**그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 0을 반환 하 고 저장의 경우 nothing는 `BSTR`합니다. MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤 컨트롤의 라이선스 키를 검색 하는 재정의 제공 합니다.  
  
##  <a name="islicensevalid"></a>COleObjectFactory::IsLicenseValid  
 컨트롤의 라이선스 유효 인지 여부를 확인 합니다.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 successul; 그렇지 않으면 false입니다.  
  
##  <a name="isregistered"></a>COleObjectFactory::IsRegistered  
 공장 OLE 시스템 Dll에 등록 되어 있으면&0;이 아닌 값을 반환 합니다.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>반환 값  
 공장 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="oncreateobject"></a>COleObjectFactory::OnCreateObject  
 새 개체를 만드는 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>반환 값  
 만든된 개체에 대 한 포인터입니다. 실패 하는 경우 메모리 예외를 throw 할 수 것입니다.  
  
### <a name="remarks"></a>주의  
 이외의 다른 항목에서 개체를 만들려면이 함수를 재정의 하는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 생성자에 전달 합니다.  
  
##  <a name="register"></a>COleObjectFactory::Register  
 OLE 시스템 Dll이 개체 팩터리를 등록합니다.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>반환 값  
 공장 성공적으로 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램 시작 시.  
  
##  <a name="registerall"></a>COleObjectFactory::RegisterAll  
 OLE 시스템 Dll 모든 응용 프로그램의 개체 팩터리를 등록합니다.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리를 성공적으로 등록 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램 시작 시.  
  
##  <a name="revoke"></a>COleObjectFactory::Revoke  
 이 개체 팩터리를 OLE 시스템 Dll 사용이 등록을 취소합니다.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.  
  
##  <a name="revokeall"></a>COleObjectFactory::RevokeAll  
 모든 OLE 시스템 Dll에 있는 응용 프로그램의 개체 팩터리 등록 취소합니다.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>주의  
 응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.  
  
##  <a name="unregisterall"></a>COleObjectFactory::UnregisterAll  
 모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 TRUE이고, 실패하면 FALSE입니다.  
  
##  <a name="updateregistry"></a>COleObjectFactory::UpdateRegistry  
 OLE 시스템 레지스트리에 있는 모든 응용 프로그램의 개체 팩터리를 등록합니다.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProgID`  
 "Excel.Document.5."와 같은 사람이 읽을 수 있는 프로그램 식별자를 포함 하는 문자열에 대 한 포인터  
  
 `bRegister`  
 컨트롤 클래스의 개체 팩터리를 등록 인지 확인 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 대 한 두 가지 형태 중 간략 한 논의 수행합니다.  
  
- **UpdateRegistry (** `lpszProgID` **)** OLE 시스템 레지스트리를이 개체 팩터리를 등록 합니다. 이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램 시작 시.  
  
- **UpdateRegistry (** `bRegister` **)** 이 함수의 형식으로 재정의 될 수 있습니다. 경우 `bRegister` 는 **TRUE**,이 함수는 시스템 레지스트리에 컨트롤 클래스를 등록 합니다. 그렇지 않으면 클래스 등록 취소합니다.  
  
     MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤이 순수 가상 함수에 대 한 재정의 제공 합니다.  
  
##  <a name="updateregistryall"></a>COleObjectFactory::UpdateRegistryAll  
 OLE 시스템 레지스트리에 있는 모든 응용 프로그램의 개체 팩터리를 등록합니다.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegister`  
 컨트롤 클래스의 개체 팩터리를 등록 인지 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 팩터리를 성공적으로 업데이트 됩니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 호출한 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램 시작 시.  
  
##  <a name="verifylicensekey"></a>COleObjectFactory::VerifyLicenseKey  
 컨테이너는 OLE 컨트롤을 사용 하 여 라이선스를 갖고 있는지 확인 합니다.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrKey`  
 A `BSTR` 라이선스 문자열의 컨테이너의 버전을 저장 합니다.  
  
### <a name="return-value"></a>반환 값  
 런타임 라이선스 유효 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 버전을 호출 하 여 [GetLicenseKey](#getlicensekey) 컨트롤의 복사본을 얻으려면과 문자열을 비교 하 고 라이선스 문자열의 `bstrKey`합니다. 두 문자열이 일치 하는 경우 반환 0이 아닌 값입니다. 그렇지 않으면 0을 반환 합니다.  
  
 라이선스의 사용자 지정된 확인 기능을 제공 하려면이 함수를 재정의할 수 있습니다.  
  
 함수 [VerifyUserLicense](#verifyuserlicense) 디자인 타임 라이선스를 확인 합니다.  
  
##  <a name="verifyuserlicense"></a>COleObjectFactory::VerifyUserLicense  
 OLE 컨트롤에 대 한 디자인 타임 라이선스를 확인합니다.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>반환 값  
 디자인 타임 라이선스 유효 하면 0이 아니고 그렇지 않으면 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)

