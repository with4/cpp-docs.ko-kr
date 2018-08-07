---
title: IWorkerThreadClient 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86e35910469128ecaf38751d6db73094adf3422e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884727"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient 인터페이스
`IWorkerThreadClient` 클라이언트에서 구현 된 인터페이스를 [CWorkerThread](../../atl/reference/cworkerthread-class.md) 클래스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|이 개체와 연결 된 핸들을 종료 하려면이 메서드를 구현 합니다.|  
|[실행](#execute)|이 개체를 사용 하 여 연결 핸들에 신호 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.|  
  
## <a name="remarks"></a>설명  
 신호 핸들에 대 한 응답으로 작업자 스레드에서 실행 해야 하는 코드가 있는 경우이 인터페이스를 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 와 atlutil.h  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 이 개체와 연결 된 핸들을 종료 하려면이 메서드를 구현 합니다.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>매개 변수  
 *hHandle*  
 핸들을 닫아야입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여이 개체를 사용 하 여 이전에 연결 된이 메서드에 전달 된 핸들이 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예  
 다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::CloseHandle`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 이 개체를 사용 하 여 연결 핸들에 신호 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwParam*  
 사용자 매개 변수입니다.  
  
 *hObject*  
 신호에 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여이 개체를 사용 하 여 이전에 연관 된 핸들과이 메서드에 전달 되는 DWORD/포인터 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예  
 다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::Execute`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CWorkerThread 클래스](../../atl/reference/cworkerthread-class.md)
