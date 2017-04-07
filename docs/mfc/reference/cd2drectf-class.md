---
title: "CD2DRectF 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF class
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5bca2dcce32679083e5917d855f711984989a489
ms.lasthandoff: 02/24/2017

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
  
##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
 CRect 개체에서 CD2DRectF 개체를 만듭니다.  
  
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
 원본 왼쪽된 좌표  
  
 `fTop`  
 원본 위쪽 좌표  
  
 `fRight`  
 원본 오른쪽 좌표  
  
 `fBottom`  
 원본 아래쪽 좌표  
  
##  <a name="isnull"></a>CD2DRectF::IsNull  
 식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="operator_crect"></a>CD2DRectF::operator CRect  
 CD2DRectF CRect 개체로 변환합니다.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 사각형의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

