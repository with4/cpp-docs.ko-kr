---
title: "CRgn 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRgn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRGN"
  - "CRgn 클래스"
  - "지역, MFC"
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRgn 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows GDI(그래픽 장치 인터페이스) 영역을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn__crgn)|`CRgn` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRgn::CombineRgn](#crgn__combinergn)|집합을 `CRgn` 개체의 지정 된 두 개의 통합 하는 것과 같습니다 있도록 `CRgn` 개체입니다.|  
|[CRgn::CopyRgn](#crgn__copyrgn)|설정 된 `CRgn` 개체는 지정 된 복사본 수 있도록 `CRgn` 개체입니다.|  
|[CRgn::CreateEllipticRgn](#crgn__createellipticrgn)|초기화는 `CRgn` 타원형 영역이 있는 개체입니다.|  
|[CRgn::CreateEllipticRgnIndirect](#crgn__createellipticrgnindirect)|초기화는 `CRgn` 정의한 타원형 영역이 있는 개체는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.|  
|[CRgn::CreateFromData](#crgn__createfromdata)|지정된 된 지역 및 변환 데이터에서 영역을 만듭니다.|  
|[CRgn::CreateFromPath](#crgn__createfrompath)|지정 된 장치 컨텍스트에서 선택 된 경로에서 영역을 만듭니다.|  
|[CRgn::CreatePolygonRgn](#crgn__createpolygonrgn)|초기화는 `CRgn` 다각형 영역이 있는 개체입니다. 시스템은 다각형 자동으로 닫힙니다, 필요한 경우 첫 번째와 마지막 꼭지점에서 선을 그려.|  
|[CRgn::CreatePolyPolygonRgn](#crgn__createpolypolygonrgn)|초기화 한 `CRgn` 는 일련의 닫힌된 다각형으로 구성 된 영역을 사용한 개체입니다. 다각형, 연결 되지 않은 이거나 겹칠 수 있습니다.|  
|[CRgn::CreateRectRgn](#crgn__createrectrgn)|초기화는 `CRgn` 사각형 영역 개체입니다.|  
|[CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect)|초기화는 `CRgn` 개체에 정의 된 사각형 영역이 있는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.|  
|[CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn)|초기화 한 `CRgn` 모퉁이가 둥근 사각형 영역이 있는 개체입니다.|  
|[CRgn::EqualRgn](#crgn__equalrgn)|에서는 두 `CRgn` 동일한 지 여부를 결정 하는 개체입니다.|  
|[CRgn::FromHandle](#crgn__fromhandle)|에 대 한 포인터를 반환 합니다.는 `CRgn` 개체 Windows 영역에 대 한 핸들을 지정 합니다.|  
|[CRgn::GetRegionData](#crgn__getregiondata)|지정 된 영역을 설명 하는 데이터는 지정 된 버퍼를 채웁니다.|  
|[CRgn::GetRgnBox](#crgn__getrgnbox)|경계 사각형의 좌표를 검색 한 `CRgn` 개체입니다.|  
|[CRgn::OffsetRgn](#crgn__offsetrgn)|이동 된 `CRgn` 개체에서 지정 된 오프셋 합니다.|  
|[CRgn::PtInRegion](#crgn__ptinregion)|지역에 지정된 된 지점 인지 확인 합니다.|  
|[CRgn::RectInRegion](#crgn__rectinregion)|영역의 경계 내에 지정된 된 사각형의 일부 인지 여부를 결정 합니다.|  
|[CRgn::SetRectRgn](#crgn__setrectrgn)|설정의 `CRgn` 개체 지정된 된 사각형 영역입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HRGN CRgn::operator](#crgn__operator_hrgn)|에 포함 된 Windows 핸들을 반환 된 `CRgn` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 영역은 창 내에서 타원 또는 다각형 영역입니다. 클래스의 멤버 함수를 사용 하면 영역을 사용 하려면 `CRgn` 클래스의 멤버로 정의 된 클리핑 함수로 `CDC`합니다.  
  
 멤버 함수는 `CRgn` 생성, 변경 및를 이라고 영역 개체에 대 한 정보를 검색 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRgn`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecrgncombinergna-crgncombinergn"></a><a name="crgn__combinergn"></a>  CRgn::CombineRgn  
 두 개의 기존 영역을 결합 하 여 새 GDI 영역을 만듭니다.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRgn1`  
 기존 영역을 식별합니다.  
  
 `pRgn2`  
 기존 영역을 식별합니다.  
  
 `nCombineMode`  
 두 소스 영역을 결합 하는 경우 수행할 작업을 지정 합니다. 다음 값 중 하나를 수 있습니다.  
  
- **RGN_AND** 두 영역 (교집합)의 겹치는 영역을 사용 합니다.  
  
- **RGN_COPY** 지역 1의 복사본을 만듭니다 (으로 식별 `pRgn1`).  
  
- **RGN_DIFF** 1 영역의 영역으로 구성 된 영역을 만듭니다 (으로 식별 `pRgn1`)는 2 영역에 속하지 않는 (로 식별 되 `pRgn2`).  
  
- **RGN_OR** 두 영역 (합집합) 전체에서를 결합 합니다.  
  
- **RGN_XOR** 두 지역 결합 하지만 겹치는 영역을 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 결과 영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.  
  
- **COMPLEXREGION** 새 영역에 테두리를 중첩 합니다.  
  
- **오류** 만든 새 지역 없습니다.  
  
- **NULLREGION** 새 영역이 비어 있습니다.  
  
- **SIMPLEREGION** 새 지역에 겹치는 테두리가 없습니다.  
  
### <a name="remarks"></a>설명  
 영역을 결합 하 여 지정 된 대로 `nCombineMode`합니다.  
  
 지정 된 영역을 결합 하 고 결과 영역 핸들에 저장 된 두는 `CRgn` 개체입니다. 어떤 영역에 저장 된 따라서는 `CRgn` 개체에서 결합 된 영역으로 대체 됩니다.  
  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 사용 하 여 [CopyRgn](#crgn__copyrgn) 한 지역의 다른 영역으로 복사 하 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/CPP/crgn-class_1.cpp)]  
  
##  <a name="a-namecrgncopyrgna-crgncopyrgn"></a><a name="crgn__copyrgn"></a>  CRgn::CopyRgn  
 정의한 영역의 복사 `pRgnSrc` 에 `CRgn` 개체입니다.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRgnSrc`  
 기존 영역을 식별합니다.  
  
### <a name="return-value"></a>반환 값  
 결과 영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.  
  
- **COMPLEXREGION** 새 영역에 테두리를 중첩 합니다.  
  
- **오류** 만든 새 지역 없습니다.  
  
- **NULLREGION** 새 영역이 비어 있습니다.  
  
- **SIMPLEREGION** 새 지역에 겹치는 테두리가 없습니다.  
  
### <a name="remarks"></a>설명  
 이전에 저장 된 영역을 대체 하는 새 지역에서 `CRgn` 개체입니다. 이 함수는 특수 한 경우는 [CombineRgn](#crgn__combinergn) 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRgn::CreateEllipticRgn](#crgn__createellipticrgn)합니다.  
  
##  <a name="a-namecrgncreateellipticrgna-crgncreateellipticrgn"></a><a name="crgn__createellipticrgn"></a>  CRgn::CreateEllipticRgn  
 타원형의 영역을 만듭니다.  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>매개 변수  
 `x1`  
 타원의 경계 사각형의 왼쪽 위 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y1`  
 타원의 경계 사각형의 왼쪽 위 모퉁이의 논리적 y 좌표를 지정합니다.  
  
 `x2`  
 타원의 경계 사각형의 오른쪽 아래 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y2`  
 타원의 경계 사각형의 오른쪽 아래 모퉁이의 논리적 y 좌표를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지역으로 지정 된 경계 사각형에 의해 정의 된 `x1`, `y1`, `x2`, 및 `y2`합니다. 영역에 저장 되는 `CRgn` 개체입니다.  
  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 마친 다음 사용 하 여 만든 영역을 사용 하는 `CreateEllipticRgn` 함수의 경우, 응용 프로그램에 장치 컨텍스트 및 사용 하 여 아웃 지역을 선택 해야는 `DeleteObject` 함수를 제거 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/CPP/crgn-class_2.cpp)]  
  
##  <a name="a-namecrgncreateellipticrgnindirecta-crgncreateellipticrgnindirect"></a><a name="crgn__createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 타원형의 영역을 만듭니다.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조 또는 `CRect` 타원의 경계 사각형의 왼쪽 위 및 오른쪽 아래 모퉁이의 논리적 좌표가 포함 된 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 영역 구조 또는 가리키는 개체에 의해 정의 된 `lpRect` 에 저장 하 고는 `CRgn` 개체입니다.  
  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 마친 다음 사용 하 여 만든 영역을 사용 하는 `CreateEllipticRgnIndirect` 함수의 경우, 응용 프로그램에 장치 컨텍스트 및 사용 하 여 아웃 지역을 선택 해야는 `DeleteObject` 함수를 제거 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRgn::CreateRectRgnIndirect](#crgn__createrectrgnindirect)합니다.  
  
##  <a name="a-namecrgncreatefromdataa-crgncreatefromdata"></a><a name="crgn__createfromdata"></a>  CRgn::CreateFromData  
 지정된 된 지역 및 변환 데이터에서 영역을 만듭니다.  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpXForm*  
 가리키는 [XFORM](../../mfc/reference/xform-structure.md) 영역에서 수행할 변환을 정의 하는 데이터 구조입니다. 이 포인터 이면 **NULL**, id 변환을 사용 됩니다.  
  
 `nCount`  
 가 가리키는 바이트 수가 지정 `pRgnData`합니다.  
  
 `pRgnData`  
 가리키는 [RGNDATA](../../mfc/reference/rgndata-structure.md) 지역 데이터를 포함 하는 데이터 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 하 여 응용 프로그램 영역에 대 한 데이터를 검색할 수는 `CRgn::GetRegionData` 함수입니다.  
  
##  <a name="a-namecrgncreatefrompatha-crgncreatefrompath"></a><a name="crgn__createfrompath"></a>  CRgn::CreateFromPath  
 지정 된 장치 컨텍스트에서 선택 된 경로에서 영역을 만듭니다.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 닫힌된 경로 포함 하는 장치 컨텍스트를 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 로 식별 되는 장치 컨텍스트는 `pDC` 매개 변수는 닫힌된 경로 포함 해야 합니다. 후 `CreateFromPath` Windows 영역 경로 장치 컨텍스트에서 닫힌된 경로 삭제 합니다.  
  
##  <a name="a-namecrgncreatepolygonrgna-crgncreatepolygonrgn"></a><a name="crgn__createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 다각형 영역을 만듭니다.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPoints`  
 배열을 가리키는 **지점** 구조 또는 배열을 `CPoint` 개체입니다. 각 구조에는 x 좌표와 y 좌표는 다각형의 한 꼭 짓 점에 지정합니다.  **지점** 구조 형식은 다음과 같습니다.  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 수를 지정 **지점** 구조 또는 `CPoint` 가리키는 배열의 개체에에서 `lpPoints`합니다.  
  
 `nMode`  
 지역에 대 한 채우기 모드를 지정합니다. 이 매개 변수 중 하나일 수 있습니다 **대체** 또는 **굴곡**합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 시스템은 다각형 자동으로 닫힙니다, 필요한 경우 첫 번째와 마지막 꼭지점에서 선을 그려. 결과 영역에 저장 되는 `CRgn` 개체입니다.  
  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 다각형 채우기 모드를 사용 하는 경우 **대체**, 시스템 스캔 한 줄에 홀수와 짝수 다각형 양쪽 영역을 채웁니다. 즉, 시스템 세 번째와 네 번째 쪽 등에 사이, 첫 번째 및 두 번째 측면 사이의 영역을 채웁니다.  
  
 다각형 채우기 모드를 사용 하는 경우 **굴곡**, 시스템은 도형 그린 영역을 채우는 여부를 결정 하는 방향을 사용 합니다. Polygon에 있는 각 선 세그먼트는 시계 방향으로 또는 시계 반대 방향에 그려집니다. 그림의 외부에 포함 된 영역에서 가져온 가상 선 시계 방향으로 선 세그먼트를 통과할 때마다 수는 증가 합니다. 줄 시계 반대 방향으로 선 세그먼트를 통과할 카운트가 감소 합니다. 줄에는 그림의 바깥쪽에 도달할 때 카운트가 0이 아닌 경우는 영역을 채웁니다.  
  
 응용 프로그램이를 완료할 때 사용 하 여 만든 영역을 사용 하 여 `CreatePolygonRgn` 함수를 사용 하 여 장치 컨텍스트에 아웃 지역 선택 해야는 `DeleteObject` 함수를 제거 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/CPP/crgn-class_3.cpp)]  
  
##  <a name="a-namecrgncreatepolypolygonrgna-crgncreatepolypolygonrgn"></a><a name="crgn__createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 일련의 닫힌된 다각형으로 구성 된 영역을 만듭니다.  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPoints`  
 배열을 가리키는 **지점** 구조 또는 배열을 `CPoint` 다각형의 꼭지점을 정의 하는 개체입니다. 시스템에 자동으로 닫히지 않습니다 때문에 각 다각형을 명시적으로 종료 해야 합니다. 다각형은 연속으로 지정 됩니다.  **지점** 구조 형식은 다음과 같습니다.  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 정수 배열 가리킵니다. 에 있는 첫 번째 다각형의 꼭 짓 점 수를 지정 하는 첫 번째 정수는 `lpPoints` 두 번째 다각형의 꼭 짓 점 수를 지정 하는 배열에 두 번째 정수입니다.  
  
 `nCount`  
 총 수에 정수를 지정 된 `lpPolyCounts` 배열입니다.  
  
 `nPolyFillMode`  
 다각형 채우기 모드를 지정합니다. 이 값 중 하나일 수 있습니다 **대체** 또는 **굴곡**합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 결과 영역에 저장 되는 `CRgn` 개체입니다.  
  
 다각형, 연결 되지 않은 이거나 겹칠 수 있습니다.  
  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 다각형 채우기 모드를 사용 하는 경우 **대체**, 시스템 스캔 한 줄에 홀수와 짝수 다각형 양쪽 영역을 채웁니다. 즉, 시스템 세 번째와 네 번째 쪽 등에 사이, 첫 번째 및 두 번째 측면 사이의 영역을 채웁니다.  
  
 다각형 채우기 모드를 사용 하는 경우 **굴곡**, 시스템은 도형 그린 영역을 채우는 여부를 결정 하는 방향을 사용 합니다. Polygon에 있는 각 선 세그먼트는 시계 방향으로 또는 시계 반대 방향에 그려집니다. 그림의 외부에 포함 된 영역에서 가져온 가상 선 시계 방향으로 선 세그먼트를 통과할 때마다 수는 증가 합니다. 줄 시계 반대 방향으로 선 세그먼트를 통과할 카운트가 감소 합니다. 줄에는 그림의 바깥쪽에 도달할 때 카운트가 0이 아닌 경우는 영역을 채웁니다.  
  
 응용 프로그램이를 완료할 때 사용 하 여 만든 영역을 사용 하 여 `CreatePolyPolygonRgn` 함수를 사용 하 여 장치 컨텍스트에 아웃 지역 선택 해야는 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 멤버 함수를 제거 합니다.  
  
##  <a name="a-namecrgncreaterectrgna-crgncreaterectrgn"></a><a name="crgn__createrectrgn"></a>  CRgn::CreateRectRgn  
 에 저장 되어 있는 사각형 영역을 만드는 데는 `CRgn` 개체입니다.  
  
```  
BOOL CreateRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>매개 변수  
 `x1`  
 영역의 왼쪽 위 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y1`  
 영역의 왼쪽 위 모퉁이의 논리적 y 좌표를 지정합니다.  
  
 `x2`  
 영역의 오른쪽 아래 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y2`  
 영역의 오른쪽 아래 모퉁이의 논리적 y 좌표를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 마친 의해 만들어진 영역을 사용 하 여 `CreateRectRgn`, 응용 프로그램을 사용할지는 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 영역을 제거 하는 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/CPP/crgn-class_4.cpp)]  
  
 추가 예제를 참조 하십시오. [CRgn::CombineRgn](#crgn__combinergn)합니다.  
  
##  <a name="a-namecrgncreaterectrgnindirecta-crgncreaterectrgnindirect"></a><a name="crgn__createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 에 저장 되어 있는 사각형 영역을 만드는 데는 `CRgn` 개체입니다.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조 또는 `CRect` 영역의 왼쪽 위 및 오른쪽 아래 모퉁이의 논리적 좌표가 포함 된 개체입니다.  `RECT` 구조 형식은 다음과 같습니다.  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 마친 의해 만들어진 영역을 사용 하 여 `CreateRectRgnIndirect`, 응용 프로그램을 사용할지는 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 영역을 제거 하는 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/CPP/crgn-class_5.cpp)]  
  
##  <a name="a-namecrgncreateroundrectrgna-crgncreateroundrectrgn"></a><a name="crgn__createroundrectrgn"></a>  CRgn::CreateRoundRectRgn  
 에 저장 된 모퉁이가 둥근 사각형 영역을 만드는 데는 `CRgn` 개체입니다.  
  
```  
BOOL CreateRoundRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);
```  
  
### <a name="parameters"></a>매개 변수  
 `x1`  
 영역의 왼쪽 위 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y1`  
 영역의 왼쪽 위 모퉁이의 논리적 y 좌표를 지정합니다.  
  
 `x2`  
 영역의 오른쪽 아래 모퉁이의 논리적 x 좌표를 지정합니다.  
  
 `y2`  
 영역의 오른쪽 아래 모퉁이의 논리적 y 좌표를 지정합니다.  
  
 *x3*  
 둥근된 모퉁이 만드는 데 타원의 너비를 지정 합니다.  
  
 `y3`  
 둥근된 모퉁이 만드는 데 타원의 높이 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 영역의 크기는 32, 767에서 32, 767 논리 단위 또는 64k의 메모리 제한, 중 더 작은 값입니다.  
  
 응용 프로그램이를 완료할 때 사용 하 여 만든 영역을 사용 하 여 `CreateRoundRectRgn` 함수를 사용 하 여 장치 컨텍스트에 아웃 지역 선택 해야는 [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#cgdiobject__deleteobject) 멤버 함수를 제거 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/CPP/crgn-class_6.cpp)]  
  
##  <a name="a-namecrgncrgna-crgncrgn"></a><a name="crgn__crgn"></a>  CRgn::CRgn  
 `CRgn` 개체를 생성합니다.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>설명  
  `m_hObject` 데이터 멤버와 하나 이상의 다른 개체가 인스턴스화될 때까지 Windows GDI 영역이 포함 되지 않도록 `CRgn` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRgn::CreateRoundRectRgn](#crgn__createroundrectrgn)합니다.  
  
##  <a name="a-namecrgnequalrgna-crgnequalrgn"></a><a name="crgn__equalrgn"></a>  CRgn::EqualRgn  
 에 저장 된 영역에 해당 하는 특정된 지역의 인지 결정 합니다.는 `CRgn` 개체입니다.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `pRgn`  
 영역을 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 두 개의 지역 동일 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/CPP/crgn-class_7.cpp)]  
  
##  <a name="a-namecrgnfromhandlea-crgnfromhandle"></a><a name="crgn__fromhandle"></a>  CRgn::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CRgn` 개체 Windows 영역에 대 한 핸들을 지정 합니다.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>매개 변수  
 `hRgn`  
 Windows 영역에 대 한 핸들을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CRgn` 개체입니다. 반환 값은 실패 한 경우 함수를 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 하는 경우는 `CRgn` 임시 핸들에 개체가 이미 연결 되지 않은 `CRgn` 개체가 생성 되 고 연결 합니다. 이 임시 `CRgn` 개체는 다음에 응용 프로그램의 경우 이벤트 루프에서 유휴 시간에, 될 때까지 모든 임시 그래픽 그 개체가 삭제 되만 유효 합니다. 말하면이는 임시 개체가 올바른지만 하나의 창 메시지를 처리 하는 동안입니다.  
  
##  <a name="a-namecrgngetregiondataa-crgngetregiondata"></a><a name="crgn__getregiondata"></a>  CRgn::GetRegionData  
 데이터 영역을 설명 하는 지정된 된 버퍼를 채웁니다.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRgnData`  
 가리키는 [RGNDATA](../../mfc/reference/rgndata-structure.md) 정보를 받는 데이터 구조입니다. 이 매개 변수가 **NULL**, 반환 값은 영역 데이터에 필요한 바이트 수를 포함 합니다.  
  
 `nCount`  
 크기 (바이트)를 지정 된 `lpRgnData` 버퍼입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 및 `nCount` 에 적절 한 수를 지정 합니다 (바이트)의 반환 값은 항상 `nCount`합니다. 함수가 실패 한 경우 또는 경우 `nCount` 작은 지정 보다 적절 한 바이트 수를 반환 값은 0 (오류).  
  
### <a name="remarks"></a>설명  
 이 데이터 영역을 구성 하는 사각형의 크기를 포함 합니다. 이 함수는와 함께에서 사용 되는 `CRgn::CreateFromData` 함수입니다.  
  
##  <a name="a-namecrgngetrgnboxa-crgngetrgnbox"></a><a name="crgn__getrgnbox"></a>  CRgn::GetRgnBox  
 경계 사각형의 좌표를 검색 된 `CRgn` 개체입니다.  
  
```  
int GetRgnBox(LPRECT lpRect) const;

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조 또는 `CRect` 경계 사각형의 좌표를 받을 개체입니다.  `RECT` 구조 형식은 다음과 같습니다.  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>반환 값  
 영역의 유형을 지정합니다. 다음 값 중 하나일 수 있습니다.  
  
- **COMPLEXREGION** 테두리가 겹치는 영역에 있습니다.  
  
- **NULLREGION** 영역이 비어 있습니다.  
  
- **오류** `CRgn` 개체 유효한 영역을 지정 하지 않습니다.  
  
- **SIMPLEREGION** 지역에 겹치는 테두리가 없습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRgn::CreatePolygonRgn](#crgn__createpolygonrgn)합니다.  
  
##  <a name="a-namecrgnoffsetrgna-crgnoffsetrgn"></a><a name="crgn__offsetrgn"></a>  CRgn::OffsetRgn  
 에 저장 된 영역으로 이동 된 `CRgn` 지정 된 오프셋 하 여 개체입니다.  
  
```  
int OffsetRgn(
    int x,  
    int y);

 
int OffsetRgn(
    POINT point);
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 오른쪽 또는 왼쪽으로 이동할 단위 수를 지정 합니다.  
  
 *y*  
 위로 또는 아래로 이동할 단위 수를 지정 합니다.  
  
 `point`  
 x 좌표 `point` 오른쪽 또는 왼쪽으로 이동할 단위 수를 지정 합니다. y 좌표 `point` 위로 또는 아래로 이동할 단위 수를 지정 합니다.  `point` 매개 변수 중 하나 일 수는 **지점** 구조 또는 `CPoint` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 새 영역 유형입니다. 다음 값 중 하나를 수 있습니다.  
  
- **COMPLEXREGION** 테두리가 겹치는 영역에 있습니다.  
  
- **오류** 지역 핸들이 잘못 되었습니다.  
  
- **NULLREGION** 영역이 비어 있습니다.  
  
- **SIMPLEREGION** 지역에 겹치는 테두리가 없습니다.  
  
### <a name="remarks"></a>설명  
 영역을 이동 하는 함수 *x* 단위는 x 축 및 *y* y 축의 단위입니다.  
  
 영역의 좌표 값은 32, 767 및 보다 크거나 같은 –32,768 보다 작아야 합니다.  *x* 및 *y* 잘못 된 지역 좌표를 방지 하기 위해 매개 변수를 신중 하 게 선택 해야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRgn::CreateEllipticRgn](#crgn__createellipticrgn)합니다.  
  
##  <a name="a-namecrgnoperatorhrgna-crgnoperator-hrgn"></a><a name="crgn__operator_hrgn"></a>  HRGN CRgn::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CRgn` 개체입니다.  
  
' ' 연산자 HRGN() const;

 
```  
  
### Return Value  
 If successful, a handle to the Windows GDI object represented by the `CRgn` object; otherwise **NULL**.  
  
### Remarks  
 This operator is a casting operator, which supports direct use of an **HRGN** object.  
  
 For more information about using graphic objects, see the article [Graphic Objects](http://msdn.microsoft.com/library/windows/desktop/dd144962) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="crgn__ptinregion"></a>  CRgn::PtInRegion  
 Checks whether the point given by *x* and *y* is in the region stored in the `CRgn` object.  
  
```  
BOOL PtInRegion (int x,  
    int y) const;

 
 
Const; BOOL PtInRegion (포인트)

 
```  
  
### Parameters  
 *x*  
 Specifies the logical x-coordinate of the point to test.  
  
 *y*  
 Specifies the logical y-coordinate of the point to test.  
  
 `point`  
 The x- and y-coordinates of `point` specify the x- and y-coordinates of the point to test the value of. The `point` parameter can either be a **POINT** structure or a `CPoint` object.  
  
### Return Value  
 Nonzero if the point is in the region; otherwise 0.  
  
##  <a name="crgn__rectinregion"></a>  CRgn::RectInRegion  
 Determines whether any part of the rectangle specified by `lpRect` is within the boundaries of the region stored in the `CRgn` object.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;

 
```  
  
### Parameters  
 `lpRect`  
 Points to a `RECT` structure or `CRect` object. The `RECT` structure has the following form:  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### Return Value  
 Nonzero if any part of the specified rectangle lies within the boundaries of the region; otherwise 0.  
  
##  <a name="crgn__setrectrgn"></a>  CRgn::SetRectRgn  
 Creates a rectangular region.  
  
```  
void SetRectRgn (int x1,  
    int y1,  
    int x2,  
    int y2);

 
void SetRectRgn (LPCRECT lpRect);
```  
  
### Parameters  
 `x1`  
 Specifies the x-coordinate of the upper-left corner of the rectangular region.  
  
 `y1`  
 Specifies the y-coordinate of the upper-left corner of the rectangular region.  
  
 `x2`  
 Specifies the x-coordinate of the lower-right corner of the rectangular region.  
  
 `y2`  
 Specifies the y-coordinate of the lower-right corner of the rectangular region.  
  
 `lpRect`  
 Specifies the rectangular region. Can be either a pointer to a `RECT` structure or a `CRect` object.  
  
### Remarks  
 Unlike [CreateRectRgn](#crgn__createrectrgn), however, it does not allocate any additional memory from the local Windows application heap. Instead, it uses the space allocated for the region stored in the `CRgn` object. This means that the `CRgn` object must already have been initialized with a valid Windows region before calling `SetRectRgn`. The points given by `x1`, `y1`, `x2`, and `y2` specify the minimum size of the allocated space.  
  
 Use this function instead of the `CreateRectRgn` member function to avoid calls to the local memory manager.  
  
## See Also  
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)



