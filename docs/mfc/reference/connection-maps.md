---
title: 연결 맵 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 475314edba2a11535349991db644a4915e352ae7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372840"
---
# <a name="connection-maps"></a>연결 맵
OLE 컨트롤은 다른 응용 프로그램에 대 한 인터페이스를 노출할 수 있습니다. 이러한 인터페이스는이 컨트롤에는 컨테이너에서의 액세스만을 허용 합니다. OLE 컨트롤을 다른 OLE 개체의 외부 인터페이스에 액세스 하려는 경우 한 연결 지점을 설정 되어야 합니다. 이 연결점에는 나가는 이벤트 맵 또는 알림 함수 등의 외부 디스패치 맵에 대 한 액세스를 제어할 수 있습니다.  
  
 Microsoft Foundation Class 라이브러리는 프로그래밍 모델을 지 원하는 연결 지점을 제공 합니다. 이 모델에서는 "연결 매핑되 는" 인터페이스 또는 OLE 컨트롤에 대 한 연결점을 나타내는 데 사용 됩니다. 연결 맵 각 연결 지점에 대 한 매크로 포함합니다. 연결 맵에 자세한 내용은 참조는 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) 클래스입니다.  
  
 일반적으로 컨트롤에서 두 개의 연결 지점 지원 됩니다: 이벤트 속성 알림입니다. 이러한 작업으로 구현 됩니다는 `COleControl` 기본 클래스 및 컨트롤 기록기에 의해 추가 작업이 필요 합니다. 클래스에서 구현 하려는 모든 추가 연결 지점은 수동으로 추가 해야 합니다. 연결 맵 및 포인트를 지원 하려면 MFC 다음 매크로 제공 합니다.  
  
