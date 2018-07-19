---
title: CSize 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0494b22d3166ebfd75a6aeaceba839f80b84bc1
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884407"
---
# <a name="csize-class"></a>CSize 클래스
상대 좌표 또는 위치를 구현하는 Windows [SIZE](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조체와 유사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSize::CSize](#csize)|`CSize` 개체를 생성합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|두 가지 크기를 뺍니다.|  
|[CSize::operator! =](#operator_neq)|이 다른 지 확인 `CSize` 및 크기입니다.|  
|[CSize::operator +](#operator_add)|두 가지 크기를 추가합니다.|  
|[CSize::operator + =](#operator_add_eq)|추가 크기 `CSize`합니다.|  
|[CSize::operator =](#operator_-_eq)|크기를 뺍니다 `CSize`합니다.|  
|[CSize::operator = =](#operator_eq_eq)|같은지 확인 `CSize` 및 크기입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스에서 파생 되는 `SIZE` 구조입니다. 즉, 전달할 수 있습니다는 `CSize` 필요로 하는 매개 변수를 `SIZE` 하 고의 데이터 멤버를 `SIZE` 구조는 액세스할 수 있는 데이터 멤버의 `CSize`합니다.  
  
 `cx` 하 고 `cy` 멤버인 `SIZE` (및 `CSize`)는 공용입니다. 또한 `CSize` 조작 하는 멤버 함수를 구현 하는 `SIZE` 구조입니다.  
  
> [!NOTE]
>  공유 유틸리티 클래스에 대 한 자세한 (같은 `CSize`)를 참조 하세요 [공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltypes.h  
  
##  <a name="csize"></a>  CSize::CSize  
 `CSize` 개체를 생성합니다.  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *initCX*  
 집합의 `cx` 에 대 한 멤버는 `CSize`합니다.  
  
 *initCY*  
 집합의 `cy` 에 대 한 멤버는 `CSize`합니다.  
  
 *initSize*  
 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조 나 `CSize` 개체를 초기화 하는 데 `CSize`합니다.  
  
 *initPt*  
 [지점](../../mfc/reference/point-structure1.md) 구조 나 `CPoint` 개체를 초기화 하는 데 `CSize`합니다.  
  
 *dwSize*  
 DWORD 초기화 하는 데 `CSize`합니다. 하위 단어를 `cx` 멤버 이며 상위 단어를 `cy` 멤버입니다.  
  
### <a name="remarks"></a>설명  
 인수 없이 지정 된 경우 `cx` 고 `cy` 0으로 초기화 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CSize::operator = =  
 두 크기가 같은지 확인 합니다.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>설명  
 크기가 같으면 0이 아닌 반환 하 고, otherwize 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>  CSize::operator! =  
 두 크기가 같지 확인 합니다.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>설명  
 크기가 같지 않은 경우 0이 아닌 반환 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>  CSize::operator + =  
 이 크기를 추가 `CSize`합니다.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>  CSize::operator =  
 이 크기를 뺍니다 `CSize`합니다.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>  CSize::operator +  
 이러한 연산자는이 추가 `CSize` 매개 변수의 값입니다.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>설명  
 개별 연산자의 다음 설명을 참조 하세요.  
  
- **operator + (** `size` **)** 이 작업은 두 개의 추가 `CSize` 값입니다.  
  
- **연산자 + (** `point` **)** 오프셋 (이동)을이 작업을 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) (또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) 값이 `CSize` 값입니다. **cx** 및 **cy** 이 멤버인 `CSize` 값에 추가 됩니다는 **x** 및 **y** 의 데이터 멤버는 **지점**  값입니다. 버전의 유사 [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) 를 사용 하는 한 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 매개 변수입니다.  
  
- **연산자 + (** `lpRect` **)** 오프셋 (이동)을이 작업을 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (또는 [CRect](../../atl-mfc-shared/reference/crect-class.md)) 값이 `CSize` 값입니다. **cx** 및 **cy** 이 멤버 `CSize` 값에 추가 되는 **왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽** 데이터 멤버는 `RECT` 값입니다. 버전의 유사 [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) 를 사용 하는 한 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 매개 변수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>  CSize::operator-  
 이러한 연산자의 처음 3 개를 뺄이 `CSize` 매개 변수의 값입니다.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>설명  
 부호를 변경 하는 단항 빼기, 네 번째 연산자는 `CSize` 값입니다. 개별 연산자의 다음 설명을 참조 하세요.  
  
- **연산자-(** `size` **)** 이 작업을 뺍니다 두 `CSize` 값입니다.  
  
- **연산자-(** `point` **)** 오프셋 (이동)을이 작업을 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 또는 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 값이 덧셈 역 원을 `CSize` 값입니다. **cx** 및 **cy** 이 `CSize` 값에서 뺀 합니다 **x** 및 **y** 의 데이터 멤버는 **지점**  값입니다. 버전의 유사 [CPoint::operator-](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) 를 사용 하는 한 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 매개 변수입니다.  
  
- **연산자-(** `lpRect` **)** 오프셋 (이동)을이 작업을 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 값이 덧셈 역으로 `CSize` 값입니다. **cx** 및 **cy** 이 멤버인 `CSize` 값에서 뺀 합니다 **왼쪽**, **위쪽**, **오른쪽**, 및 **아래쪽** 의 데이터 멤버는 `RECT` 값입니다. 버전의 유사 [CRect::operator-](../../atl-mfc-shared/reference/crect-class.md#operator_-) 를 사용 하는 한 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 매개 변수입니다.  
  
- **연산자-()** 이 작업의 덧셈 역 원을 반환 `CSize` 값입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDI](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRect 클래스](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint 클래스](../../atl-mfc-shared/reference/cpoint-class.md)

