---
title: CD2DRectU 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e054c23d2137f5802c17731fac86dd64080389e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336476"
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
|[CD2DRectU::IsNull](#isnull)|반환 된 **부울** 식에 유효 하지 않은 데이터 (NULL)이 포함 되어 있는지 여부를 나타내는 값입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|변환 `CD2DRectU` 에 `CRect` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="cd2drectu"></a>  CD2DRectU::CD2DRectU  
 CRect 개체에서 CD2DRectU 개체를 생성합니다.  
  
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
 *rect*  
 소스 사각형  
  
 *uLeft*  
 원본 왼쪽된 좌표  
  
 *uTop*  
 원본 위쪽 좌표  
  
 *uRight*  
 원본 오른쪽 좌표  
  
 *uBottom*  
 원본 아래쪽 좌표입니다.  
  
##  <a name="isnull"></a>  CD2DRectU::IsNull  
 식에 유효 하지 않은 데이터 (Null)이 포함 되어 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사각형의 위쪽, 왼쪽, 아래쪽 및 오른쪽 값을 0으로 모두 같을 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="operator_crect"></a>  CD2DRectU::operator CRect  
 CD2DRectU CRect 개체로 변환합니다.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>반환 값  
 D2D 사각형의 현재 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