### <a name="connection-map-declaration-and-demarcation"></a>연결 맵 선언 및 구분  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|(클래스 선언에 사용 해야 합니다)는 추가 연결 지점을 구현 하는 포함 된 클래스를 선언 합니다.|  
|[END_CONNECTION_PART](#end_connection_part)|(클래스 선언에 사용 해야 합니다) 연결 지점의 선언을 종료 합니다.|  
|[CONNECTION_IID](#connection_iid)|컨트롤의 연결 지점의 인터페이스 ID를 지정합니다.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|연결 맵이 클래스 (클래스 선언에 사용 해야 합니다)에서 사용 되는 선언 합니다.|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 시작 합니다.|  
|[END_CONNECTION_MAP](#end_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 종료 합니다.|  
|[CONNECTION_PART](#connection_part)|컨트롤의 연결 맵을 연결점을 지정합니다.|  
  
 다음 함수는 싱크 설정 하 고 연결 지점을 사용 하 여 연결을 끊기 지원:  
  
### <a name="initializationtermination-of-connection-points"></a>연결 지점의 초기화/종료  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|원본 및 싱크 간에 연결을 설정 합니다.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|원본 서버와 싱크 간의 연결을 중단합니다.|  
  
##  <a name="begin_connection_part"></a>  BEGIN_CONNECTION_PART  
 사용 하 여는 `BEGIN_CONNECTION_PART` 매크로를 추가 연결 지점 이벤트와 속성 알림 연결 지점 외의 정의 시작 합니다.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 연결점 컨트롤 클래스의 이름을 지정 합니다.  
  
 *localClass*  
 연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.  
  
### <a name="remarks"></a>설명  
 클래스 멤버 함수를 정의 하는 선언 (.h) 파일에서 시작 연결점은 `BEGIN_CONNECTION_PART` 매크로 다음 추가 `CONNECTION_IID` 매크로 다른 멤버 함수를 구현 하 고 연결 지점 맵을 완료 합니다. 와 `END_CONNECTION_PART` 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="end_connection_part"></a>  END_CONNECTION_PART  
 연결 지점의 선언을 종료합니다.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 *localClass*  
 연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="connection_iid"></a>  CONNECTION_IID  
 사이 사용 된 `BEGIN_CONNECTION_PART` 및 `END_CONNECTION_PART` OLE 컨트롤에서 지 원하는 연결 지점에 대 한 인터페이스 ID를 정의 하는 매크로입니다.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 연결 지점에서 호출 하는 인터페이스의 인터페이스 ID입니다.  
  
### <a name="remarks"></a>설명  
 `iid` 인수는 ID에 해당 연결 된 싱크 연결점은 호출 하는 인터페이스를 식별 하는 데 사용 하는 인터페이스입니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 호출 하는 연결 지점을 지정는 `ISinkInterface` 인터페이스입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="declare_connection_map"></a>  DECLARE_CONNECTION_MAP  
 각 `COleControl`-프로그램의 파생된 클래스를 지 원하는 컨트롤 추가 연결 지점을 지정 하 고 연결 맵을 제공할 수 있습니다.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>설명  
 사용 하 여 컨트롤에 추가 점을 지원는 `DECLARE_CONNECTION_MAP` 끝 클래스 선언에는 매크로입니다. 그런 다음 클래스에 대 한 멤버 함수를 정의 하는.cpp 파일에서 사용 하는 `BEGIN_CONNECTION_MAP` 매크로 `CONNECTION_PART` 각 컨트롤의 연결 지점에 대 한 매크로 및 `END_CONNECTION_MAP` 연결 맵의 끝을 선언 하는 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="begin_connection_map"></a>  BEGIN_CONNECTION_MAP  
 프로그램에서 각 `COleControl` 파생 클래스는 컨트롤을 지원하는 연결 포인트를 지정하기 위해 연결 맵을 제공할 수 있습니다.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 연결을 매핑할 컨트롤 클래스의 이름을 지정합니다.  
  
 *theBase*  
 `theClass`의 기본 클래스 이름을 지정합니다.  
  
### <a name="remarks"></a>설명  
 구현에서 (합니다. 클래스에 대 한 멤버 함수를 정의 하는 CPP) 파일 연결 맵을 시작는 `BEGIN_CONNECTION_MAP` 매크로 다음 사용 하 여 연결 지점의 각각에 대해 매크로 항목을 추가 [CONNECTION_PART](#connection_part) 매크로입니다. 마지막으로 연결 맵을 완료 합니다.는 [END_CONNECTION_MAP](#end_connection_map) 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="end_connection_map"></a>  END_CONNECTION_MAP  
 연결 맵의 정의를 끝냅니다.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="connection_part"></a>  CONNECTION_PART  
 OLE 컨트롤에 대 한 연결 지점을 ID로 매핑합니다.는 특정 인터페이스  
  
```   
CONNECTION_PART(theClass, iid, localClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 연결점 컨트롤 클래스의 이름을 지정 합니다.  
  
 `iid`  
 연결 지점에서 호출 하는 인터페이스의 인터페이스 ID입니다.  
  
 *localClass*  
 연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.  
  
### <a name="remarks"></a>설명  
 예를 들어:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 호출 하는 연결 지점과 연결 맵을 구현 하는 `IID_ISinkInterface` 인터페이스입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="afxconnectionadvise"></a>  AfxConnectionAdvise  
 로 지정 된 원본 사이의 연결을 설정 하려면이 함수를 호출 `pUnkSrc`를 및로 지정 된 싱크 `pUnkSink`합니다.  
  
```   
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD FAR* pdwCookie);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkSrc`  
 인터페이스를 호출 하는 개체에 대 한 포인터입니다.  
  
 `pUnkSink`  
 인터페이스를 구현 하는 개체에 대 한 포인터입니다.  
  
 `iid`  
 연결의 인터페이스 ID입니다.  
  
 `bRefCount`  
 **True 이면** 연결을 만드는의 참조 횟수를 인해 해야 함을 나타냅니다 `pUnkSink` 증가 합니다. **FALSE** 참조 횟수를 증가 하지 되 나타냅니다.  
  
 `pdwCookie`  
 에 대 한 포인터는 `DWORD` 연결 식별자 반환 됩니다. 이 값으로 전달 해야는 `dwCookie` 매개 변수를 `AfxConnectionUnadvise` 연결의 연결을 끊을 때.  
  
### <a name="return-value"></a>반환 값  
 연결이 설정 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h 

##  <a name="afxconnectionunadvise"></a>  AfxConnectionUnadvise  
 로 지정 된 소스 간에 연결을 끊거나이 함수를 호출 `pUnkSrc`를 및로 지정 된 싱크 `pUnkSink`합니다.  
  
```   
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc, 
    REFIID iid, 
    LPUNKNOWN pUnkSink, 
    BOOL bRefCount, 
    DWORD dwCookie); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkSrc`  
 인터페이스를 호출 하는 개체에 대 한 포인터입니다.  
  
 `pUnkSink`  
 인터페이스를 구현 하는 개체에 대 한 포인터입니다.  
  
 `iid`  
 연결 지점 인터페이스의 인터페이스 ID입니다.  
  
 `bRefCount`  
 **True 이면** 는 연결을 끊기의 참조 횟수를 인해 해야 함을 나타냅니다 `pUnkSink` 감소 됩니다. **FALSE** 참조 횟수 감소 하지 않아야 나타냅니다.  
  
 `dwCookie`  
 반환 된 연결 식별자 `AfxConnectionAdvise`합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우에 대 한 연결이 끊어졌습니다. 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
