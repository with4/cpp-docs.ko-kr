---
title: "CRect 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRect
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fa528d300c546bfdeaab55ff88735efcaf8533a5
ms.lasthandoff: 02/24/2017

---
# <a name="crect-class"></a>CRect 클래스
Windows와 유사한 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRect::CRect](#crect)|`CRect` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|오른쪽 아래 지점을 반환 `CRect`합니다.|  
|[CRect::CenterPoint](#centerpoint)|중심점 반환 `CRect`합니다.|  
|[CRect::CopyRect](#copyrect)|소스 사각형의 크기를 복사 `CRect`합니다.|  
|[CRect::DeflateRect](#deflaterect)|높이 너비 감소 `CRect`합니다.|  
|[CRect::EqualRect](#equalrect)|결정 여부 `CRect` 은 지정 된 사각형에과 같습니다.|  
|[CRect::Height](#height)|높이 계산 `CRect`합니다.|  
|[CRect::InflateRect](#inflaterect)|너비 및 높이 늘리는 `CRect`합니다.|  
|[CRect::IntersectRect](#intersectrect)|집합 `CRect` 두 개의 사각형의 교차 부분으로 동일 합니다.|  
|[CRect::IsRectEmpty](#isrectempty)|결정 여부 `CRect` 비어 있습니다. `CRect`너비 및 높이 0에서 하는 경우 비어 있습니다.|  
|[CRect::IsRectNull](#isrectnull)|결정 여부는 **위쪽**, **아래쪽**, **왼쪽**, 및 **오른쪽** 멤버 변수는 모두 0으로 동등 합니다.|  
|[CRect::MoveToX](#movetox)|이동 `CRect` 지정한 x 좌표입니다.|  
|[CRect::MoveToXY](#movetoxy)|이동 `CRect` 에 지정 된 x 및 y 좌표가 있습니다.|  
|[CRect::MoveToY](#movetoy)|이동 `CRect` 지정 y-좌표입니다.|  
|[Crect:: Normalizerect](#normalizerect)|너비와 높이 표준화 `CRect`합니다.|  
|[CRect::OffsetRect](#offsetrect)|이동 `CRect` 지정 된 오프셋으로 합니다.|  
|[CRect::PtInRect](#ptinrect)|지정된 된 지점 내에 있는지 여부를 확인 `CRect`합니다.|  
|[CRect::SetRect](#setrect)|크기를 설정 `CRect`합니다.|  
|[CRect::SetRectEmpty](#setrectempty)|집합 `CRect` 빈 사각형 (모든 좌표에 해당 하는 0)에 있습니다.|  
|[CRect::Size](#size)|크기를 계산 `CRect`합니다.|  
|[CRect::SubtractRect](#subtractrect)|다른 한 사각형을 뺍니다.|  
|[CRect::TopLeft](#topleft)|왼쪽 위 지점을 반환 `CRect`합니다.|  
|[CRect::UnionRect](#unionrect)|집합 `CRect` 같은 두 개의 사각형의 합집합입니다.|  
|[CRect::Width](#width)|폼의 너비를 계산 `CRect`합니다.|  
  
### <a name="public-operators"></a>Public 연산자    
|이름|설명|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|지정 된 오프셋을 뺍니다 `CRect` 수축 또는 `CRect` 결과 반환 하 고 `CRect`합니다.|  
|[LPCRECT CRect::operator](#operator_lpcrect)|변환 된 `CRect` 에 **LPCRECT**합니다.|  
|[LPRECT CRect::operator](#operator_lprect)|변환 된 `CRect` 에 `LPRECT`합니다.|  
|[CRect::operator! =](#operator_neq)|결정 여부 `CRect` 사각형 같지 않습니다.|  
|[CRect::operator&amp;](#operator_amp)|교차 부분을 만듭니다 `CRect` 및 사각형 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator&amp;=](#operator_amp_eq)|집합 `CRect` 의 교차점으로 같은 `CRect` 및 사각형입니다.|  
|[CRect::operator |](#operator_or)|합집합을 만듭니다 `CRect` 및 사각형 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator |=](#operator_or_eq)|집합 `CRect` 의 합집합 같지 `CRect` 및 사각형입니다.|  
|[CRect::operator +](#operator_add)|지정 된 오프셋을 추가 하는 `CRect` 팽창 또는 `CRect` 결과 반환 하 고 `CRect`합니다.|  
|[CRect::operator + =](#operator_add_eq)|지정 된 오프셋을 추가 하는 `CRect` 팽창 또는 `CRect`합니다.|  
|[CRect::operator =](#operator_eq)|복사 하는 사각형의 크기 `CRect`합니다.|  
|[-= CRect::operator](#operator_-_eq)|지정 된 오프셋을 뺍니다 `CRect` 수축 또는 `CRect`합니다.|  
|[CRect::operator = =](#operator_eq_eq)|결정 여부 `CRect` 사각형 같습니다.|  
  
## <a name="remarks"></a>주의  
 `CRect`또한 조작 하는 멤버 함수를 포함 `CRect` 개체 및 Windows `RECT` 구조입니다.  
  
 A `CRect` 개체를 함수 매개 변수로 전달할 수 있습니다 언제나는 `RECT` 구조 **LPCRECT**, 또는 `LPRECT` 전달 될 수 있습니다.  
  
> [!NOTE]
>  이 클래스에서 파생 되는 **tagRECT** 구조입니다. (이름 **tagRECT** 는 덜 일반적으로 사용에 대 한 이름인는 `RECT` 구조입니다.) 즉, 데이터 멤버 (**왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽**)의 `RECT` 구조 액세스할 수 있는 데이터의 멤버인 `CRect`합니다.  
  
 A `CRect` 사각형의 왼쪽 위 및 오른쪽 아래 지점을 정의 하는 멤버 변수가 포함 되어 있습니다.  
  
 지정 하는 경우는 `CRect`을 정규화 할 수 있도록 구성 하는 주의 해야-즉, 왼쪽된 좌표 값을 사용 하면 위쪽과 오른쪽 보다 작으면 되도록 보다 작으면 아래쪽입니다. 예를 들어 top (10,10)의 왼쪽 (20,20)의 오른쪽 아래에 정사각형을 정의 하지만 top (20,20)의 왼쪽 및 (10,10)의 오른쪽 아래에서 정규화 되지 않은 사각형을 정의 합니다. 사각형 정규화 되지 않으므로 많은 경우 `CRect` 멤버 함수는 잘못 된 결과 반환할 수 있습니다. (참조 [crect:: Normalizerect](#normalizerect) 이러한 함수 목록은.) 정규화 되지 않은 사각형을 정규화 할 수를 호출 하 여 정규화 된 사각형을 필요로 하는 함수를 호출 하기 전에 `NormalizeRect` 함수입니다.  
  
 조작할 때는 주의 `CRect` 와 [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp) 및 [CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp) 멤버 함수입니다. 디스플레이 컨텍스트 매핑 모드는 y-익스텐트가 음수인 경우에서 같이 `MM_LOENGLISH`, 다음 `CDC::DPtoLP` 변환는 `CRect` top 아래쪽 보다 크면 되도록 합니다. 와 같은 함수가 **높이** 및 **크기** 그런 다음 변환 된 높이 대 한 음수 값을 반환 합니다 `CRect`, 사각형 정규화 되지 않은 잠금 해제 됩니다.  

  
 사용 하 여이 오버 로드 `CRect` 연산자, 첫 번째 피연산자는 반드시는 `CRect`; 두 번째 수는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 개체.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltypes.h  
  
##  <a name="a-namebottomrighta--crectbottomright"></a><a name="bottomright"></a>CRect::BottomRight  
 좌표에 대 한 참조로 반환 되는 [CPoint](cpoint-class.md) 개체에 포함 된 `CRect`합니다.  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 사각형의 오른쪽 아래 모퉁이의 좌표입니다.  
  
### <a name="remarks"></a>주의  
 Get 또는 set 사각형의 오른쪽 아래 모서리에이 함수를 사용할 수 있습니다. 할당 연산자의 왼쪽에이 함수를 사용 하 여 모퉁이 설정 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 // use BottomRight() to retrieve the bottom
 // right POINT 
 CRect rect(210, 150, 350, 900);
 CPoint ptDown;

 ptDown = rect.BottomRight();

 // ptDown is now set to (350, 900)
 ASSERT(ptDown == CPoint(350, 900));

 // or, use BottomRight() to set the bottom
 // right POINT 
 CRect rect2(10, 10, 350, 350);
 CPoint ptLow(180, 180);

   CRect rect2(10, 10, 350, 350);
   CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

   // rect2 is now (10, 10, 180, 180)
   ASSERT(rect2 == CRect(10, 10, 180, 180));   
```
  
##  <a name="a-namecenterpointa--crectcenterpoint"></a><a name="centerpoint"></a>CRect::CenterPoint 
 계산의 중심점 `CRect` 왼쪽 및 오른쪽 값을 추가 하 고&2;로 하 고 위쪽 및 아래쪽 값을 추가 나누고&2;로 나눈 합니다.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 A `CPoint` 개체의 중심점입니다 `CRect`합니다.  
  
### <a name="example"></a>예제  
```cpp  
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog. 
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);


    // device context for painting

    // get the size and position of the client area of 
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT 
  // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```
  
##  <a name="a-namecopyrecta--crectcopyrect"></a><a name="copyrect"></a>CRect::CopyRect  
 복사본은 `lpSrcRect` 사각형으로 `CRect`합니다.  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lpSrcRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 복사 될 개체입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rectSource(35, 10, 125, 10);
 CRect rectDest;

 rectDest.CopyRect(&rectSource);

 // rectDest is now set to (35, 10, 125, 10)

 RECT rectSource2;
 rectSource2.left = 0;
 rectSource2.top = 0;
 rectSource2.bottom = 480;
 rectSource2.right = 640;

 rectDest.CopyRect(&rectSource2);

 // works against RECT structures, too!
 // rectDest is now set to (0, 0, 640, 480)   
```

  
##  <a name="a-namecrecta--crectcrect"></a><a name="crect"></a>CRect::CRect  
 `CRect` 개체를 생성합니다.  
  
```  
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();  
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
  
### <a name="remarks"></a>주의  
 인수 없이 제공 **왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽** 멤버는 초기화 되지 않습니다.  
  
 `CRect`(**const RECT < /**) 및 `CRect`(**LPCRECT**) 생성자는 수행 된 [CopyRect](#copyrect)합니다. 다른 생성자는 직접 개체의 멤버 변수를 초기화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 // default constructor doesn't initialize!
 CRect rectUnknown;

 // four-integers are left, top, right, and bottom
 CRect rect(0, 0, 100, 50);
 ASSERT(rect.Width() == 100);
 ASSERT(rect.Height() == 50);

 // Initialize from RECT stucture
 RECT sdkRect;
 sdkRect.left = 0;
 sdkRect.top = 0;
 sdkRect.right = 100;
 sdkRect.bottom = 50;

 CRect rect2(sdkRect);
 // by reference
 CRect rect3(&sdkRect);


 // by address
 ASSERT(rect2 == rect);
 ASSERT(rect3 == rect);

 // from a point and a size
 CPoint pt(0, 0);
 CSize sz(100, 50);
 CRect rect4(pt, sz);
 ASSERT(rect4 == rect2);

 // from two points
 CPoint ptBottomRight(100, 50);
 CRect rect5(pt, ptBottomRight);
 ASSERT(rect5 == rect4);  
```
  
##  <a name="a-namedeflaterecta--crectdeflaterect"></a><a name="deflaterect"></a>CRect::DeflateRect  
 `DeflateRect`수축 `CRect` 의 측면의 중심을 향해 이동 하 여 합니다.  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 왼쪽 deflate 단위 수의 왼쪽과 오른쪽 지정 `CRect`합니다.  
  
 *y*  
 위쪽 및 아래쪽을 deflate 단위 수를 지정 `CRect`합니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 또는 [CSize](csize-class.md) deflate 단위 수를 지정 하는 `CRect`합니다. `cx` 좌 변과 우변을 deflate 단위 수를 지정 하는 값 및 `cy` 값 위쪽 및 아래쪽 deflate 단위 수를 지정 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이렇게 하려면 `DeflateRect` left 및 top에 장치를 추가 하 고 오른쪽 아래에서 단위를 뺍니다. 매개 변수 `DeflateRect` 서명 된 값으로 deflate 양수 값 `CRect` 및 음수 값을 확장할 것입니다.  
  
 처음 두 개의 오버 로드 두 쌍의 반대편의 deflate `CRect` 두 번의 전체 너비 감소 되도록 *x* (또는 `cx`) 두 번의 전체 높이 감소 및 *y* (또는 `cy`). 다른 두 오버 로드의 각 면 deflate `CRect` 독립적입니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);
   
   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);   
```
  
##  <a name="a-nameequalrecta--crectequalrect"></a><a name="equalrect"></a>CRect::EqualRect  
 결정 여부 `CRect` 은 지정 된 사각형에과 같습니다.  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 사각형의 왼쪽 위 및 오른쪽 아래 모퉁이 좌표를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 두 개의 사각형 동일한 위쪽, 왼쪽, 아래쪽 및 오른쪽 값이 있습니다; 경우에 0이 아닌 그렇지 않으면 0입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
   ASSERT(!rect1.EqualRect(rect3));
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1.EqualRect(&test));  
```

##  <a name="a-nameheighta--crectheight"></a><a name="height"></a>CRect::Height  
 높이 계산 `CRect` 아래쪽 값에서 맨 위에 있는 값을 빼서 합니다.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 높이 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 결과 값은 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(20, 30, 80, 70);
 int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```

  
##  <a name="a-nameinflaterecta--crectinflaterect"></a><a name="inflaterect"></a>CRect::InflateRect  
 `InflateRect`팽창 `CRect` 중심 반대쪽의 측면을 이동 하 여 합니다.  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 왼쪽 확장할 단위 수의 왼쪽과 오른쪽 지정 `CRect`합니다.  
  
 *y*  
 위쪽 및 아래쪽을 확장할 단위 수를 지정 `CRect`합니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 또는 [CSize](csize-class.md) 을 확장할 단위의 수를 지정 하는 `CRect`합니다. `cx` 값을 왼쪽 및 오른쪽 확장할 단위의 수를 지정 및 `cy` 값을 위쪽 및 아래쪽 확장할 단위의 수를 지정 합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이렇게 하려면 `InflateRect` left 및 top에서 단위를 빼고를 오른쪽 아래에 장치를 추가 합니다. 매개 변수 `InflateRect` 서명 값 확장할 양수 값 `CRect` , 음수 값을 deflate 것입니다.  
  
 처음 두 개의 오버 로드 두 쌍의 반대편의 확장할 `CRect` 총 너비가 두 배로 증가 되도록 *x* (또는 `cx`) 하 고 총 높이 두 배로 증가 *y* (또는 `cy`). 다른 두 오버 로드의 각 면 확장할 `CRect` 독립적입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="a-nameintersectrecta--crectintersectrect"></a><a name="intersectrect"></a>CRect::IntersectRect  
 사용 하면는 `CRect` 두 개의 기존 사각형의 교차 부분으로 동일 합니다.  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.  
  
 `lpRect2`  
 가리키는 `RECT` 구조 또는 `CRect` 소스 사각형을 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 교차 비어 있지 않으면; 0이 아닌 교집합이 비어 있는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 교집합 모두 기존 사각형에 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rectOne(125, 0, 150, 200);
 CRect rectTwo(0, 75, 350,  95);
 CRect rectInter;

```cpp  
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
 ASSERT(rectInter == CRect(125, 75, 150, 95));
 // operator &= can do the same task:

 CRect rectInter2 = rectOne;
 rectInter2 &= rectTwo;
 ASSERT(rectInter2 == CRect(125, 75, 150, 95));  
```
  
##  <a name="a-nameisrectemptya--crectisrectempty"></a><a name="isrectempty"></a>CRect::IsRectEmpty  
 결정 여부 `CRect` 비어 있습니다.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 `CRect` 빈 않으면 0 경우 `CRect` 비어 있지 않습니다.  
  
### <a name="remarks"></a>주의  
 사각형 비어 너비 및 높이 0 또는 음수 됩니다. 다른 `IsRectNull`, 사각형의 모든 좌표는&0;이 있는지 여부를 결정 하는 합니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());   
```

  
##  <a name="a-nameisrectnulla--crectisrectnull"></a><a name="isrectnull"></a>CRect::IsRectNull  
 위쪽, 왼쪽, 아래쪽 있는지 여부를 결정 및의 값이 여기 `CRect` 은 모두 0입니다.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 `CRect`의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0이 고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 다른 `IsRectEmpty`, 사각형 비어 있는지 여부를 결정 하 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
 // note that null means _all_ zeros

 CRect rectNotNull(0, 0, 35, 50);
 ASSERT(!rectNotNull.IsRectNull());  
```
  
##  <a name="a-namemovetoxa--crectmovetox"></a><a name="movetox"></a>CRect::MoveToX  
 사각형을 지정 하 여 절대 x-좌표 이동 하려면이 함수를 호출 *x*합니다.  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToX(10);

```cpp  
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));   
```
  
##  <a name="a-namemovetoxya--crectmovetoxy"></a><a name="movetoxy"></a>CRect::MoveToXY  
 에 절대 x 및 y 좌표가 지정 된 사각형을 이동 하려면이 함수를 호출 합니다.  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 x 좌표입니다.  
  
 *y*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.  
  
 `point`  
 A **지점** 사각형의 절대 왼쪽 위 모퉁이 지정 하는 구조입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToXY(10, 10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));   
```

  
##  <a name="a-namemovetoya--crectmovetoy"></a><a name="movetoy"></a>CRect::MoveToY  
 사각형을 지정 하 여 절대 y-좌표 이동 하려면이 함수를 호출 *y*합니다.  
  
```  
void MoveToY(int y) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *y*  
 사각형의 왼쪽 위 모퉁이 대 한 절대 y 좌표입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```

  
##  <a name="a-namenormalizerecta--crectnormalizerect"></a><a name="normalizerect"></a>Crect:: Normalizerect  
 정규화 `CRect` 의 높이 너비는 양성 수 있도록 합니다.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>주의  
 사각형 네 번째 구성 요소 위치 지정에 대 한 정규화 된 좌표에 대 한 일반적으로 Windows를 사용 합니다. `NormalizeRect`위쪽 및 아래쪽 값을 비교 하 고 맨 아래 보다 큰 경우이 교환 합니다. 마찬가지로, 왼쪽에서 오른쪽 보다 큰 경우 left 및 right 값 바꿉니다. 이 함수는 서로 다른 매핑 모드를 처리할 때 유용 하 고 사각형을 반전 합니다.  
  
> [!NOTE]
>  다음 `CRect` 멤버 함수에는 제대로 작동 하려면 정규화 된 사각형 필요: [높이](#height), [너비](#width), [크기](#size), [IsRectEmpty](#isrectempty), [PtInRect](#ptinrect), [EqualRect](#equalrect), [UnionRect](#unionrect), [IntersectRect](#intersectrect), [SubtractRect](#subtractrect), [연산자 = =](#operator_eq_eq), [연산자! =](#operator_neq), [연산자 |](#operator_or), [연산자 | =](#operator_or_eq), [연산자 < /](#operator_amp), 및 [연산자 = / /](#operator_amp_eq)합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(110, 100, 250, 310);
 CRect rect2(250, 310, 110, 100);

```cpp  
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
   rect2.NormalizeRect();
 ASSERT(rect1 == rect2);  
```
  
##  <a name="a-nameoffsetrecta--crectoffsetrect"></a><a name="offsetrect"></a>CRect::OffsetRect  
 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 오른쪽 또는 왼쪽으로 이동 하 여 지정 합니다. 왼쪽으로 이동에 음수 여야 합니다.  
  
 *y*  
 위로 또는 아래로 이동할 거리를 지정 합니다. 위로 이동 하려면 음수 여야 합니다.  
  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](cpoint-class.md) 이동 하는 크기를 모두 지정 하는 개체입니다.  
  
 `size`  
 포함 된 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](csize-class.md) 이동 하는 크기를 모두 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이동 `CRect` *x* 단위는 x 축 및 *y* y 축의 단위입니다. *x* 및 *y* 매개 변수는 부호 있는 값 하므로 `CRect` 왼쪽 이동 하거나 오른쪽 및 또는 축소 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 35, 35);
 rect.OffsetRect(230, 230);

```cpp  
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));   
```

  
##  <a name="a-nameoperatorlpcrecta--crectoperator-lpcrect-converts-a-crect-to-an-lpcrectmfcreferencedata-types-mfcmd"></a><a name="operator_lpcrect"></a>CRect::operator LPCRECT 변환은 `CRect` 에 [LPCRECT](../../mfc/reference/data-types-mfc.md)합니다.  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>주의  
 Address-of 않아도이 기능을 사용할 때 (**&**) 연산자. 전달 하는 경우이 연산자 자동으로 사용 된 `CRect` 필요로 하는 함수에는 개체는 **LPCRECT**합니다.  
  

##  <a name="a-nameoperatorlprecta--crectoperator-lprect"></a><a name="operator_lprect"></a>LPRECT CRect::operator  
 변환 된 `CRect` 에 [LPRECT](../../mfc/reference/data-types-mfc.md)합니다.  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>주의  
 Address-of 않아도이 기능을 사용할 때 (**&**) 연산자. 전달 하는 경우이 연산자 자동으로 사용 된 `CRect` 필요로 하는 함수에는 개체는 `LPRECT`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::operator LPCRECT](#operator_lpcrect)합니다.  
  
##  <a name="a-nameoperatoreqa--crectoperator-"></a><a name="operator_eq"></a>CRect::operator =  
 할당 *srcRect* 를 `CRect`합니다.  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *srcRect*  
 소스 사각형을 가리킵니다. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(0, 0, 127, 168);
 CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```

  
##  <a name="a-nameoperatoreqeqa--crectoperator-"></a><a name="operator_eq_eq"></a>CRect::operator = =  
 결정 여부 `rect` 같으면 `CRect` 의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여 합니다.  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형을 가리킵니다. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1 == test);  
```

  
##  <a name="a-nameoperatorneqa--crectoperator-"></a><a name="operator_neq"></a>CRect::operator! =  
 결정 여부 `rect` 과 같지 않은 `CRect` 의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 비교 하 여 합니다.  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형을 가리킵니다. Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>반환 값  
 개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 != rect3);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect3 != test);  
```
  
##  <a name="a-nameoperatoraddeqa--crectoperator-"></a><a name="operator_add_eq"></a>CRect::operator + =  
 처음 두 개의 오버 로드가 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](cpoint-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](csize-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 단위를의 양쪽을 확장할 수 있는 개체 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값에 추가 됩니다 `CRect`합니다.  
  
 세 번째 오버 로드 팽창 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);   
```
  
##  <a name="a-nameoperator-eqa--crectoperator--"></a><a name="operator_-_eq"></a>-= CRect::operator  
 처음 두 개의 오버 로드가 이동 `CRect` 지정 된 오프셋으로 합니다.  
  
```  
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](cpoint-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](csize-class.md) 사각형을 이동할 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` deflate의 각 측면에 대 한 단위 수를 포함 하는 개체 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 값에서 빼면 `CRect`합니다.  
  
 세 번째 오버 로드 수축 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수입니다. 이 오버 로드와 같은 함수는 [DeflateRect](#deflaterect)합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```
  
##  <a name="a-nameoperatorampeqa--crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect::operator&amp;=  
 집합 `CRect` 의 교차점으로 같은 `CRect` 및 `rect`합니다.  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 교집합에 두 개의 사각형이 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::IntersectRect](#intersectrect)합니다.  
  
##  <a name="a-nameoperatororeqa--crectoperator-124"></a><a name="operator_or_eq"></a>CRect::operator | =  
 집합 `CRect` 의 합집합 같지 `CRect` 및 `rect`합니다.  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 포함 된 `CRect` 또는 [RECT](../../mfc/reference/rect-structure1.md)합니다.  
  
### <a name="remarks"></a>주의  
 공용 구조체는 두 개의 소스 사각형이 포함 된 가장 작은 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```

  
##  <a name="a-nameoperatoradda--crectoperator-"></a><a name="operator_add"></a>CRect::operator +  
 처음 두 개의 오버 로드 반환는 `CRect` 개체 같음 `CRect` 지정 된 오프셋에 의해 치환입니다.  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](cpoint-class.md) 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](csize-class.md) 반환 값을 이동 하는 단위 수를 지정 하는 개체입니다.  
  
 `lpRect`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 을 반환 값의 각 면 확장할 단위의 수를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 `CRect` 이동 하거나 늘려 결과 `CRect` 매개 변수에 지정 하는 단위 수입니다.  
  
### <a name="remarks"></a>주의  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`)에 매개 변수는 추가 `CRect`위치 합니다.  
  
 세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 확장 합니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);   
```

  
##  <a name="a-nameoperator-a--crectoperator--"></a><a name="operator_-"></a>CRect::operator-  
 처음 두 개의 오버 로드 반환는 `CRect` 개체 같음 `CRect` 지정 된 오프셋에 의해 치환입니다.  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
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
  
### <a name="remarks"></a>주의  
 매개 변수의 *x* 및 *y* (또는 `cx` 및 `cy`) 매개 변수에서 뺀 `CRect`위치 합니다.  
  
 세 번째 오버 로드는 새 반환 `CRect` 와 같은 `CRect` 매개 변수의 각 멤버에 지정 된 단위 수로 축소 됩니다. 이 오버 로드와 같은 함수는 [DeflateRect](#deflaterect)이 아니라 [SubtractRect](#subtractrect)합니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);   
```

  
##  <a name="a-nameoperatorampa--crectoperator-amp"></a><a name="operator_amp"></a>CRect::operator&amp;  
 반환 된 `CRect` 의 교집합 즉 `CRect` 및 *rect2*.  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *rect2*  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 의 교집합 즉 `CRect` 및 *rect2*합니다.  
  
### <a name="remarks"></a>주의  
 교집합에 두 개의 사각형이 포함 된 가장 큰 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="a-nameoperatorora--crectoperator-124"></a><a name="operator_or"></a>CRect::operator |  
 반환 된 `CRect` 의 합집합 즉 `CRect` 및 *rect2*합니다.  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *rect2*  
 포함 된 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect`합니다.  
  
### <a name="return-value"></a>반환 값  
 A `CRect` 의 합집합 즉 `CRect` 및 *rect2*합니다.  
  
### <a name="remarks"></a>주의  
 공용 구조체는 두 개의 사각형이 포함 된 가장 작은 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 CRect rect3;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="a-nameptinrecta--crectptinrect"></a><a name="ptinrect"></a>CRect::PtInRect  
 지정된 된 지점 내에 있는지 여부를 확인 `CRect`합니다.  
  
```   
BOOL PtInRect(POINT point) const throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](cpoint-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 지점 내에 0이 아닌 `CRect`그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 안에 점이 `CRect` 왼쪽 이나 위쪽 측면에서 네 면 모두 내 여부입니다. 외부 오른쪽 또는 아래쪽 쪽 점은 `CRect`합니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(5, 5, 100, 100);
 CPoint pt1(35, 50);
 CPoint pt2(125, 298);

 // this is true, because pt1 is inside the rectangle
 ASSERT(rect.PtInRect(pt1));

 // this is NOT true, because pt2 is outside the rectangle
 ASSERT(!rect.PtInRect(pt2));

 // note that the right and the bottom aren't inside
 ASSERT(!rect.PtInRect(CPoint(35, 100)));
 ASSERT(!rect.PtInRect(CPoint(100, 98)));

 // but the top and the left are inside
 ASSERT(rect.PtInRect(CPoint(5, 65)));
 ASSERT(rect.PtInRect(CPoint(88, 5)));

 // and that PtInRect() works against a POINT, too
 POINT pt;
 pt.x = 35;
 pt.y = 50;
 ASSERT(rect.PtInRect(pt));  
```
  
##  <a name="a-namesetrecta--crectsetrect"></a><a name="setrect"></a>CRect::SetRect  
 크기를 설정 `CRect` 지정 된 좌표입니다.  
  
```   
void SetRect(int x1, int y1, int x2, int y2) throw(); 
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
```cpp  
 CRect rect;
 rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```

  
##  <a name="a-namesetrectemptya--crectsetrectempty"></a><a name="setrectempty"></a>CRect::SetRectEmpty  
 사용 하면 `CRect` 모든 좌표를&0;으로 설정 하 여 null 사각형입니다.  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>예제  
```cpp  
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());  
```
  
##  <a name="a-namesizea--crectsize"></a><a name="size"></a>CRect::SIZE 
 `cx` 및 `cy` 멤버의 반환 값의 너비와 높이가 포함 `CRect`합니다.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 A [CSize](csize-class.md) 개체의 크기를 포함 하는 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 너비 또는 높이 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="a-namesubtractrecta--crectsubtractrect"></a><a name="subtractrect"></a>CRect::SubtractRect  
 크기를 사용 하면는 **CRect** 의 빼기 같음 `lpRectSrc2` 에서 `lpRectSrc1`합니다.  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRectSrc1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 `CRect` 사각형을 뺄 개체입니다.  
  
 `lpRectSrc2`  
 가리키는 `RECT` 구조 또는 `CRect` 가리키는 개체에는 사각형에서 뺄는 `lpRectSrc1` 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 빼기는 모든 요소를 포함 하는 가장 작은 사각형 `lpRectScr1` 의 교집합에 없는 `lpRectScr1` 및 *lpRectScr2*합니다.  
  
 으로 지정 된 사각형 `lpRectSrc1` 은 변경 되지 사각형으로 지정 된 경우 `lpRectSrc2` 으로 지정 된 사각형을 완전히 겹치지 않는 *lpRectSrc1* 하나 이상의의 x-또는 y-지시 합니다.  
  
 예를 들어 경우 `lpRectSrc1` 되었습니다 (10,10, 100100) 및 `lpRectSrc2` 되었습니다 (50,50, 150,150) 가리키는 사각형 `lpRectSrc1` 는 변경 되지 함수가 반환 하는 경우. 그러나 경우 `lpRectSrc1` 되었습니다 (10,10, 100100) 및 `lpRectSrc2` 되었습니다 (50,10, 150,150) 사각형 가리키는 `lpRectSrc1` (10,10, 50,100) 정보를 포함 하는 함수가 반환 된 경우.  
  
 `SubtractRect`와 동일 하지는 [연산자-](#operator_-) 나 [-= 연산자](#operator_-_eq)합니다. 이러한 연산자에 해당 하지 않거나 적 호출 `SubtractRect`합니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);   
```
  
##  <a name="a-nametoplefta--crecttopleft"></a><a name="topleft"></a>CRect::TopLeft  
 좌표에 대 한 참조로 반환 되는 [CPoint](cpoint-class.md) 개체에 포함 된 `CRect`합니다.  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 사각형의 왼쪽 위 모퉁이의 좌표입니다.  
  
### <a name="remarks"></a>주의  
 Get 또는 set 사각형의 왼쪽 위 모퉁이를이 함수를 사용할 수 있습니다. 할당 연산자의 왼쪽에이 함수를 사용 하 여 모퉁이 설정 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CRect::CenterPoint](#centerpoint)합니다.  
  
##  <a name="a-nameunionrecta--crectunionrect"></a><a name="unionrect"></a>CRect::UnionRect  
 크기를 사용 하면 `CRect` 같으면 두 소스 사각형의 합집합입니다.  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect1`  
 가리키는 [RECT](../../mfc/reference/rect-structure1.md) 또는 `CRect` 소스 사각형을 포함 하는 합니다.  
  
 `lpRect2`  
 가리키는 `RECT` 또는 `CRect` 소스 사각형을 포함 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 Union이 비어 있습니다. 0이 아닌 union이 비어 있으면 0입니다.  
  
### <a name="remarks"></a>주의  
 공용 구조체는 두 개의 소스 사각형이 포함 된 가장 작은 사각형입니다.  
  
 Windows; 빈 사각형의 크기를 무시합니다. 즉, 높이 없음 되었거나에 없는 폭이 지정 된 사각형입니다.  
  
> [!NOTE]
>  모두 사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```
 
##  <a name="a-namewidtha--crectwidth"></a><a name="width"></a>CRect::Width  
 폼의 너비를 계산 `CRect` 값 오른쪽에서 왼쪽된 값을 빼서 합니다.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 너비 `CRect`합니다.  
  
### <a name="remarks"></a>주의  
 너비는 음수일 수 있습니다.  
  
> [!NOTE]
>  사각형을 표준화 해야 하거나이 함수는 실패할 수 있습니다. 호출할 수 있습니다 [NormalizeRect](#normalizerect) 를이 함수를 호출 하기 전에 사각형을 정규화 합니다.  
  
### <a name="example"></a>예제  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>참고 항목  
 [CPoint 클래스](cpoint-class.md)   
 [CSize 클래스](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)



