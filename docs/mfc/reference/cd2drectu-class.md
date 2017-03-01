---
title: "CD2DRectU 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- afxrendertarget/CD2DRectU
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU class
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
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
ms.openlocfilehash: 74c05d7f4be9b9308cdcb2b91a0455a4cd025dc1
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectu-class"></a>CD2DRectU 클래스
`D2D1_RECT_U`의 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|오버로드됨. 생성 된 `CD2DRectU` 에서 개체 `D2D1_RECT_U` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectU::IsNull](#isnull)|반환 된 `boolean` 유효 하지 않은 데이터 식에 포함 되어 있는지 여부를 나타내는 값 ( `null`).|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|변환 `CD2DRectU` 를 `CRect` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="a-namecd2drectua--cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
 CRect 개체에서 CD2DRectU 개체를 만듭니다.  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 소스 사각형  
  
 `uLeft`  
 원본 왼쪽된 좌표  
  
 `uTop`  
 원본 위쪽 좌표  
  
 `uRight`  
 원본 오른쪽 좌표  
  
 `uBottom`  
 원본 아래쪽 좌표  
  
##  <a name="a-nameisnulla--cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull  
 식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값은 모두 0입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="a-nameoperatorcrecta--cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::operator CRect  
 CD2DRectU CRect 개체로 변환합니다.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 사각형의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

