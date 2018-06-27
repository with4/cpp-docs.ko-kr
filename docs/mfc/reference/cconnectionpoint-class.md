---
title: CConnectionPoint 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CConnectionPoint
- AFXDISP/CConnectionPoint
- AFXDISP/CConnectionPoint::CConnectionPoint
- AFXDISP/CConnectionPoint::GetConnections
- AFXDISP/CConnectionPoint::GetContainer
- AFXDISP/CConnectionPoint::GetIID
- AFXDISP/CConnectionPoint::GetMaxConnections
- AFXDISP/CConnectionPoint::GetNextConnection
- AFXDISP/CConnectionPoint::GetStartPosition
- AFXDISP/CConnectionPoint::OnAdvise
- AFXDISP/CConnectionPoint::QuerySinkInterface
dev_langs:
- C++
helpviewer_keywords:
- CConnectionPoint [MFC], CConnectionPoint
- CConnectionPoint [MFC], GetConnections
- CConnectionPoint [MFC], GetContainer
- CConnectionPoint [MFC], GetIID
- CConnectionPoint [MFC], GetMaxConnections
- CConnectionPoint [MFC], GetNextConnection
- CConnectionPoint [MFC], GetStartPosition
- CConnectionPoint [MFC], OnAdvise
- CConnectionPoint [MFC], QuerySinkInterface
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d892ea225e3b1c1089447587eb808e56370bbb69
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952224"
---
# <a name="cconnectionpoint-class"></a>CConnectionPoint 클래스
"연결점"이라고 하는 다른 OLE 개체와 통신하는 데 사용하는 특별한 형식의 인터페이스를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CConnectionPoint::CConnectionPoint](#cconnectionpoint)|`CConnectionPoint` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CConnectionPoint::GetConnections](#getconnections)|연결 맵의 모든 연결점을 검색합니다.|  
|[CConnectionPoint::GetContainer](#getcontainer)|연결 맵을 소유 하는 컨트롤의 컨테이너를 검색 합니다.|  
|[CConnectionPoint::GetIID](#getiid)|연결 지점의 인터페이스 ID를 검색합니다.|  
|[CConnectionPoint::GetMaxConnections](#getmaxconnections)|컨트롤에서 지 원하는 연결 포인트의 최대 수를 검색 합니다.|  
|[CConnectionPoint::GetNextConnection](#getnextconnection)|에 있는 연결 요소에 대 한 포인터를 검색 *pos*합니다.|  
|[CConnectionPoint::GetStartPosition](#getstartposition)|가 반환 하 여 맵 반복을 시작할는 **위치** 에 전달 될 수 있는 값을 `GetNextConnection` 호출 합니다.|  
|[CConnectionPoint::OnAdvise](#onadvise)|설정 하거나 더 세분화할 연결 때 프레임 워크에서 호출 됩니다.|  
|[CConnectionPoint::QuerySinkInterface](#querysinkinterface)|요청 된 싱크 인터페이스에 대 한 포인터를 검색합니다.|  
  
## <a name="remarks"></a>설명  
 연결 지점 구현 하 고 OLE 컨트롤의 기능을 노출에 사용 되는 기본 OLE 인터페이스와 달리 변경 알림 및 이벤트를 발생 시키고 등의 다른 개체에 대 한 작업을 시작할 수 있는 송신 인터페이스를 구현 합니다.  
  
 연결을 두 부분으로 구성 됩니다: "원본" 및 인터페이스를 구현 하는 개체 인터페이스를 호출 하는 개체 "sink" 라는 연결점을 표시 함으로써 소스 싱크를 자신에 대 한 연결을 설정할 수 있습니다. 연결 지점 메커니즘을 통해 소스 개체 멤버 함수의 집합의 싱크 구현에 대 한 포인터를 가져옵니다. 예를 들어 싱크에 의해 구현 된 이벤트를 발생 시키는 소스 싱크 구현의 적절 한 메서드를 호출할 수 있습니다.  
  
 기본적으로는 `COleControl`-파생 된 클래스는 두 개의 연결 지점 구현: 이벤트 및 속성에 대 한 변경 알림입니다. 이 연결을 사용, 각각에 대 한 이벤트 발생 및 싱크 (예: 컨트롤의 컨테이너)에 게 알림을 보낼 때 속성 값을 변경 되었습니다. 추가 연결 지점을 구현 하는 OLE 컨트롤에 대 한 지원이 제공 됩니다. 컨트롤 클래스에서 구현 된 각 추가 연결 지점에 대 한 연결 지점을 구현 하는 "연결 부분이" 선언 해야 합니다. 하나 이상의 연결점을 구현 하는 경우 또한 단일 컨트롤 클래스의 "연결 맵을"를 선언 해야 합니다.  
  
 다음 예제에서는 간단한 연결 맵과 대 한 연결 지점을 `Sample` OLE 컨트롤을 코드의 두 부분으로 이루어진: 연결 맵 및 포인트를 선언 하는 첫 번째 부분, 두 번째가 맵과 연결 지점을 구현 합니다. 첫 번째 조각의 아래에서 컨트롤 클래스의 선언에 삽입 되는 `protected` 섹션:  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/cpp/cconnectionpoint-class_1.h)]  
  
 BEGIN_CONNECTION_PART 및 END_CONNECTION_PART 매크로 포함 된 클래스를 선언 `XSampleConnPt` (에서 파생 된 `CConnectionPoint`)이 특정 연결 지점을 구현 하는 합니다. 재정의 하려는 경우 `CConnectionPoint` 멤버 함수 또는 자신만의 멤버 함수를 추가, 이러한 두 매크로 사이 선언 합니다. 예를 들어 CONNECTION_IID 매크로 재정의 `CConnectionPoint::GetIID` 이러한 두 매크로 사이 배치 하는 경우 멤버 함수입니다.  
  
 두 번째 코드 조각에서 구현 파일에 삽입 됩니다 (합니다. CPP) control 클래스입니다. 이 코드를 추가 연결 지점을 포함 하 여 연결 맵을 구현 `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/cconnectionpoint-class_2.cpp)]  
  
 샘플 OLE 컨트롤에 대 한 연결 지점을 노출 면이 코드 조각이 삽입 된 `ISampleSink` 인터페이스입니다.  
  
 일반적으로 연결점 "멀티 캐스팅"를 브로드캐스트하는 여러 개의 싱크 같은 인터페이스에 연결 하는 기능을 지원 합니다. 다음 코드 조각에서는 연결 지점에 대해 각 싱크를 반복 하 여 멀티 캐스팅을 수행 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
 연결의 현재 집합을 검색 하는이 예제는 `SampleConnPt` 연결점을 호출 하 여 `CConnectionPoint::GetConnections`합니다. 연결 및 호출을 반복 `ISampleSink::SinkFunc` 모든 활성 연결 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CConnectionPoint`, 문서를 참조 [연결점](../../mfc/connection-points.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  
  
##  <a name="cconnectionpoint"></a>  CConnectionPoint::CConnectionPoint  
 `CConnectionPoint` 개체를 생성합니다.  
  
```  
CConnectionPoint();
```  
  
##  <a name="getconnections"></a>  CConnectionPoint::GetConnections  
 연결 지점에 대 한 모든 활성 연결을 검색 하려면이 함수를 호출 합니다.  
  
```  
const CPtrArray* GetConnections();
```  
  
### <a name="return-value"></a>반환 값  
 활성 연결 (싱크)의 배열에 대 한 포인터입니다. 배열에서 포인터의 일부가 NULL 수도 있습니다. 이 배열에 있는 각 NULL이 아닌 포인터는 캐스트 연산자를 사용 하 여 싱크 인터페이스에 대 한 포인터를 안전 하 게 변환할 수 있습니다.  
  
##  <a name="getcontainer"></a>  CConnectionPoint::GetContainer  
 검색 하기 위해 프레임 워크에서 호출 된 **IConnectionPointContainer** 연결점에 대 한 합니다.  
  
```  
virtual LPCONNECTIONPOINTCONTAINER GetContainer();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 컨테이너;에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 BEGIN_CONNECTION_PART 매크로 의해 구현 됩니다.  
  
##  <a name="getiid"></a>  CConnectionPoint::GetIID  
 연결 지점의 인터페이스 ID를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual REFIID GetIID() = 0;  
```  
  
### <a name="return-value"></a>반환 값  
 연결 지점의 인터페이스 id입니다.에 대 한 참조  
  
### <a name="remarks"></a>설명  
 이 연결점에 대 한 인터페이스 ID를 반환 하려면이 함수를 재정의 합니다.  
  
##  <a name="getmaxconnections"></a>  CConnectionPoint::GetMaxConnections  
 연결 지점에서 지원 되는 연결의 최대 수를 검색 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual int GetMaxConnections();
```  
  
### <a name="return-value"></a>반환 값  
 경우 제한 없음, 컨트롤 또는-1에서 지 원하는 연결의 최대 수입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 제한이 없음을 나타내는-1을 반환 합니다.  
  
 컨트롤에 연결할 수 있는 싱크의 수를 제한 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="getnextconnection"></a>  CConnectionPoint::GetNextConnection  
 에 있는 연결 요소에 대 한 포인터를 검색 *pos*합니다.  
  
```  
LPUNKNOWN GetNextConnection(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pos*  
 에 대 한 참조를 지정 된 **위치** 이전에서 반환 된 값 `GetNextConnection` 또는 [GetStartPosition](#getstartposition) 호출 합니다.  
  
### <a name="return-value"></a>반환 값  
 로 지정한 요소를 연결에 대 한 포인터 *pos*, 또는 NULL입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 연결 맵에 있는 모든 요소를 통해 반복 하는 데 가장 유용 합니다. 계산할 때,이 함수에서 반환 된 Null을 건너뜁니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/cpp/cconnectionpoint-class_3.cpp)]  
  
##  <a name="getstartposition"></a>  CConnectionPoint::GetStartPosition  
 가 반환 하 여 맵 반복을 시작할는 **위치** 에 전달 될 수 있는 값을 [GetNextConnection](#getnextconnection) 호출 합니다.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 지도; 반복 하기 위한 시작 위치를 나타내는 값 또는 **NULL** 맵이 비어 있는 경우.  
  
### <a name="remarks"></a>설명  
 반복 순서는 예측할 수 없으며; 따라서 "맵 내에서 요소 첫 번째" 특별 한 의미가 없습니다.  
  
### <a name="example"></a>예  
  예를 참조 [CConnectionPoint::GetNextConnection](#getnextconnection)합니다.  
  
##  <a name="onadvise"></a>  CConnectionPoint::OnAdvise  
 설정 되거나 끊어지면가 연결 될 때 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnAdvise(BOOL bAdvise);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAdvise*  
 **True 이면**연결 되 고, 그렇지 않으면 설정 된 경우, **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행하지 않습니다.  
  
 싱크에 연결 하거나 연결 지점에서 연결을 끊을 때 알림을 원하는 경우이 함수를 재정의 합니다.  
  
##  <a name="querysinkinterface"></a>  CConnectionPoint::QuerySinkInterface  
 요청 된 싱크 인터페이스에 대 한 포인터를 검색합니다.  
  
```  
virtual HRESULT QuerySinkInterface(
    LPUNKNOWN pUnkSink,  
    void** ppInterface);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkSink*  
 요청 되 고 싱크 인터페이스의 식별자입니다.  
  
 *ppInterface*  
 으로 식별 된 인터페이스 포인터에 대 한 포인터 *pUnkSink*합니다. 개체가이 인터페이스를 지원 하지 않는 경우 \* *ppInterface* 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)

