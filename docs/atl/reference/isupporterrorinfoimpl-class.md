---
title: "ISupportErrorInfoImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs: C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 61e8dc6b277f8eb59ade428d3ef8ea3dd5c083ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl 클래스
이 클래스의 기본 구현을 제공는 [ISupportErrorInfo 인터페이스](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) 단일 인터페이스만 개체에는 오류를 생성 하는 경우에 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>매개 변수  
 `piid`  
 지 원하는 인터페이스의 IID에 대 한 포인터 [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|인터페이스에서 식별할지 여부를 나타냅니다. `riid` 지원는 [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) 인터페이스입니다.|  
  
## <a name="remarks"></a>설명  
 [ISupportErrorInfo 인터페이스](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) 하면 클라이언트에 오류 정보를 반환할 수 있습니다. 사용 하는 개체 **IErrorInfo** 구현 해야 **ISupportErrorInfo**합니다.  
  
 클래스 `ISupportErrorInfoImpl` 의 기본 구현을 제공 **ISupportErrorInfo** 단일 인터페이스만 개체에는 오류를 생성 하는 경우에 사용할 수 있습니다. 예:  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 인터페이스에서 식별할지 여부를 나타냅니다. `riid` 지원는 [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) 인터페이스입니다.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>설명  
 참조 [ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) in the Windows SDK입니다.  
  
##  <a name="getsize"></a>IThreadPoolConfig::GetSize  
 풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>매개 변수  
 `pnNumThreads`  
 [out] 성공할 경우 풀의 스레드 수를 수신 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>매개 변수  
 `pdwMaxWait`  
 [out] 성공할 경우 스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에 최대 시간을 수신 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNumThreads`  
 스레드 풀의 요청된 수입니다.  
  
 경우 `nNumThreads` 가 음수 이면 절대값이 곱합니다 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수입니다.  
  
 경우 `nNumThreads` 0 이면 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) 스레드의 총 개수를 가져올 컴퓨터의 프로세서 수를 곱합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에 최대 시간을 설정 하려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMaxWait`  
 스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에 요청 된 최대 시간입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
