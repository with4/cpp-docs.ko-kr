---
title: "연결 맵 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
caps.latest.revision: 12
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8947930d20cc65075abe442b233e4c086f10f76e
ms.lasthandoff: 02/24/2017

---
# <a name="connection-maps"></a>연결 맵
OLE 컨트롤의 다른 응용 프로그램에 대 한 인터페이스를 노출할 수 있습니다. 이러한 인터페이스는이 컨트롤에는 컨테이너에서의 액세스만을 허용 합니다. OLE 컨트롤을 다른 OLE 개체의 외부 인터페이스에 액세스 하려는 경우에 연결점을 확립 되어야 합니다. 이 연결점에는 나가는 외부 디스패치 맵, 예: 이벤트 맵 또는 알림 함수에 대 한 액세스를 제어할 수 있습니다.  
  
 Microsoft Foundation Class 라이브러리는 연결 지점을 지 원하는 프로그래밍 모델을 제공 합니다. 이 모델에서는 "연결 매핑합니다" 인터페이스 또는 OLE 컨트롤에 대 한 연결 지점을 지정 하는 데 사용 됩니다. 연결 맵 각 연결 지점에 대 한 매크로 포함합니다. 연결 맵에 대 한 자세한 내용은 참조는 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) 클래스입니다.  
  
 일반적으로 컨트롤이 두 개의 연결 지점을 지원 합니다: 이벤트 및 알림 속성에 대 한 하나입니다. 이러한 작업으로 구현 됩니다는 `COleControl` 기본 클래스 및 컨트롤 기록기에 의해 추가 작업이 필요 합니다. 클래스에서 구현 하려는 모든 추가 연결 포인트를 수동으로 추가 해야 합니다. 연결 맵 및 지점 지원, MFC에서는 다음 매크로 제공 합니다.  
  
