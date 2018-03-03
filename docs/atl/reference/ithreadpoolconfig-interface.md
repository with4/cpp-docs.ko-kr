---
title: "IThreadPoolConfig 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d967720778305eace4eff9ad8b2163456fb4bb46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig 인터페이스
이 인터페이스는 스레드 풀을 구성 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[GetSize](#getsize)|풀의 스레드 수를 가져오려면이 메서드를 호출 합니다.|  
|[GetTimeout](#gettimeout)|스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.|  
|[SetSize](#setsize)|풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.|  
|[SetTimeout](#settimeout)|스레드 풀에서 대기 하는 스레드를 종료 하는 시간 (밀리초)에 최대 시간을 설정 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 구현 하 여 [CThreadPool](../../atl/reference/cthreadpool-class.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
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
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
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
 [클래스](../../atl/reference/atl-classes.md)   
 [CThreadPool 클래스](../../atl/reference/cthreadpool-class.md)
