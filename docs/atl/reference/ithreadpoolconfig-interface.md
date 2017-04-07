---
title: "IThreadPoolConfig 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 24
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
ms.openlocfilehash: e10885373442890978feff42cda99309692a21d0
ms.lasthandoff: 02/24/2017

---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig 인터페이스
이 인터페이스는 스레드 풀을 구성 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
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
|[GetTimeout](#gettimeout)|스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.|  
|[SetSize](#setsize)|풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.|  
|[SetTimeout](#settimeout)|스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
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
 [out] 성공 풀의 스레드 수를 수신 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&134;](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 가져오려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>매개 변수  
 `pdwMaxWait`  
 [out] 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 받으면 성공 하는 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예제  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 풀의 스레드 수를 설정 하려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNumThreads`  
 스레드 풀의 요청된 수입니다.  
  
 경우 `nNumThreads` 가 음수 이면 절대값이 곱할 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수입니다.  
  
 경우 `nNumThreads` 가&0; 이면 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) 스레드의 총 개수를 가져올 컴퓨터에서 프로세서의 수를 곱합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예제  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에는 최대 시간을 설정 하려면이 메서드를 호출 합니다.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMaxWait`  
 스레드 풀 스레드를 종료를 대기 하는 시간 (밀리초)에 대 한 요청 된 최대 시간입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="example"></a>예제  
 참조 [IThreadPoolConfig::GetSize](#getsize)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CThreadPool 클래스](../../atl/reference/cthreadpool-class.md)

