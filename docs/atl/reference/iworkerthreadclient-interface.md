---
title: "IWorkerThreadClient 인터페이스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IWorkerThreadClient
- ATL::IWorkerThreadClient
- IWorkerThreadClient
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 2127d13dc11edb353ef27396f3457dd9abdc4a99
ms.lasthandoff: 02/24/2017

---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient 인터페이스
`IWorkerThreadClient`클라이언트에서 구현 된 인터페이스는 [CWorkerThread](../../atl/reference/cworkerthread-class.md) 클래스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|이 개체와 연결 된 핸들을이 메서드를 구현 합니다.|  
|[실행](#execute)|이 개체와 연결 된 핸들에 신호가 전달 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.|  
  
## <a name="remarks"></a>주의  
 신호 핸들에 대 한 응답으로 작업자 스레드에서 실행 해야 하는 코드가 있는 경우에이 인터페이스를 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="a-nameclosehandlea--iworkerthreadclientclosehandle"></a><a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 이 개체와 연결 된 핸들을이 메서드를 구현 합니다.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>매개 변수  
 *hHandle*  
 닫을 수에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드에 전달 된 핸들이를 호출 하 여이 개체와 이전에 연결 되어 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예제  
 다음 코드에서는의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::CloseHandle`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities #&135;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="a-nameexecutea--iworkerthreadclientexecute"></a><a name="execute"></a>IWorkerThreadClient::Execute  
 이 개체와 연결 된 핸들에 신호가 전달 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwParam`  
 사용자 매개 변수입니다.  
  
 `hObject`  
 신호가 전송 되는 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 또는 실패 시 오류 HRESULT에 S_OK를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 핸들 및 DWORD/이 메서드에 전달 된 포인터를 호출 하 여이 개체와 이미 연결 되어 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.  
  
### <a name="example"></a>예제  
 다음 코드에서는의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::Execute`합니다.  
  
 [!code-cpp[NVC_ATL_Utilities #&136;](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)   
 [CWorkerThread 클래스](../../atl/reference/cworkerthread-class.md)