### <a name="connection-map-declaration-and-demarcation"></a>연결 맵 선언 및 구분  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_PART](#begin_connection_part)|(클래스 선언에 사용 해야 합니다)는 추가 연결 지점을 구현 하는 포함된 된 클래스를 선언 합니다.|  
|[END_CONNECTION_PART](#end_connection_part)|(클래스 선언에 사용 해야 합니다) 연결 지점의 선언을 종료 합니다.|  
|[CONNECTION_IID](#connection_iid)|컨트롤의 연결 지점의 인터페이스 ID를 지정합니다.|  
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|연결 맵 클래스 (클래스 선언에 사용 해야 합니다)에서 사용될지를 선언 합니다.|  
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 시작 합니다.|  
|[END_CONNECTION_MAP](#end_connection_map)|(클래스 구현에 사용 해야 합니다) 연결 맵의 정의 끝냅니다.|  
|[CONNECTION_PART](#connection_part)|컨트롤의 연결 맵을 연결점을 지정합니다.|  
  
 다음 함수는 싱크 설정 하 고 연결 지점을 사용 하 여 연결을 끊기 지원:  
  
### <a name="initializationtermination-of-connection-points"></a>연결 지점의 초기화/종료  
  
|||  
|-|-|  
|[AfxConnectionAdvise](#afxconnectionadvise)|원본 및 싱크 간에 연결을 설정 합니다.|  
|[AfxConnectionUnadvise](#afxconnectionunadvise)|원본 및 싱크 간의 연결을 중단합니다.|  
  
##  <a name="a-namebeginconnectionparta--beginconnectionpart"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART  
 사용 된 `BEGIN_CONNECTION_PART` 추가 연결 지점 이벤트와 속성 알림 연결 지점 외의 정의 시작 하는 매크로입니다.  
  
```   
BEGIN_CONNECTION_PART(theClass, localClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 연결점 컨트롤 클래스의 이름을 지정 합니다.  
  
 *localClass*  
 연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.  
  
### <a name="remarks"></a>주의  
 클래스 멤버 함수를 정의 하는 선언 (.h) 파일에서 시작 하 여 연결 지점을 `BEGIN_CONNECTION_PART` 매크로 추가 `CONNECTION_IID` 매크로 및 구현 하 고 연결 지점 맵을 완료 하려는 다른 모든 멤버 함수는 `END_CONNECTION_PART` 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameendconnectionparta--endconnectionpart"></a><a name="end_connection_part"></a>END_CONNECTION_PART  
 연결 지점의 선언을 종료합니다.  
  
```   
END_CONNECTION_PART(localClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 *localClass*  
 연결 지점을 구현하는 로컬 클래스의 이름을 지정합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameconnectioniida--connectioniid"></a><a name="connection_iid"></a>CONNECTION_IID  
 Between은 `BEGIN_CONNECTION_PART` 및 `END_CONNECTION_PART` OLE 컨트롤에서 지 원하는 연결 지점에 대 한 인터페이스 ID를 정의 하는 매크로입니다.  
  
```   
CONNECTION_IID(iid)   
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 연결 지점에서 호출 하는 인터페이스의 인터페이스 ID입니다.  
  
### <a name="remarks"></a>주의  
 `iid` 인수가 ID 연결 지점에 연결 된 해당 싱크를 호출 하는 인터페이스를 식별 하는 데 사용 하는 인터페이스입니다. 예:  
  
 [!code-cpp[NVC_MFCConnectionPoints #&10;](../../mfc/codesnippet/cpp/connection-maps_1.h)]  
  
 호출 하는 연결 지점을 지정 하는 `ISinkInterface` 인터페이스입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-namedeclareconnectionmapa--declareconnectionmap"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP  
 각 `COleControl`-프로그램의 파생된 클래스에 추가 연결 지점을 지 원하는 컨트롤을 지정 하기 위해 연결 맵을 제공할 수 있습니다.  
  
```   
DECLARE_CONNECTION_MAP() 
```  
  
### <a name="remarks"></a>주의  
 사용 하 여 컨트롤 추가 점수를 지 원하는 경우는 `DECLARE_CONNECTION_MAP` 클래스 선언 후에는 매크로입니다. 그런 다음 클래스 멤버 함수를 정의 하는.cpp 파일에서 사용 하는 `BEGIN_CONNECTION_MAP` 매크로 `CONNECTION_PART` 각 컨트롤의 연결 포인트에 대 한 매크로 및 `END_CONNECTION_MAP` 연결 맵의 끝을 선언 하는 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-namebeginconnectionmapa--beginconnectionmap"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP  
 프로그램에서 각 `COleControl` 파생 클래스는 컨트롤을 지원하는 연결 포인트를 지정하기 위해 연결 맵을 제공할 수 있습니다.  
  
```   
BEGIN_CONNECTION_MAP(theClass, theBase)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 연결을 매핑할 컨트롤 클래스의 이름을 지정합니다.  
  
 *theBase*  
 `theClass`의 기본 클래스 이름을 지정합니다.  
  
### <a name="remarks"></a>주의  
 구현에서 (합니다. 클래스에 대 한 멤버 함수를 정의 하는 CPP) 파일 연결 맵을 시작한는 `BEGIN_CONNECTION_MAP` 매크로 사용 하 여 연결 지점의 각각에 대해 매크로 항목을 추가 합니다는 [CONNECTION_PART](#connection_part) 매크로입니다. 마지막으로, 연결 맵을 완료는 [END_CONNECTION_MAP](#end_connection_map) 매크로입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameendconnectionmapa--endconnectionmap"></a><a name="end_connection_map"></a>END_CONNECTION_MAP  
 연결 맵의 정의를 끝냅니다.  
  
```   
END_CONNECTION_MAP()  
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameconnectionparta--connectionpart"></a><a name="connection_part"></a>CONNECTION_PART  
 OLE 컨트롤에 대 한 연결 지점을 특정 인터페이스 ID에 매핑합니다.  
  
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
  
### <a name="remarks"></a>주의  
 예:  
  
 [!code-cpp[NVC_MFCConnectionPoints #&2;](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]  
  
 호출 하는 연결 지점과 연결 맵을 구현 하는 `IID_ISinkInterface` 인터페이스입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="a-nameafxconnectionadvisea--afxconnectionadvise"></a><a name="afxconnectionadvise"></a>AfxConnectionAdvise  
 로 지정 된 소스 간에 연결을 설정 하려면이 함수를 호출 `pUnkSrc`, 및로 지정 된 분류 `pUnkSink`합니다.  
  
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
 **True 이면** 연결을 만들의 참조 횟수를 인해 해야 함을 나타냅니다 `pUnkSink` 증가 합니다. **FALSE** 참조 횟수가 증가 하지를 나타냅니다.  
  
 `pdwCookie`  
 에 대 한 포인터는 `DWORD` 연결 식별자를 반환할 위치입니다. 이 값으로 전달할지는 `dwCookie` 매개 변수를 `AfxConnectionUnadvise` 연결을 끊으면.  
  
### <a name="return-value"></a>반환 값  
 연결이 설정 된; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCConnectionPoints #&8;](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h 

##  <a name="a-nameafxconnectionunadvisea--afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>AfxConnectionUnadvise  
 로 지정 된 소스, 간의 연결을 끊거나이 함수를 호출 `pUnkSrc`, 및로 지정 된 분류 `pUnkSink`합니다.  
  
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
 **True 이면** 는 연결을 끊는 중의 참조 횟수를 인해 해야 함을 나타냅니다 `pUnkSink` 감소 됩니다. **FALSE** 참조 횟수 감소 하지 않아야 나타냅니다.  
  
 `dwCookie`  
 반환 된 연결 식별자 `AfxConnectionAdvise`합니다.  
  
### <a name="return-value"></a>반환 값  
 연결 하는 0이 아닌 경우 연결이 끊어졌습니다. 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCConnectionPoints #&9;](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxctl.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

