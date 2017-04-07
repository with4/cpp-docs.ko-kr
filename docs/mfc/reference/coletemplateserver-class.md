---
title: "COleTemplateServer 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleTemplateServer
- AFXDISP/COleTemplateServer
- AFXDISP/COleTemplateServer::COleTemplateServer
- AFXDISP/COleTemplateServer::ConnectTemplate
- AFXDISP/COleTemplateServer::Unregister
- AFXDISP/COleTemplateServer::UpdateRegistry
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [C++], implementing
- servers, OLE
- OLE server applications, managing server documents
- link containers [C++]
- visual editing, servers
- OLE link containers
- COleTemplateServer class
- OLE server applications, COleTemplateServer class
ms.assetid: 47a2887d-8162-4993-a842-a784177c7f5c
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea82939cd0e8a8ba5612c65d238be8ae9996ef08
ms.lasthandoff: 02/24/2017

---
# <a name="coletemplateserver-class"></a>COleTemplateServer 클래스
OLE 비주얼 편집 서버, 자동화 서버 및 링크 컨테이너(포함에 대한 링크를 지원하는 응용 프로그램)에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleTemplateServer : public COleObjectFactory  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleTemplateServer::COleTemplateServer](#coletemplateserver)|`COleTemplateServer` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleTemplateServer::ConnectTemplate](#connecttemplate)|문서 서식 파일을 연결 하는 기본 `COleObjectFactory` 개체입니다.|  
|[COleTemplateServer::Unregister](#unregister)|관련된 문서 서식 파일을 등록 취소합니다.|  
|[COleTemplateServer::UpdateRegistry](#updateregistry)|OLE 시스템 레지스트리에 문서 유형을 등록합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 클래스에서 파생 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md); 일반적으로 사용할 수 있습니다 `COleTemplateServer` 사용자 고유의 클래스를 파생 하는 대신 직접. `COleTemplateServer`사용 하 여 한 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 서버 문서를 관리 하는 개체입니다. 사용 하 여 `COleTemplateServer` 전체 서버, 즉, 독립 실행형 응용 프로그램으로 실행할 수 있는 서버를 구현 하는 경우. 단일 문서 인터페이스 (SDI) 응용 프로그램은 지원 하지만 전체 서버는 일반적으로 여러 문서 MDI (인터페이스) 응용 프로그램입니다. 하나의 `COleTemplateServer` 응용 프로그램이 지 원하는 서버 문서의 각 형식에 대 한 개체가 필요 합니다; 즉, 서버 응용 프로그램에서 워크시트 및 차트 모두를 지 원하는 경우 있습니다 있어야 두 `COleTemplateServer` 개체입니다.  
  
 `COleTemplateServer`재정의 `OnCreateInstance` 멤버 함수에 정의 된 `COleObjectFactory`합니다. 이 멤버 함수는 올바른 형식의 c + + 개체를 만드는 프레임 워크에 의해 호출 됩니다.  
  
 서버에 대 한 자세한 내용은 문서를 참조 하십시오. [서버: 서버 구현](../../mfc/servers-implementing-a-server.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md)  
  
 `COleTemplateServer`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="coletemplateserver"></a>COleTemplateServer::COleTemplateServer  
 `COleTemplateServer` 개체를 생성합니다.  
  
```  
COleTemplateServer();
```  
  
### <a name="remarks"></a>주의  
 에 대 한 간략 한 설명은의 사용은 `COleTemplateServer` 클래스를 참조는 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md) 클래스 개요.  
  
##  <a name="connecttemplate"></a>COleTemplateServer::ConnectTemplate  
 가 가리키는 문서 서식 파일을 연결 `pDocTemplate` 기본 [COleObjectFactory](../../mfc/reference/coleobjectfactory-class.md) 개체입니다.  
  
```  
void ConnectTemplate(
    REFCLSID clsid,  
    CDocTemplate* pDocTemplate,  
    BOOL bMultiInstance);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 서식 파일을 요청 하는 OLE 클래스 ID에 대 한 참조입니다.  
  
 `pDocTemplate`  
 서식 파일에 대 한 포인터입니다.  
  
 `bMultiInstance`  
 단일 인스턴스 응용 프로그램의 여러 인스턴스를 지원할 수 있는지를 나타냅니다. 경우 **TRUE**, 개체를 만들 각 요청에 대 한 응용 프로그램의 여러 인스턴스가 시작 됩니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="unregister"></a>COleTemplateServer::Unregister  
 관련된 문서 서식 파일을 등록 취소합니다.  
  
```  
BOOL Unregister();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 TRUE이고, 실패하면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 EnterRemarks  
  
##  <a name="updateregistry"></a>COleTemplateServer::UpdateRegistry  
 문서 템플릿 문자열에서 파일 형식 정보를 로드 하 고 OLE 시스템 레지스트리에 해당 정보를 배치 합니다.  
  
```  
void UpdateRegistry(
    OLE_APPTYPE nAppType = OAT_INPLACE_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL,  
    BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nAppType`  
 값은 **OLE_APPTYPE** AFXDISP에 정의 된 열거형입니다.&8;. 다음 값 중 하나를 가질 수 있습니다.  
  
- `OAT_INPLACE_SERVER`서버에는 전체 서버 사용자 인터페이스에 있습니다.  
  
- `OAT_SERVER`서버 지원만 포함 합니다.  
  
- `OAT_CONTAINER`컨테이너는 포함 된 개체에 대 한 링크를 지원합니다.  
  
- `OAT_DISPATCH_OBJECT`개체는 `IDispatch`-가능 합니다.  
  
- **OAT_DOC_OBJECT_SERVER** 서버 모두를 지원 합니다. 포함 및 구성 요소 문서 개체 모델입니다.  
  
 `rglpszRegister`  
 항목이 없는 경우에 레지스트리에 기록 된 항목의 목록입니다.  
  
 `rglpszOverwrite`  
 위의 모든 항목의 존재 여부에 관계 없이 레지스트리로 작성 된 목록 항목입니다.  
  
 `bRegister`  
 클래스를 등록 인지 확인 합니다. 경우 `bRegister` 는 **TRUE**, 클래스는 시스템 레지스트리에 등록 됩니다. 그렇지 않으면 클래스 등록 취소합니다.  
  
### <a name="remarks"></a>주의  
 등록 정보에 대 한 호출을 사용 하 여 로드는 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)합니다. 검색할 부분 문자열에는 인덱스에 의해 식별 **regFileTypeId**, **regFileTypeName**, 및 **fileNewName**에 설명 된 대로 `GetDocString` 페이지를 참조 합니다.  
  
 하는 경우는 **regFileTypeId** 부분 문자열은 비어 있거나에 대 한 호출 `GetDocString` 기타 다른 이유로,이 함수가 실패 하면 실패 하 고 레지스트리에서 파일 정보를 입력 하지 않으면.  
  
 인수에 있는 정보 `rglpszRegister` 및 `rglpszOverwrite` 호출을 통해 레지스트리에 기록 [AfxOleRegisterServerClass](application-control.md#afxoleregisterserverclass)합니다. 두 개의 인수는 등록 되는 기본 정보를 **NULL**, 대부분의 응용 프로그램에 적합 합니다. 이러한 인수에 있는 정보의 구조에 대 한 정보를 참조 하십시오. `AfxOleRegisterServerClass`합니다.  
  
 자세한 내용은 참조 [IDispatch 인터페이스를 구현](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [COleObjectFactory 클래스](../../mfc/reference/coleobjectfactory-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerDoc 클래스](../../mfc/reference/coleserverdoc-class.md)   
 [COleServerItem 클래스](../../mfc/reference/coleserveritem-class.md)

