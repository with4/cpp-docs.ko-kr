---
title: "CD2DGeometrySink 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 0e48ad7304cb505526ab5eab0b9cd1bbba62895c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink 클래스
ID2D1GeometrySink에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 만듭니다.|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|소멸자입니다. D2D geometry 싱크 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|Pathgeometry에 단일 원호를 추가합니다.|  
|[CD2DGeometrySink::AddBezier](#addbezier)|현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|입방 형 3 차원 곡선의 시퀀스를 만들어 기 하 도형 싱크에를 추가 합니다.|  
|[CD2DGeometrySink::AddLine](#addline)|현재 지점과 지정한 끝점 사이 선 세그먼트를 만들어 기 하 도형 싱크를 추가 합니다.|  
|[CD2DGeometrySink::AddLines](#addlines)|지정된 된 요소를 사용 하 여 줄의 시퀀스를 만들어 기 하 도형 싱크에를 추가 합니다.|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|한 번의 호출 배열 정방형 3 차원 세그먼트의 시퀀스를 추가 합니다.|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|지정된 된 지점에 새 그림을 시작 합니다.|  
|[CD2DGeometrySink::Close](#close)|기 하 도형 싱크를 닫습니다.|  
|[CD2DGeometrySink::EndFigure](#endfigure)|현재 그림; 종료 필요에 따라 닫습니다.|  
|[CD2DGeometrySink::Get](#get)|반환 ID2D1GeometrySink 인터페이스|  
|[CD2DGeometrySink::IsValid](#isvalid)|Geometry 싱크 유효성 검사|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|고 포인트 바깥에 있는 요소가이 geometry 싱크에 의해 설명 된 geometry 내부 되는지를 결정 하는 데 사용 하는 방법을 지정 합니다.|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|기 하 도형 싱크에 추가 된 새 세그먼트에 적용 될 스트로크 및 조인 옵션을 지정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|반환 ID2D1GeometrySink 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|ID2D1GeometrySink에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometrysink"></a>CD2DGeometrySink:: ~ CD2DGeometrySink  
 소멸자입니다. D2D geometry 싱크 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>CD2DGeometrySink::AddArc  
 Pathgeometry에 단일 원호를 추가합니다.  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>매개 변수  
 `arc`  
 원호 세그먼트는 그림에 추가 하려면  
  
##  <a name="addbezier"></a>CD2DGeometrySink::AddBezier  
 현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>매개 변수  
 `bezier`  
 제어점 및 추가할 베 지 어 곡선의 끝점을 설명 하는 구조입니다.  
  
##  <a name="addbeziers"></a>CD2DGeometrySink::AddBeziers  
 입방 형 3 차원 곡선의 시퀀스를 만들어 기 하 도형 싱크에를 추가 합니다.  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>매개 변수  
 `beziers`  
 만들려는 베 지 어 곡선을 설명 하는 베 지 어 세그먼트의 배열입니다. 배열의 첫 번째 베 지 어 세그먼트의 끝점에 기 하 도형 싱크 현재 위치 (BeginFigure로 지정 된 위치 또는 그려진 마지막 세그먼트의 끝 지점)에서 곡선이 그려집니다. 배열 하는 추가 베 지 어 세그먼트 들어 있는 경우 각 후속 베 지 어 세그먼트 시작 점으로 위의 베 지 어 세그먼트의 끝점을 사용 합니다.  
  
##  <a name="addline"></a>CD2DGeometrySink::AddLine  
 현재 지점과 지정한 끝점 사이 선 세그먼트를 만들어 기 하 도형 싱크를 추가 합니다.  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 그릴 선의 끝점입니다.  
  
##  <a name="addlines"></a>CD2DGeometrySink::AddLines  
 지정된 된 요소를 사용 하 여 줄의 시퀀스를 만들어 기 하 도형 싱크에를 추가 합니다.  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>매개 변수  
 `points`  
 줄을 그릴를 설명 하는 하나 이상의 포인트의 배열입니다. 배열의 첫 번째 지점에 기 하 도형 싱크 현재 위치 (BeginFigure로 지정 된 위치 또는 그려진 마지막 세그먼트의 끝 지점)에서 선이 그려집니다. 배열에 추가 점을 포함 하는 경우 첫 번째 요소에서 줄에는 세 번째 점과 등 두 번째 요소에서 배열에 두 번째 요소에 그려집니다. 배열을 그릴 선의 시작점과 끝점의 시퀀스입니다.  
  
##  <a name="addquadraticbezier"></a>CD2DGeometrySink::AddQuadraticBezier  
 현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>매개 변수  
 `bezier`  
 제어점 및 추가할 정방형 3 차원 곡선의 끝점을 설명 하는 구조입니다.  
  
##  <a name="addquadraticbeziers"></a>CD2DGeometrySink::AddQuadraticBeziers  
 한 번의 호출 배열 정방형 3 차원 세그먼트의 시퀀스를 추가 합니다.  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>매개 변수  
 `beziers`  
 배열 정방형 3 차원 세그먼트의 시퀀스입니다.  
  
##  <a name="beginfigure"></a>CD2DGeometrySink::BeginFigure  
 지정된 된 지점에 새 그림을 시작 합니다.  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>매개 변수  
 `startPoint`  
 새 그림을 시작 하는 지점입니다.  
  
 `figureBegin`  
 여부 비우거나 채울 새 그림 이어야 합니다.  
  
##  <a name="cd2dgeometrysink"></a>CD2DGeometrySink::CD2DGeometrySink  
 CD2DPathGeometry 개체에서 CD2DGeometrySink 개체를 만듭니다.  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>매개 변수  
 `pathGeometry`  
 기존 CD2DPathGeometry 개체입니다.  
  
##  <a name="close"></a>CD2DGeometrySink::Close  
 기 하 도형 싱크를 닫습니다.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 그렇지 않으면 FALSE입니다.  
  
##  <a name="endfigure"></a>CD2DGeometrySink::EndFigure  
 현재 그림; 종료 필요에 따라 닫습니다.  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `figureEnd`  
 현재 형상이 닫혀 있는지 여부를 나타내는 값입니다. 그림 닫혀 있는 경우 현재 지점과 BeginFigure로 지정 된 시작점 간에 선이 그려집니다.  
  
##  <a name="get"></a>CD2DGeometrySink::Get  
 반환 ID2D1GeometrySink 인터페이스  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>반환 값  
 ID2D1GeometrySink 인터페이스 또는 개체가 아직 초기화 되지 않은 경우에 NULL 포인터입니다.  
  
##  <a name="isvalid"></a>CD2DGeometrySink::IsValid  
 Geometry 싱크 유효성 검사  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 기 하 도형 싱크 올바르면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="m_psink"></a>CD2DGeometrySink::m_pSink  
 ID2D1GeometrySink에 대 한 포인터입니다.  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>CD2DGeometrySink::operator ID2D1GeometrySink *  
 반환 ID2D1GeometrySink 인터페이스  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>반환 값  
 ID2D1GeometrySink 인터페이스 또는 개체가 아직 초기화 되지 않은 경우에 NULL 포인터입니다.  
  
##  <a name="setfillmode"></a>CD2DGeometrySink::SetFillMode  
 고 포인트 바깥에 있는 요소가이 geometry 싱크에 의해 설명 된 geometry 내부 되는지를 결정 하는 데 사용 하는 방법을 지정 합니다.  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `fillMode`  
 지정된 된 지점 기 하 도형의 일부 인지 확인 하는 데 사용 되는 메서드.  
  
##  <a name="setsegmentflags"></a>CD2DGeometrySink::SetSegmentFlags  
 기 하 도형 싱크에 추가 된 새 세그먼트에 적용 될 스트로크 및 조인 옵션을 지정 합니다.  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `vertexFlags`  
 기 하 도형에 추가 된 새 세그먼트에 적용 될 스트로크 및 조인 옵션 싱크입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

