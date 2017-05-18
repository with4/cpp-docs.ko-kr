---
title: "CPoint 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 6b1afeea5a1d55fb3317b432871f2ed15dd5d19e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cpoint-class"></a>CPoint 클래스
Windows `POINT` 구조체와 유사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPoint : public tagPOINT 
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPoint::CPoint](#cpoint)|`CPoint`를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPoint::Offset](#offset)|값을 추가 하는 **x** 및 **y** 의 멤버는 `CPoint`합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|차이 반환 된 `CPoint` 및 크기, 또는 점, 또는 두 점 또는 음수 크기에 따라 오프셋 사이의 크기 차이의 부정입니다.|  
|[CPoint::operator! =](#operator_neq)|두 점 사이의 다른 지 확인 합니다.|  
|[CPoint::operator +](#operator_add)|합을 반환 하는 `CPoint` , 크기, 지점, 또는 `CRect` 크기 만큼 오프셋 합니다.|  
|[CPoint::operator + =](#operator_add_eq)|오프셋 `CPoint` 크기 또는 포인트를 추가 합니다.|  
|[-= CPoint::operator](#operator_-_eq)|오프셋 `CPoint` 크기 또는 포인트를 빼는 방식으로 합니다.|  
|[CPoint::operator = =](#operator_eq_eq)|두 점 사이의 같은지 확인 합니다.|  
  
## <a name="remarks"></a>주의  
 조작 하는 멤버 함수에도 `CPoint` 및 [지점](../../mfc/reference/point-structure1.md) 구조입니다.  
  
 A `CPoint` 개체 일 수 아무 곳에 나 사용 되는 `POINT` 구조체를 사용 합니다. 둘 중 하나는 "크기" 상호 작용 하는이 클래스의 연산자 허용 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체 또는 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조를 두는 동일 하 게 사용 합니다.  
  
> [!NOTE]
>  이 클래스에서 파생 되는 `tagPOINT` 구조입니다. (이름 `tagPOINT` 에 대 한 자주 사용 하지 않는 이름인는 `POINT` 구조입니다.) 즉, 데이터 멤버는 `POINT` 구조 `x` 및 `y`의 액세스 가능 데이터 멤버가 `CPoint`합니다.  
  
> [!NOTE]
>  대 한 자세한 내용은 공유 유틸리티 클래스 (같은 `CPoint`), 참조 [공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagPOINT`  
  
 `CPoint`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltypes.h  
  
##  <a name="cpoint"></a>CPoint::CPoint
 `CPoint` 개체를 생성합니다.  
  
```  
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `initX`  
 `x`의 `CPoint` 멤버 값을 지정합니다.  
  
 `initY`  
 `y`의 `CPoint` 멤버 값을 지정합니다.  
  
 `initPt`  
 [지점](../../mfc/reference/point-structure1.md) 구조 또는 `CPoint` 초기화 하는 데 사용 되는 값을 지정 하는 `CPoint`합니다.  
  
 `initSize`  
 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 초기화 하는 데 사용 되는 값을 지정 하는 `CPoint`합니다.  
  
 `dwPoint`  
 `x` 멤버를 `dwPoint`의 하위 단어로 설정하고 `y` 멤버를 `dwPoint`의 상위 단어로 설정합니다.  
  
### <a name="remarks"></a>주의  
 인수가 지정되지 않으면 `x` 및 `y` 멤버가 0으로 설정됩니다.  
  
### <a name="example"></a>예제  
  
```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too  
 
POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;  
 
CPoint   ptMFCHere(ptHere);
 
// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;  
 
CPoint ptMFCBig(sHowBig); 
// or from a DWORD  
 
DWORD   dwSize;  
dwSize = MAKELONG(35, 95);
 
CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```  
  
##  <a name="offset"></a>CPoint::Offset  
 값을 추가 하는 **x** 및 **y** 의 멤버는 `CPoint`합니다.  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *사분면*  
 오프셋할 크기를 지정 된 **x** 의 멤버는 `CPoint`합니다.  
  
 *y 오프셋*  
 오프셋할 크기를 지정 된 **y** 의 멤버는 `CPoint`합니다.  
  
 `point`  
 크기 지정 ( [지점](../../mfc/reference/point-structure1.md) 또는 `CPoint`) 오프셋의 `CPoint`합니다.  
  
 `size`  
 크기 지정 ( [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md)) 오프셋의 `CPoint`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&28;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CPoint::operator = =  
 두 점 사이의 같은지 확인 합니다.  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 `CPoint` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 Points 같으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&29;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CPoint::operator! =  
 두 점 사이의 다른 지 확인 합니다.  
  
```  
BOOL operator!=(POINT point) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 `CPoint` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 개체가 동일 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&30;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CPoint::operator + =  
 크기를 추가 하는 첫 번째 오버 로드는 `CPoint`합니다.  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 포함 된 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.  
  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 에 점을 추가 하는 두 번째 오버 로드는 `CPoint`합니다.  
  
 두 경우 모두, 추가 추가 하 여 수행 됩니다는 **x** (또는 **cx**) 멤버에는 오른쪽 피연산자의는 **x** 의 멤버는 `CPoint` 추가 하 고는 **y** (또는 **cy**)는 오른쪽 피연산자의 멤버는 **y** 의 멤버는 `CPoint`.  
  
 예를 들어 추가 `CPoint(5, -7)` 포함 된 변수에 `CPoint(30, 40)` 변수를 변경 `CPoint(35, 33)`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&31;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>-= CPoint::operator  
 첫 번째 오버 로드에서 크기를 뺍니다는 `CPoint`합니다.  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 포함 된 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.  
  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 두 번째 오버 로드에서 점을 뺍니다는 `CPoint`합니다.  
  
 두 경우 모두 빼기를 빼는 방식으로 이루어집니다는 **x** (또는 **cx**)에서 오른쪽 피연산자의 멤버는 **x** 의 멤버는 `CPoint` 을 빼는 방법는 **y** (또는 **cy**)에서 오른쪽 피연산자의 멤버는 **y** 의 멤버는 `CPoint`합니다.  
  
 예를 들어 뺀 `CPoint(5, -7)` 포함 된 변수에서 `CPoint(30, 40)` 변수를 변경 `CPoint(25, 47)`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&32;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>CPoint::operator +  
 이 연산자를 사용 하 여 오프셋 `CPoint` 하 여는 `CPoint` 또는 `CSize` 개체 또는 오프셋 하는 `CRect` 하 여는 `CPoint`합니다.  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 포함 된 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.  
  
 `point`  
 포함 된 [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.  
  
 `lpRect`  
 에 대 한 포인터를 포함 한 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CPoint` 하는 크기에 따라 오프셋 되는 **CPoint** 한 지점에서 오프셋 되는 또는 **CRect** 지점으로 오프셋입니다.  
  
### <a name="remarks"></a>주의  
 예를 들어를 사용 하 여 처음 두 개의 오버 로드 중 하나는 지점 오프셋 `CPoint(25, -19)` 지점 `CPoint(15, 5)` 또는 크기 `CSize(15, 5)` 값을 반환 `CPoint(40, -14)`합니다.  
  
 오프셋 되 고 후 사각형을 반환 지점에 사각형을 추가 **x** 및 **y** 지점에 지정 된 값입니다. 예를 들어 마지막 오버 로드를 사용 하 여 사각형 오프셋 `CRect(125, 219, 325, 419)` 지점 `CPoint(25, -19)` 반환 `CRect(150, 200, 350, 400)`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&33;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>CPoint::operator-  
 사용 하는 처음 두 개의 오버 로드 중 하나는 `CPoint` 또는 `CSize` 에서 개체 `CPoint`합니다.  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `point`  
 A [지점](../../mfc/reference/point-structure1.md) 구조 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 개체입니다.  
  
 `size`  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 또는 [CSize](../../atl-mfc-shared/reference/csize-class.md) 개체입니다.  
  
 `lpRect`  
 에 대 한 포인터는 [RECT](../../mfc/reference/rect-structure1.md) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CSize` 두 점 사이의 차이 나타내는 `CPoint` 하 되는 크기의 부정 납니다는 `CRect` 점의 부정 되 납니다 또는 `CPoint` 점의 부정입니다.  
  
### <a name="remarks"></a>주의  
 세 번째 오버 로드는 오프셋을 `CRect` 의 부정 하 여 `CPoint`합니다. 마지막으로, 단항 연산자를 사용 하 여 부정할 `CPoint`합니다.  
  
 예를 들어, 첫 번째 오버 로드를 사용 하 여 두 점 사이의 차이 확인 하려면 `CPoint(25, -19)` 및 `CPoint(15, 5)` 반환 `CSize(10, -24)`합니다.  
  
 빼기는 `CSize` 에서 `CPoint` 위와 같은 계산을 수행 하지만 반환는 `CPoint` 개체가 아니라는 `CSize` 개체입니다. 예를 들어, 두 번째 오버 로드를 사용 하 여 지점 사이의 차이 확인 하려면 `CPoint(25, -19)` 및 크기 `CSize(15, 5)` 반환 `CPoint(10, -24)`합니다.  
  
 부정 하 여 사각형 오프셋을 반환 하는 지점에서 사각형을 뺀는 **x** 및 **y** 지점에 지정 된 값입니다. 예를 들어 마지막 오버 로드를 사용 하 여 사각형 오프셋 `CRect(125, 200, 325, 400)` 지점에서 `CPoint(25, -19)` 반환 `CRect(100, 219, 300, 419)`합니다.  
  
 단항 연산자를 사용 하 여 점을 부정 합니다. 예를 들어 단항 연산자를 사용 하 여 지점과 `CPoint(25, -19)` 반환 `CPoint(-25, 19)`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&34;](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDI](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [POINT 구조체](../../mfc/reference/point-structure1.md)   
 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)   
 [CSize 클래스](../../atl-mfc-shared/reference/csize-class.md)




