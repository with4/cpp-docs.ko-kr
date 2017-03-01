---
title: "CAtlComModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlComModule
- CAtlComModule
- ATL::CAtlComModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b933b5388fccc2dc0e31d035aa7eb56de3b1866
ms.lasthandoff: 02/24/2017

---
# <a name="catlcommodule-class"></a>CAtlComModule 클래스
이 클래스는 COM 서버 모듈을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|생성자입니다.|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|형식 라이브러리를 등록 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|개체 맵의 각 개체의 등록을 취소 하려면이 메서드를 호출 합니다.|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|형식 라이브러리 등록을 취소 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 `CAtlComModule`모듈의 구성 요소에 액세스 하는 클라이언트는 COM 서버 모듈을 구현 합니다.  
  
 이 클래스는 사용 되지 않는 대신 [CComModule](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용 되는 클래스 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-namecatlcommodulea--catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>CAtlComModule::CAtlComModule  
 생성자입니다.  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>주의  
 모듈을 초기화합니다.  
  
##  <a name="a-namedtora--catlcommodulecatlcommodule"></a><a name="dtor"></a>CAtlComModule:: ~ CAtlComModule  
 소멸자입니다.  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>주의  
 모든 클래스 팩터리를 해제합니다.  
  
##  <a name="a-nameregisterservera--catlcommoduleregisterserver"></a><a name="registerserver"></a>CAtlComModule::RegisterServer  
 개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트 하려면이 메서드를 호출 합니다.  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 형식 라이브러리를 등록 하면 TRUE입니다. 기본값은 FALSE입니다.  
  
 `pCLSID`  
 등록할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체를 등록할 경우.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 전역 함수를 호출 [AtlComModuleRegisterServer](http://msdn.microsoft.com/library/d11a0c91-0c56-4b1b-a5f5-1287970f798b)합니다.  
  
##  <a name="a-nameregistertypeliba--catlcommoduleregistertypelib"></a><a name="registertypelib"></a>CAtlComModule::RegisterTypeLib  
 형식 라이브러리를 등록 하려면이 메서드를 호출 합니다.  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIndex`  
 형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 시스템 레지스트리를 형식 라이브러리에 대 한 정보를 추가합니다. 여러 개의 형식 라이브러리를 포함 하는 모듈 인스턴스를이 메서드의 첫 번째 버전 사용 하 여 지정 된 형식 라이브러리를 사용 해야 합니다.  
  
##  <a name="a-nameunregisterservera--catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>CAtlComModule::UnregisterServer  
 개체 맵의 각 개체의 등록을 취소 하려면이 메서드를 호출 합니다.  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 TRUE 이면 등록 취소할 형식 라이브러리입니다. 기본값은 FALSE입니다.  
  
 `pCLSID`  
 등록 취소할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체는가 등록 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 전역 함수를 호출 [AtlComModuleUnregisterServer](http://msdn.microsoft.com/library/c4ef3da4-def7-4aaf-b005-573a02e389d5)합니다.  
  
##  <a name="a-nameunregistertypeliba--catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib  
 형식 라이브러리 등록을 취소 하려면이 메서드를 호출 합니다.  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIndex`  
 형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다.  
  
### <a name="remarks"></a>주의  
 시스템 레지스트리에서 형식 라이브러리에 대 한 정보를 제거합니다. 여러 개의 형식 라이브러리를 포함 하는 모듈 인스턴스를이 메서드의 첫 번째 버전 사용 하 여 지정 된 형식 라이브러리를 사용 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [클래스 개요](../../atl/atl-class-overview.md)

