---
title: "IRunnableObjectImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a9b2698c195ac5bd709e6d40d3c30008d3fa26d4
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl 클래스
이 클래스는 구현 **IUnknown** 의 기본 구현을 제공 하 고는 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IRunnableObjectImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|실행 중인 컨트롤의 CLSID를 반환합니다. CLSID 설정 하는 ATL 구현 `GUID_NULL` 반환 **E_UNEXPECTED**합니다.|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|컨트롤이 실행 되 고 있는지 확인 합니다. ATL 구현은 **TRUE**합니다.|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|실행 중 상태로 컨트롤을 잠급니다. ATL 구현은 `S_OK`합니다.|  
|[IRunnableObjectImpl::Run](#run)|강제로 실행 합니다. ATL 구현은 `S_OK`합니다.|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|컨트롤이 포함 되어 있음을 나타냅니다. ATL 구현은 `S_OK`합니다.|  
  
## <a name="remarks"></a>주의  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) 인터페이스를 사용 하는 컨테이너에 컨트롤 실행 되 고 있는지 확인 하 고, 실행 또는 실행 중 상태로 잠글 수 있습니다. 클래스 `IRunnableObjectImpl` 이 인터페이스의 기본 구현을 제공 하 고 구현 **IUnknown** 장치에서 디버그 덤프를 정보를 전송 하 여 빌드합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="getrunningclass"></a>IRunnableObjectImpl::GetRunningClass  
 실행 중인 컨트롤의 CLSID를 반환합니다.  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>반환 값  
 ATL 구현 설정 \* *lpClsid* 를 `GUID_NULL` 반환 **E_UNEXPECTED**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="isrunning"></a>IRunnableObjectImpl::IsRunning  
 컨트롤이 실행 되 고 있는지 확인 합니다.  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>반환 값  
 ATL 구현은 **TRUE**합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="lockrunning"></a>IRunnableObjectImpl::LockRunning  
 실행 중 상태로 컨트롤을 잠급니다.  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>반환 값  
 ATL 구현은 `S_OK`합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="run"></a>IRunnableObjectImpl::Run  
 강제로 실행 합니다.  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>반환 값  
 ATL 구현은 `S_OK`합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setcontainedobject"></a>IRunnableObjectImpl::SetContainedObject  
 컨트롤이 포함 되어 있음을 나타냅니다.  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>반환 값  
 ATL 구현은 `S_OK`합니다.  
  
### <a name="remarks"></a>주의  
 참조 [IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

