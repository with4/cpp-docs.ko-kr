---
title: CD2DRectF 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec43e6bb14b9c5629bde60faec80d9e31e2e5188
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cd2drectf-class"></a>CD2DRectF 클래스
`D2D1_RECT_F`의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|오버로드됨. 생성 된 `CD2DRectF` 에서 개체 `D2D1_RECT_F` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|반환 된 `boolean` 유효 하지 않은 데이터 식에 포함 되어 있는지 여부를 나타내는 값 ( `null`).|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|변환 `CD2DRectF` 를 `CRect` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>  CD2DRectF::CD2DRectF  
 CD2DRectF CRect 개체에서 개체를 만듭니다.  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형  
  
 `fLeft`  
 소스 왼쪽된 좌표  
  
 `fTop`  
 소스 위쪽 좌표  
  
 `fRight`  
 원본 오른쪽 좌표  
  
 `fBottom`  
 소스 아래쪽 좌표입니다.  
  
##  <a name="isnull"></a>  CD2DRectF::IsNull  
 식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0; 그렇지 않으면 FALSE입니다.  
  
##  <a name="operator_crect"></a>  CD2DRectF::operator CRect  
 CD2DRectF CRect 개체로 변환합니다.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 사각형의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
