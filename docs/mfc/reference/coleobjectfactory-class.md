---
title: COleObjectFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd68493c9be5eb0bff63504cf49b38b9a2f216d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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
|[COleObjectFactory::IsRegistered](#isregistered)|개체 팩터리 OLE 시스템 Dll에 등록 되었는지 여부를 나타냅니다.|  
|[COleObjectFactory::Register](#register)|OLE 시스템 Dll이 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::RegisterAll](#registerall)|OLE 시스템 Dll 모든 응용 프로그램의 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::Revoke](#revoke)|OLE 시스템 Dll이 개체 팩터리이 등록을 취소합니다.|  
|[COleObjectFactory::RevokeAll](#revokeall)|OLE 시스템 Dll에 있는 응용 프로그램의 개체 팩터리 등록을 취소합니다.|  
|[COleObjectFactory::UnregisterAll](#unregisterall)|모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|OLE 시스템 레지스트리를이 개체 팩터리를 등록합니다.|  
|[COleObjectFactory::UpdateRegistryAll](#updateregistryall)|OLE 시스템 레지스트리에 모든 응용 프로그램의 개체 팩터리를 등록 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|컨트롤의 DLL에서 고유 키를 요청합니다.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|이 팩터리의 형식의 새 개체를 만들기 위해 프레임 워크에서 호출 됩니다.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|컨트롤에 포함 된 키 컨테이너에 포함 된 키와 일치 하는지 확인 합니다.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|컨트롤은 디자인 타임 사용에 대 한 라이선스를 갖고 있는지 확인 합니다.|  
  
## <a name="remarks"></a>설명  
 `COleObjectFactory` 클래스에는 다음과 같은 기능을 수행 하기 위한 멤버 함수:  
  
-   개체의 등록을 관리 합니다.  
  
-   개체 실행 중이 고 메시지를 받을 준비가 OLE에 알려 주는 런타임에 등록 뿐만 아니라 OLE 시스템 레지스터를 업데이트 합니다.  
  
-   디자인 타임에 사용이 허가 된 개발자에 게 유용 하 고 런타임 시 사용이 허가 된 응용 프로그램에 제어의 사용을 제한 하 여 라이선스를 적용 합니다.  
  
-   OLE 시스템 레지스트리로 제어 개체 팩터리를 등록합니다.  
  
 개체 만들기에 대 한 자세한 내용은 문서를 참조 [데이터 개체 및 데이터 소스 (OLE)](../../mfc/data-objects-and-data-sources-ole.md) 및 [데이터 개체 및 데이터 소스: 생성 및 소멸](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)합니다. 등록에 대 한 자세한 문서를 참조 [등록](../../mfc/registration.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 생성 된 `COleObjectFactory` 개체는 등록 되지 않은 개체 팩터리로 초기화 하 고 팩터리 목록에 추가 합니다.  
  
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
 단일 인스턴스 응용 프로그램의 여러 인스턴스를 지원할 수 있는지 여부를 나타냅니다. 경우 **TRUE**, 개체를 만드는 각 요청에 대 한 응용 프로그램의 여러 인스턴스를 시작 합니다.  
  
 `nFlags`  
 다음과 같은 플래그 중 하나 이상을 포함 되어 있습니다.  
  
- **afxRegDefault** ThreadingModel을 설정 하는 스레딩 모델이 아파트 = 합니다.  
  
- **afxRegInsertable** 에 표시를 제어할 수 있습니다는 **개체 삽입** OLE 개체에 대 한 대화 상자.  
  
- `afxRegApartmentThreading` ThreadingModel 레지스트리에서 설정 하는 스레딩 모델이 아파트 = 합니다.  
  
- **afxRegFreeThreading** ThreadingModel 레지스트리에서 스레딩 모델을 설정 합니다. 무료 = 합니다.  
  
     두 플래그를 결합할 수 있습니다 `afxRegApartmentThreading` 및 `afxRegFreeThreading` ThreadingModel 설정할 = Both입니다. 참조 [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) 스레딩 모델 등록에 대 한 자세한 내용은 Windows sdk입니다.  
  
 `lpszProgID`  
 "Microsoft Excel입니다."와 같은 구두 프로그램 식별자를 포함 하는 문자열에 대 한 포인터  
  
### <a name="remarks"></a>설명  
 그러나 개체를 사용 하려면 등록 해야 합니다.  
  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows sdk에서입니다.  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 이 팩터리를 나타내는 OLE 클래스 ID에 대 한 참조를 반환 합니다.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 팩터리가 OLE 클래스 ID에 대 한 참조를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows sdk에서입니다.  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
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
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 0을 반환 하 고 nothing에 저장 된 `BSTR`합니다. MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤에서 컨트롤의 라이선스 키를 검색 하는 재정의 제공 합니다.  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 컨트롤의 라이선스 유효 인지 여부를 확인 합니다.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 successul; 그렇지 않으면 false입니다.  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 공장 OLE 시스템 Dll에 등록 되어 있으면 0이 아닌 값을 반환 합니다.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>반환 값  
 공장 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 새 개체를 만드는 프레임 워크에서 호출 됩니다.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>반환 값  
 만든된 개체에 대 한 포인터입니다. 실패할 경우 메모리 예외가 발생할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 이 함수 이외의 항목에서 개체를 만들고를 재정의 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 생성자에 전달 합니다.  
  
##  <a name="register"></a>  COleObjectFactory::Register  
 OLE 시스템 Dll이 개체 팩터리를 등록합니다.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리가 성공적으로 등록 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 하 여 호출 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 OLE 시스템 Dll 모든 응용 프로그램의 개체 팩터리를 등록합니다.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리 성공적으로 등록 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 하 여 호출 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.  
  
##  <a name="revoke"></a>  COleObjectFactory::Revoke  
 OLE 시스템 Dll이 개체 팩터리이 등록을 취소합니다.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>설명  
 응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 모든 OLE 시스템 Dll에 있는 응용 프로그램의 개체 팩터리 등록을 취소합니다.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>설명  
 응용 프로그램을 종료 하기 전에이 함수를 자동으로 호출 하는 프레임 워크입니다. 필요한 경우 재정의에서 호출할 [CWinApp::ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance)합니다.  
  
##  <a name="unregisterall"></a>  COleObjectFactory::UnregisterAll  
 모든 응용 프로그램의 개체 팩터리를 등록 취소합니다.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 TRUE이고, 실패하면 FALSE입니다.  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 OLE 시스템 레지스트리에 모든 응용 프로그램의 개체 팩터리를 등록 합니다.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszProgID`  
 "Excel.Document.5" 등의 사용자를 읽을 수 있는 프로그램 식별자를 포함 하는 문자열에 대 한 포인터  
  
 `bRegister`  
 컨트롤 클래스의 개체 팩터리를 등록 해야 하는지를 결정 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수에 대 한 두 가지 형태 중 간략 한 토론을 수행합니다.  
  
- **UpdateRegistry (** `lpszProgID` **)** OLE 시스템 레지스트리에이 개체 팩터리를 등록 합니다. 이 함수는 일반적으로 하 여 호출 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.  
  
- **UpdateRegistry (** `bRegister` **)** 는이 함수의 재정의 될 수 있습니다. 경우 `bRegister` 은 **TRUE**,이 함수는 시스템 레지스트리의 control 클래스에 등록 합니다. 그렇지 않으면 클래스 등록 취소합니다.  
  
     MFC ActiveX 컨트롤을 사용 하 여 프로젝트를 만드는 경우 컨트롤이 순수 가상 함수 재정의 제공 합니다.  
  
##  <a name="updateregistryall"></a>  COleObjectFactory::UpdateRegistryAll  
 OLE 시스템 레지스트리에 모든 응용 프로그램의 개체 팩터리를 등록 합니다.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegister`  
 컨트롤 클래스의 개체 팩터리를 등록 해야 하는지를 결정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적으로 업데이트 되는 팩터리 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 하 여 호출 [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 응용 프로그램이 시작 될 때입니다.  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 컨테이너는 OLE 컨트롤을 사용 하려면 라이선스를 갖고 있는지 확인 합니다.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>매개 변수  
 `bstrKey`  
 A `BSTR` 라이선스 문자열의 컨테이너의 버전을 저장 합니다.  
  
### <a name="return-value"></a>반환 값  
 런타임 라이선스 유효 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 버전을 호출 하 여 [GetLicenseKey](#getlicensekey) 컨트롤의 복사본을 가져오려면 라이선스 문자열의 해시와 비교의 문자열로 `bstrKey`합니다. 두 문자열이 일치 하는 경우 함수가 0이 아닌 값을 반환 그렇지 않으면 0을 반환 합니다.  
  
 라이선스의 사용자 지정된 확인 기능을 제공 하려면이 함수를 재정의할 수 있습니다.  
  
 함수 [VerifyUserLicense](#verifyuserlicense) 디자인 타임 라이선스를 확인 합니다.  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 OLE 컨트롤에 대 한 디자인 타임 라이선스를 확인합니다.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>반환 값  
 디자인 타임 라이선스가 잘못 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer 클래스](../../mfc/reference/coletemplateserver-class.md)
