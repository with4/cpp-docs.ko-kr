---
title: "CRect 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPCRECT 데이터 형식"
  - "CRect 클래스"
  - "LPRECT 연산자"
  - "RECT 구조체"
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRect 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows와 유사한 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRect::CRect](#crect__crect)|`CRect` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRect::BottomRight](#crect__bottomright)|오른쪽 아래 점을 반환 `CRect`합니다.|  
|[CRect::CenterPoint](#crect__centerpoint)|중심점 반환 `CRect`합니다.|  
|[CRect::CopyRect](#crect__copyrect)|소스 사각형의 크기를 복사 `CRect`합니다.|  
|[CRect::DeflateRect](#crect__deflaterect)|높이 너비 감소 `CRect`합니다.|  
|[CRect::EqualRect](#crect__equalrect)|결정 여부 `CRect` 은 지정 된 사각형에과 같습니다.|  
|[CRect::Height](#crect__height)|높이 계산 `CRect`합니다.|  
|[CRect::InflateRect](#crect__inflaterect)|너비 및 높이 늘리는 `CRect`합니다.|  
|[CRect::IntersectRect](#crect__intersectrect)|집합 `CRect` 두 개의 사각형의 교차 부분으로 동일 합니다.|  
|[CRect::IsRectEmpty](#crect__isrectempty)|결정 여부 `CRect` 비어 있습니다. `CRect` 너비 및 높이 0에서 하는 경우 비어 있습니다.|  
|[CRect::IsRectNull](#crect__isrectnull)|결정 여부는 **위쪽**, **아래쪽**, **왼쪽**, 및 **오른쪽** 멤버 변수는 모두 0으로 동등 합니다.|  
|[CRect::MoveToX](#crect__movetox)|이동 `CRect` 지정한 x 좌표입니다.|  
|[CRect::MoveToXY](#crect__movetoxy)|이동 `CRect` 에 지정 된 x 및 y 좌표가 있습니다.|  
|[CRect::MoveToY](#crect__movetoy)|이동 `CRect` 지정 y-좌표입니다.|  
|[Crect:: Normalizerect](#crect__normalizerect)|너비와 높이 표준화 `CRect`합니다.|  
|[CRect::OffsetRect](#crect__offsetrect)|이동 `CRect` 지정 된 오프셋으로 합니다.|  
|[CRect::PtInRect](#crect__ptinrect)|지정된 된 지점 내에 있는지 여부를 확인 `CRect`합니다.|  
|[CRect::SetRect](#crect__setrect)|크기를 설정 `CRect`합니다.|  
|[CRect::SetRectEmpty](#crect__setrectempty)|집합 `CRect` 빈 사각형 (모든 좌표에 해당 하는 0)에 있습니다.|  
|[CRect::Size](#crect__size)|크기를 계산 `CRect`합니다.|  
|[CRect::SubtractRect](#crect__subtractrect)|다른 한 사각형을 뺍니다.|  
|[CRect::TopLeft](#crect__topleft)|왼쪽 위 지점을 반환 `CRect`합니다.|  
|[CRect::UnionRect](#crect__unionrect)|집합 `CRect` 같은 두 개의 사각형의 합집합입니다.|  
|[CRect::Width](#crect__width)|폼의 너비를 계산 `CRect`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CRect::operator-](#crect__operator_-)|지정 된 오프셋을 뺍니다 `CRect` 수축 또는 `CRect` 결과 반환 하 고 `CRect`합니다.|  
|[LPCRECT CRect::operator](#crect__operator_lpcrect)|변환 된 `CRect` 에 **LPCRECT**합니다.|  
|[LPRECT CRect::operator](#crect__operator_lprect)|변환 된 `CRect` 에 `LPRECT`합니다.|  
|[CRect::operator! =](#crect__operator__neq)|결정 여부 `CRect` 사각형 같지 않습니다.|  
|[CRect::operator &amp;](#crect__operator__amp_)|교차 부분을 만듭니다 `CRect` 및 사각형 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator &amp;=](#crect__operator__amp__eq)|집합 `CRect` 의 교차점으로 같은 `CRect` 및 사각형입니다.|  
|[CRect::operator |](#crect__operator__or)|합집합을 만듭니다 `CRect` 및 사각형 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator |=](#crect__operator__or_eq)|집합 `CRect` 의 합집합 같지 `CRect` 및 사각형입니다.|  
|[CRect::operator +](#crect__operator__add)|지정 된 오프셋을 추가 하는 `CRect` 팽창 또는 `CRect` 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator + =](#crect__operator__add_eq)|지정 된 오프셋을 추가 하는 `CRect` 팽창 또는 `CRect`합니다.|  
|[CRect::operator =](#crect__operator__eq)|복사 하는 사각형의 크기 `CRect`합니다.|  
|[-= CRect::operator](#crect__operator_-_eq)|지정 된 오프셋을 뺍니다 `CRect` 수축 또는 `CRect`합니다.|  
|[CRect::operator = =](#crect__operator__eq_eq)|결정 여부 `CRect` 사각형 같습니다.|  
  
## <a name="remarks"></a>설명  
 `CRect` 또한 조작 하는 멤버 함수를 포함 `CRect` 개체 및 Windows `RECT` 구조입니다.  
  
 A `CRect` 개체를 함수 매개 변수로 전달할 수 있습니다 언제나는 `RECT` 구조 **LPCRECT**, 또는 `LPRECT` 전달 될 수 있습니다.  
  
> [!NOTE]
>  이 클래스에서 파생 되는 **tagRECT** 구조입니다. (이름 **tagRECT** 는 덜 일반적으로 사용에 대 한 이름인는 `RECT` 구조입니다.) 즉, 데이터 멤버 ( **왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽**)의 `RECT` 구조 액세스할 수 있는 데이터의 멤버인 `CRect`합니다.  
  
 A `CRect` 사각형의 왼쪽 위 및 오른쪽 아래 지점을 정의 하는 멤버 변수가 포함 되어 있습니다.  
  
 지정 하는 경우는 `CRect`, 을 정규화 할 수 있도록 구성 하는 주의 해야-즉, 왼쪽된 좌표 값을 사용 하면 위쪽과 오른쪽 보다 작으면 되도록 보다 작으면 아래쪽입니다. 예를 들어 top (10,10)의 왼쪽 (20,20)의 오른쪽 아래에 정사각형을 정의 하지만 top (20,20)의 왼쪽 및 (10,10)의 오른쪽 아래에서 정규화 되지 않은 사각형을 정의 합니다. 사각형 정규화 되지 않으므로 많은 경우 `CRect` 멤버 함수는 잘못 된 결과 반환할 수 있습니다. (참조 [Crect:: Normalizerect](#crect__normalizerect) 이러한 함수 목록은.) 정규화 되지 않은 사각형을 정규화 할 수를 호출 하 여 정규화 된 사각형을 필요로 하는 함수를 호출 하기 전에 `NormalizeRect` 함수입니다.  
  
 조작 때는 주의 `CRect` [CDC::DPtoLP]와 (... /Topic/CDC%20Class.md#cdc__dptolp 및 [CDC::LPtoDP] (.. /Topic/CDC%20Class.md#cdc__lptodp 멤버 함수입니다. 디스플레이 컨텍스트 매핑 모드는 y-익스텐트가 음수인 경우에서 같이 `MM_LOENGLISH`, 다음 `CDC::DPtoLP` 변환는 `CRect` top 아래쪽 보다 크면 되도록 합니다. 와 같은 함수가 **높이** 및 **크기** 그런 다음 변환 된 높이 대 한 음수 값을 반환 합니다 `CRect`, 사각형 정규화 되지 않은 잠금 해제 됩니다.  
  
 사용 하 여이 오버 로드 `CRect` 연산자, 첫 번째 피연산자는 반드시는 `CRect`; 두 번째 수는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 개체.  
  
> [!NOTE]
>  대 한 자세한 내용은 공유 유틸리티 클래스 (같은 `CRect`), 참조 [공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltypes.h  
  
##  <a name="a-namecrectbottomrighta-crectbottomright"></a><a name="crect__bottomright"></a>  CRect::BottomRight  
 좌표에 대 한 참조로 반환 되는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체에 포함 된 `CRect`합니다.  
  
```  
 
CPoint& BottomRight() throw();

const CPoint& BottomRight() const throw();

 
```  
  
### <a name="return-value"></a>반환 값  
 사각형의 오른쪽 아래 모퉁이의 좌표입니다.  
  
### <a name="remarks"></a>설명  
 Get 또는 set 사각형의 오른쪽 아래 모서리에이 함수를 사용할 수 있습니다. 할당 연산자의 왼쪽에이 함수를 사용 하 여 모퉁이 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#35](../../atl-mfc-shared/codesnippet/CPP/crect-class_1.cpp)]  
  
##  <a name="a-namecrectcenterpointa-crectcenterpoint"></a><a name="crect__centerpoint"></a>  CRect::CenterPoint  
 계산의 중심점 `CRect` 왼쪽 및 오른쪽 값을 추가 하 고 2로 하 고 위쪽 및 아래쪽 값을 추가 나누고 2로 나눈 합니다.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 A `CPoint` 개체의 중심점입니다 `CRect`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#36](../../atl-mfc-shared/codesnippet/CPP/crect-class_2.cpp)]  
  
##  <a name="a-namecrectcopyrecta-crectcopyrect"></a><a name="crect__copyrect"></a>  CRect::CopyRect  
 복사본은 `lpSrcRect` 사각형에 `CRect`합니다.  
  
```  
 
void CopyRect(
LPCRECT   
lpSrcRect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSrcRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 복사 될 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#37](../../atl-mfc-shared/codesnippet/CPP/crect-class_3.cpp)]  
  
##  <a name="a-namecrectcrecta-crectcrect"></a><a name="crect__crect"></a>  CRect::CRect  
 `CRect` 개체를 생성합니다.  
  
```  
 
    CRect() throw();
CRect(
 int    
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();
CRect(
 const RECT& 
    srcRect) throw();
CRect(
 LPCRECT    
    lpSrcRect) throw();
CRect(
 POINT    
    point ,  
    SIZE 
    size) throw();
CRect(
 POINT    
    topLeft ,  
    POINT 
    bottomRight) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *l*  
 왼쪽된 위치를 지정 `CRect`합니다.  
  
 *t*  
 맨 위에 지정 `CRect`합니다.  
  
 *r*  
 올바른 위치를 지정 `CRect`합니다.  
  
 *b*  
 아래 지정 `CRect`합니다.  
  
 *srcRect*  
 참조 하는 [RECT](../../mfc/reference/rect-structure1.md) 구조에 대 한 좌표는 `CRect`합니다.  
  
 `lpSrcRect`  
 가리키는 `RECT` 구조에 대 한 좌표는 `CRect`합니다.  
  
 `point`  
 생성 되는 사각형에 대 한 시작 지점을 지정 합니다. 왼쪽 위 모퉁이에 해당합니다.  
  
 `size`  
 생성 되는 사각형의 오른쪽 아래 모서리에 왼쪽 위 모서리에서 변위를 지정 합니다.  
  
 *왼쪽 맨 위*  
 왼쪽 위에 위치를 지정 `CRect`합니다.  
  
 *오른쪽 맨 아래*  
 오른쪽 아래 위치를 지정 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 인수 없이 제공 **왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽** 멤버는 초기화 되지 않습니다.  
  
  `CRect`( **const RECT &**) 및 `CRect`( **LPCRECT**) 수행 하는 생성자는 [CopyRect](#crect__copyrect). 다른 생성자는 직접 개체의 멤버 변수를 초기화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#38](../../atl-mfc-shared/codesnippet/CPP/crect-class_4.cpp)]  
  
##  <a name="a-namecrectdeflaterecta-crectdeflaterect"></a><a name="crect__deflaterect"></a>  CRect::DeflateRect  
 `DeflateRect` 수축 `CRect` 의 측면의 중심을 향해 이동 하 여 합니다.  
  
```  
 
    void DeflateRect(
    int 
    x ,  
    int 
    y) throw();
void DeflateRect(
    SIZE 
    size) throw();
void DeflateRect(
    LPCRECT 
    lpRect) throw();
void DeflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 왼쪽 deflate 단위 수의 왼쪽과 오른쪽 지정 `CRect`합니다.  
  
 *y*  
 위쪽 및 아래쪽을 deflate 단위 수를 지정 `CRect`합니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) deflate 단위 수를 지정 하는 `CRect`합니다.  `cx` 좌 변과 우변을 deflate 단위 수를 지정 하는 값 및 `cy` 값 위쪽 및 아래쪽 deflate 단위 수를 지정 합니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 양쪽 deflate 단위 수를 지정 하는 합니다.  
  
 *l*  
 왼쪽의 deflate 단위 수를 지정 `CRect`합니다.  
  
 *t*  
 맨 위에 deflate 단위 수를 지정 `CRect`합니다.  
  
 *r*  
 오른쪽 deflate 단위 수를 지정 `CRect`합니다.  
  
 *b*  
 맨 deflate 단위 수를 지정 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 이렇게 하려면 `DeflateRect` left 및 top에 장치를 추가 하 고 오른쪽 아래에서 단위를 뺍니다. 매개 변수 `DeflateRect` 서명 된 값으로 deflate 양수 값 `CRect` 및 음수 값을 확장할 것입니다.  
  
 처음 두 개의 오버 로드 두 쌍의 반대편의 deflate `CRect` 두 번의 전체 너비 감소 되도록 *x* (또는 `cx`) 두 번의 전체 높이 감소 및 *y* (또는 `cy`). 다른 두 오버 로드의 각 면 deflate `CRect` 독립적입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#39](../../atl-mfc-shared/codesnippet/CPP/crect-class_5.cpp)]  
  
##  <a name="a-namecrectequalrecta-crectequalrect"></a><a name="crect__equalrect"></a>  CRect::EqualRect  
 결정 여부 `CRect` 은 지정 된 사각형에과 같습니다.  
  
```  
 
BOOL EqualRect(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 사각형의 왼쪽 위 및 오른쪽 아래 모퉁이 좌표를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개의 사각형 동일한 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 있습니다; 경우에 0이 아닌 그렇지 않으면 0입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#40](../../atl-mfc-shared/codesnippet/CPP/crect-class_6.cpp)]  
  
##  <a name="a-namecrectheighta-crectheight"></a><a name="crect__height"></a>  CRect::Height  
 높이 계산 `CRect` 아래쪽 값에서 맨 위에 있는 값을 빼서 합니다.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 높이 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 결과 값은 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#41](../../atl-mfc-shared/codesnippet/CPP/crect-class_7.cpp)]  
  
##  <a name="a-namecrectinflaterecta-crectinflaterect"></a><a name="crect__inflaterect"></a>  CRect::InflateRect  
 `InflateRect` 팽창 `CRect` 중심 반대쪽의 측면을 이동 하 여 합니다.  
  
```  
 
    void InflateRect(
    int 
    x ,  
    int 
    y) throw();
void InflateRect(
    SIZE 
    size) throw();
void InflateRect(
    LPCRECT 
    lpRect) throw();
void InflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 왼쪽 확장할 단위 수의 왼쪽과 오른쪽 지정 `CRect`합니다.  
  
 *y*  
 위쪽 및 아래쪽을 확장할 단위 수를 지정 `CRect`합니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 을 확장할 단위의 수를 지정 하는 `CRect`합니다.  `cx` 값을 왼쪽 및 오른쪽 확장할 단위의 수를 지정 하며 `cy` 값을 위쪽 및 아래쪽 확장할 단위의 수를 지정 합니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 을 양쪽 확장할 단위의 수를 지정 하는 합니다.  
  
 *l*  
 왼쪽의 확장할 단위 수를 지정 `CRect`합니다.  
  
 *t*  
 맨 위에 확장할 단위 수를 지정 `CRect`합니다.  
  
 *r*  
 오른쪽 확장할 단위 수를 지정 `CRect`합니다.  
  
 *b*  
 아래쪽 팽창 단위 수를 지정 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 이렇게 하려면 `InflateRect` left 및 top에서 단위를 빼고를 오른쪽 아래에 장치를 추가 합니다. 매개 변수 `InflateRect` 서명 값 확장할 양수 값 `CRect` 음수 값을 deflate 것입니다.  
  
 처음 두 개의 오버 로드 두 쌍의 반대편의 확장할 `CRect` 총 너비가 두 배로 증가 되도록 *x* (또는 `cx`) 하 고 총 높이 두 배로 증가 *y* (또는 `cy`). 다른 두 오버 로드의 각 면 확장할 `CRect` 독립적입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#42](../../atl-mfc-shared/codesnippet/CPP/crect-class_8.cpp)]  
  
##  <a name="a-namecrectintersectrecta-crectintersectrect"></a><a name="crect__intersectrect"></a>  CRect::IntersectRect  
 사용 하면는 `CRect` 두 개의 기존 사각형의 교차 부분으로 동일 합니다.  
  
```  
 
    BOOL IntersectRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.  
  
 `lpRect2`  
 가리키는 `RECT` 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 교차 비어 있지 않으면; 0이 아닌 교집합이 비어 있는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 교집합 모두 기존 사각형에 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#43](../../atl-mfc-shared/codesnippet/CPP/crect-class_9.cpp)]  
  
##  <a name="a-namecrectisrectemptya-crectisrectempty"></a><a name="crect__isrectempty"></a>  CRect::IsRectEmpty  
 결정 여부 `CRect` 비어 있습니다.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 `CRect` 빈 않으면 0 경우 `CRect` 비어 있지 않습니다.  
  
### <a name="remarks"></a>설명  
 사각형 비어 너비 및 높이 0 또는 음수 됩니다. 다른 `IsRectNull`, 사각형의 모든 좌표는 0이 있는지 여부를 결정 하는 합니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#44](../../atl-mfc-shared/codesnippet/CPP/crect-class_10.cpp)]  
  
##  <a name="a-namecrectisrectnulla-crectisrectnull"></a><a name="crect__isrectnull"></a>  CRect::IsRectNull  
 위쪽, 왼쪽, 아래쪽 있는지 여부를 결정 및의 값이 여기 `CRect` 은 모두 0입니다.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 `CRect`의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0이 고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 다른 `IsRectEmpty`, 사각형 비어 있는지 여부를 결정 하 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#45](../../atl-mfc-shared/codesnippet/CPP/crect-class_11.cpp)]  
  
##  <a name="a-namecrectmovetoxa-crectmovetox"></a><a name="crect__movetox"></a>  CRect::MoveToX  
 사각형을 지정 하 여 절대 x-좌표 이동 하려면이 함수를 호출 *x*합니다.  
  
```  
 
void MoveToX(
int   
x) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#46](../../atl-mfc-shared/codesnippet/CPP/crect-class_12.cpp)]  
  
##  <a name="a-namecrectmovetoxya-crectmovetoxy"></a><a name="crect__movetoxy"></a>  CRect::MoveToXY  
 에 절대 x 및 y 좌표가 지정 된 사각형을 이동 하려면이 함수를 호출 합니다.  
  
```  
 
    void MoveToXY(
    int 
    x ,  
    int 
    y) throw();
void MoveToXY(
    POINT 
    point) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.  
  
 *y*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.  
  
 `point`  
 A **지점** 사각형의 절대 왼쪽 위 모퉁이 지정 하는 구조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#47](../../atl-mfc-shared/codesnippet/CPP/crect-class_13.cpp)]  
  
##  <a name="a-namecrectmovetoya-crectmovetoy"></a><a name="crect__movetoy"></a>  CRect::MoveToY  
 사각형을 지정 하 여 절대 y-좌표 이동 하려면이 함수를 호출 *y*합니다.  
  
```  
 
void MoveToY(
int   
y) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *y*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#48](../../atl-mfc-shared/codesnippet/CPP/crect-class_14.cpp)]  
  
##  <a name="a-namecrectnormalizerecta-crectnormalizerect"></a><a name="crect__normalizerect"></a>  Crect:: Normalizerect  
 정규화 `CRect` 의 높이 너비는 양성 수 있도록 합니다.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>설명  
 사각형 네 번째 구성 요소 위치 지정에 대 한 정규화 된 좌표에 대 한 일반적으로 Windows를 사용 합니다. `NormalizeRect` 위쪽 및 아래쪽 값을 비교 하 고 맨 아래 보다 큰 경우이 교환 합니다. 마찬가지로, 왼쪽에서 오른쪽 보다 큰 경우 left 및 right 값 바꿉니다. 이 함수는 서로 다른 매핑 모드를 처리할 때 유용 하 고 사각형을 반전 합니다.  
  
> [!NOTE]
>  다음 `CRect` 멤버 함수에는 제대로 작동 하려면 정규화 된 사각형 필요: [높이](#crect__height), [너비](#crect__width), [크기](#crect__size), [IsRectEmpty](#crect__isrectempty), [PtInRect](#crect__ptinrect), [EqualRect](#crect__equalrect), [UnionRect](#crect__unionrect), [IntersectRect](#crect__intersectrect), [SubtractRect](#crect__subtractrect), [연산자 = =](#crect__operator__eq_eq), [연산자! =](#crect__operator__neq), [연산자 &#124;](#crect__operator__or), [연산자 &#124; =](#crect__operator__or_eq), [연산자 (& a)](#crect__operator__amp_), 및 [연산자 (& a) =](#crect__operator__amp__eq)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#49](../../atl-mfc-shared/codesnippet/CPP/crect-class_15.cpp)]  
  
##  <a name="a-namecrectoffsetrecta-crectoffsetrect"></a><a name="crect__offsetrect"></a>  CRect::OffsetRect  
 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
 
    void OffsetRect(
    int 
    x ,  
    int 
    y) throw();
void OffsetRect(
    POINT 
    point) throw();
void OffsetRect(
    SIZE 
    size) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 오른쪽 또는 왼쪽으로 이동 하 여 지정 합니다. 왼쪽으로 이동에 음수 여야 합니다.  
  
 *y*  
 위로 또는 아래로 이동할 거리를 지정 합니다. 위로 이동 하려면 음수 여야 합니다.  
  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 이동 하는 크기를 모두 지정 하는 개체입니다.  
  
 `size`  
 포함 된 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 이동 하는 크기를 모두 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이동 `CRect`*x* 단위는 x 축 및 *y* y 축의 단위입니다.  *x* 및 *y* 매개 변수는 부호 있는 값 하므로 `CRect` 왼쪽 이동 하거나 오른쪽 및 또는 축소 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#50](../../atl-mfc-shared/codesnippet/CPP/crect-class_16.cpp)]  
  
##  <a name="a-namecrectoperatorlpcrecta-crectoperator-lpcrect"></a><a name="crect__operator_lpcrect"></a>  LPCRECT CRect::operator  
 변환 된 `CRect` 에 [LPCRECT](../../mfc/reference/data-types-mfc.md)합니다.  
  
' ' 연산자 LPCRECT() const throw ();
```  
  
### Remarks  
 When you use this function, you don't need the address-of ( **&**) operator. This operator will be automatically used when you pass a `CRect` object to a function that expects an **LPCRECT**.  
  
### Example  
 [!code-cpp[NVC_ATLMFC_Utilities#58](../../atl-mfc-shared/codesnippet/CPP/crect-class_17.cpp)]  
  
##  <a name="crect__operator_lprect"></a>  CRect::operator LPRECT  
 Converts a `CRect` to an [LPRECT](../../mfc/reference/data-types-mfc.md).  
  
```  operator LPRECT() throw();
```  
  
### <a name="remarks"></a>설명  
 Address-of 않아도이 기능을 사용할 때 ( **&**) 연산자. 전달 하는 경우이 연산자 자동으로 사용 된 `CRect` 필요로 하는 함수에는 개체는 `LPRECT`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::operator LPCRECT](#crect__operator_lpcrect)합니다.  
  
##  <a name="a-namecrectoperatoreqa-crectoperator-"></a><a name="crect__operator__eq"></a>  CRect::operator =  
 할당 *srcRect* 를 `CRect`합니다.  
  
```  
 
void operator=(
const RECT& 
srcRect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *srcRect*  
 소스 사각형을 가리킵니다. 수는 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#59](../../atl-mfc-shared/codesnippet/CPP/crect-class_18.cpp)]  
  
##  <a name="a-namecrectoperatoreqeqa-crectoperator-"></a><a name="crect__operator__eq_eq"></a>  CRect::operator = =  
 결정 여부 `rect` 같으면 `CRect` 의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여 합니다.  
  
```  
 
BOOL operator==(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형을 가리킵니다. 수는 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#60](../../atl-mfc-shared/codesnippet/CPP/crect-class_19.cpp)]  
  
##  <a name="a-namecrectoperatorneqa-crectoperator-"></a><a name="crect__operator__neq"></a>  CRect::operator! =  
 결정 여부 `rect` 과 같지 않은 `CRect` 의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여 합니다.  
  
```  
 
BOOL operator!=(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형을 가리킵니다. 수는 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#61](../../atl-mfc-shared/codesnippet/CPP/crect-class_20.cpp)]  
  
##  <a name="a-namecrectoperatoraddeqa-crectoperator-"></a><a name="crect__operator__add_eq"></a>  CRect::operator + =  
 처음 두 개의 오버 로드가 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
 
void operator+=(
POINT   
point) throw();

void operator+=(
SIZE   
size) throw();

void operator+=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 단위를의 양쪽을 확장할 수 있는 개체 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값에 추가 됩니다 `CRect`합니다.  
  
 세 번째 오버 로드 팽창 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#62](../../atl-mfc-shared/codesnippet/CPP/crect-class_21.cpp)]  
  
##  <a name="a-namecrectoperator-eqa-crectoperator--"></a><a name="crect__operator_-_eq"></a>  -= CRect::operator  
 처음 두 개의 오버 로드가 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
 
void operator-=(
POINT   
point) throw();

void operator-=(
SIZE   
size) throw();

void operator-=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 의 각 면 deflate 단위 수를 포함 하는 개체 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값에서 빼면 `CRect`합니다.  
  
 세 번째 오버 로드 수축 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다. 이 오버 로드와 같은 함수는 [DeflateRect](#crect__deflaterect)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#63](../../atl-mfc-shared/codesnippet/CPP/crect-class_22.cpp)]  
  
##  <a name="a-namecrectoperatorampeqa-crectoperator-amp"></a><a name="crect__operator__amp__eq"></a>  CRect::operator &amp;=  
 집합 `CRect` 의 교차점으로 같은 `CRect` 및 `rect`합니다.  
  
```  
 
void operator&=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 교집합에 두 개의 사각형이 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::IntersectRect](#crect__intersectrect)합니다.  
  
##  <a name="a-namecrectoperatororeqa-crectoperator-124"></a><a name="crect__operator__or_eq"></a>  CRect::operator &#124; =  
 집합 `CRect` 의 합집합 같지 `CRect` 및 `rect`합니다.  
  
```  
 
void operator|=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 포함 된 `CRect` 또는 [RECT](../../mfc/reference/rect-structure1.md)합니다.  
  
### <a name="remarks"></a>설명  
 공용 구조체는 두 개의 소스 사각형이 포함 된 가장 작은 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#64](../../atl-mfc-shared/codesnippet/CPP/crect-class_23.cpp)]  
  
##  <a name="a-namecrectoperatoradda-crectoperator-"></a><a name="crect__operator__add"></a>  CRect::operator +  
 처음 두 개의 오버 로드 반환는 `CRect` 개체 같음 `CRect` 지정 된 오프셋에 의해 치환입니다.  
  
```  
 
CRect operator+(
POINT   
point) const throw();

CRect operator+(
LPCRECT   
lpRect) const throw();

CRect operator+(
SIZE   
size) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 을 반환 값의 각 면 확장할 단위의 수를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  `CRect` 이동 하거나 늘려 결과 `CRect` 매개 변수에 지정 하는 단위 수입니다.  
  
### <a name="remarks"></a>설명  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`)에 매개 변수는 추가 `CRect`위치 합니다.  
  
 세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 확장 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#65](../../atl-mfc-shared/codesnippet/CPP/crect-class_24.cpp)]  
  
##  <a name="a-namecrectoperator-a-crectoperator--"></a><a name="crect__operator_-"></a>  CRect::operator-  
 처음 두 개의 오버 로드 반환는 `CRect` 개체 같음 `CRect` 지정 된 오프셋에 의해 치환입니다.  
  
```  
 
CRect operator-(
POINT   
point) const throw();

CRect operator-(
SIZE   
size) const throw();

CRect operator-(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 `CPoint` 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 `CSize` 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 반환 값의 각 면 deflate 단위 수를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
  `CRect` 이동 하거나 deflating 결과 `CRect` 매개 변수에 지정 하는 단위 수입니다.  
  
### <a name="remarks"></a>설명  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 매개 변수에서 뺀 `CRect`위치 합니다.  
  
 세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 축소 됩니다. 이 오버 로드와 같은 함수는 [DeflateRect](#crect__deflaterect), 이 아니라 [SubtractRect](#crect__subtractrect)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#66](../../atl-mfc-shared/codesnippet/CPP/crect-class_25.cpp)]  
  
##  <a name="a-namecrectoperatorampa-crectoperator-amp"></a><a name="crect__operator__amp_"></a>  CRect::operator &amp;  
 반환 된 `CRect` 의 교집합 즉 `CRect` 및 *rect2*.  
  
```  
 
CRect operator&(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *rect2*  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 의 교집합 즉 `CRect` 및 *rect2*합니다.  
  
### <a name="remarks"></a>설명  
 교집합에 두 개의 사각형이 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#67](../../atl-mfc-shared/codesnippet/CPP/crect-class_26.cpp)]  
  
##  <a name="a-namecrectoperatorora-crectoperator-124"></a><a name="crect__operator__or"></a>  CRect::operator &#124;  
 반환 된 `CRect` 의 합집합 즉 `CRect` 및 *rect2*합니다.  
  
```  
 
CRect operator|(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 *rect2*  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 의 합집합 즉 `CRect` 및 *rect2*합니다.  
  
### <a name="remarks"></a>설명  
 공용 구조체는 두 개의 사각형이 포함 된 가장 작은 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#68](../../atl-mfc-shared/codesnippet/CPP/crect-class_27.cpp)]  
  
##  <a name="a-namecrectptinrecta-crectptinrect"></a><a name="crect__ptinrect"></a>  CRect::PtInRect  
 지정된 된 지점 내에 있는지 여부를 확인 `CRect`합니다.  
  
```  
 
BOOL PtInRect(
POINT   
point) const throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 지점 내에 0이 아닌 `CRect`그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 안에 점이 `CRect` 왼쪽 이나 위쪽 측면에서 네 면 모두 내 여부입니다. 외부 오른쪽 또는 아래쪽 쪽 점은 `CRect`합니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#51](../../atl-mfc-shared/codesnippet/CPP/crect-class_28.cpp)]  
  
##  <a name="a-namecrectsetrecta-crectsetrect"></a><a name="crect__setrect"></a>  CRect::SetRect  
 크기를 설정 `CRect` 지정 된 좌표입니다.  
  
```  
 
    void SetRect(
    int 
    x1 ,  
    int 
    y1 ,  
    int 
    x2 ,  
    int 
    y2) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `x1`  
 왼쪽 위 모퉁이의 x 좌표를 지정합니다.  
  
 `y1`  
 왼쪽 위 모퉁이의 y 좌표를 지정합니다.  
  
 `x2`  
 오른쪽 아래 모퉁이의 x 좌표를 지정합니다.  
  
 `y2`  
 오른쪽 아래 모퉁이의 y 좌표를 지정합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#52](../../atl-mfc-shared/codesnippet/CPP/crect-class_29.cpp)]  
  
##  <a name="a-namecrectsetrectemptya-crectsetrectempty"></a><a name="crect__setrectempty"></a>  CRect::SetRectEmpty  
 사용 하면 `CRect` 모든 좌표를 0으로 설정 하 여 null 사각형입니다.  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#53](../../atl-mfc-shared/codesnippet/CPP/crect-class_30.cpp)]  
  
##  <a name="a-namecrectsizea-crectsize"></a><a name="crect__size"></a>  CRect::Size  
  `cx` 및 `cy` 멤버의 반환 값의 너비와 높이가 포함 `CRect`합니다.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체의 크기를 포함 하는 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 너비 또는 높이 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#54](../../atl-mfc-shared/codesnippet/CPP/crect-class_31.cpp)]  
  
##  <a name="a-namecrectsubtractrecta-crectsubtractrect"></a><a name="crect__subtractrect"></a>  CRect::SubtractRect  
 크기를 사용 하면는 **CRect** 의 빼기 같음 `lpRectSrc2` 에서 `lpRectSrc1`합니다.  
  
```  
 
    BOOL SubtractRect(
    LPCRECT 
    lpRectSrc1 ,  
    LPCRECT 
    lpRectSrc2) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRectSrc1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 사각형을 뺄 개체입니다.  
  
 `lpRectSrc2`  
 가리키는 `RECT` 구조 또는 `CRect` 가리키는 개체에는 사각형에서 뺄는 `lpRectSrc1` 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 빼기는 모든 요소를 포함 하는 가장 작은 사각형 `lpRectScr1` 의 교집합에 없는 `lpRectScr1` 및 *lpRectScr2*합니다.  
  
 으로 지정 된 사각형 `lpRectSrc1` 은 변경 되지 사각형으로 지정 된 경우 `lpRectSrc2` 으로 지정 된 사각형을 완전히 겹치지 않는 *lpRectSrc1* 하나 이상의의 x-또는 y-지시 합니다.  
  
 예를 들어 경우 `lpRectSrc1` 되었습니다 (10,10, 100100) 및 `lpRectSrc2` 되었습니다 (50,50, 150,150) 가리키는 사각형 `lpRectSrc1` 는 변경 되지 함수가 반환 하는 경우. 그러나 경우 `lpRectSrc1` 되었습니다 (10,10, 100100) 및 `lpRectSrc2` 되었습니다 (50,10, 150,150) 사각형 가리키는 `lpRectSrc1` (10,10, 50,100) 정보를 포함 하는 함수가 반환 된 경우.  
  
 `SubtractRect` 와 동일 하지는 [연산자-](#crect__operator_-) 나 [-= 연산자](#crect__operator_-_eq)합니다. 이러한 연산자에 해당 하지 않거나 적 호출 `SubtractRect`합니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#55](../../atl-mfc-shared/codesnippet/CPP/crect-class_32.cpp)]  
  
##  <a name="a-namecrecttoplefta-crecttopleft"></a><a name="crect__topleft"></a>  CRect::TopLeft  
 좌표에 대 한 참조로 반환 되는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체에 포함 된 `CRect`합니다.  
  
```  
 
CPoint& TopLeft() throw();

const CPoint& TopLeft() const throw();

 
```  
  
### <a name="return-value"></a>반환 값  
 사각형의 왼쪽 위 모퉁이의 좌표입니다.  
  
### <a name="remarks"></a>설명  
 Get 또는 set 사각형의 왼쪽 위 모퉁이를이 함수를 사용할 수 있습니다. 할당 연산자의 왼쪽에이 함수를 사용 하 여 모퉁이 설정 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::CenterPoint](#crect__centerpoint)합니다.  
  
##  <a name="a-namecrectunionrecta-crectunionrect"></a><a name="crect__unionrect"></a>  CRect::UnionRect  
 크기를 사용 하면 `CRect` 같으면 두 소스 사각형의 합집합입니다.  
  
```  
 
    BOOL UnionRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect` 소스 사각형을 포함 하는 합니다.  
  
 `lpRect2`  
 가리키는 `RECT` 또는 `CRect` 소스 사각형을 포함 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 Union이 비어 있습니다. 0이 아닌 union이 비어 있으면 0입니다.  
  
### <a name="remarks"></a>설명  
 공용 구조체는 두 개의 소스 사각형이 포함 된 가장 작은 사각형입니다.  
  
 Windows; 빈 사각형의 크기를 무시합니다. 즉, 높이 없음 되었거나에 없는 폭이 지정 된 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#56](../../atl-mfc-shared/codesnippet/CPP/crect-class_33.cpp)]  
  
##  <a name="a-namecrectwidtha-crectwidth"></a><a name="crect__width"></a>  CRect::Width  
 폼의 너비를 계산 `CRect` 값 오른쪽에서 왼쪽된 값을 빼서 합니다.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 너비 `CRect`합니다.  
  
### <a name="remarks"></a>설명  
 너비는 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#crect__normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#57](../../atl-mfc-shared/codesnippet/CPP/crect-class_34.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPoint 클래스](../../atl-mfc-shared/reference/cpoint-class.md)   
 [CSize 클래스](../../atl-mfc-shared/reference/csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)

