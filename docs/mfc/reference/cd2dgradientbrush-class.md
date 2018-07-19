---
title: CD2DGradientBrush 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
dev_langs:
- C++
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e479c156967addc7add8f048d2ef1c3abab0dd8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956235"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush 클래스
CD2DLinearGradientBrush 및 CD2DRadialGradientBrush 클래스의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|CD2DGradientBrush 개체를 만듭니다.|  
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|소멸자입니다. D2D 그라데이션 브러시 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DGradientBrush::Destroy](#destroy)|CD2DGradientBrush 개체를 소멸 시킵니다. (재정의 [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 구조체의 배열입니다.|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|어떤 색 그라데이션 중지점 사이의 보간을 수행 되는 공간입니다.|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|[0, 1]의 표준화 된 범위를 벗어난 그라데이션의 동작입니다.|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP 구조의 배열에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgradientbrush"></a>  CD2DGradientBrush:: ~ CD2DGradientBrush  
 소멸자입니다. D2D 그라데이션 브러시 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="cd2dgradientbrush"></a>  CD2DGradientBrush::CD2DGradientBrush  
 CD2DGradientBrush 개체를 만듭니다.  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentTarget*  
 렌더링 대상에 대 한 포인터입니다.  
  
 *gradientStops*  
 D2D1_GRADIENT_STOP 구조의 배열에 대 한 포인터입니다.  
  
 *gradientStopsCount*  
 GradientStops 배열에서 그라데이션 중지점의 수를 지정 하는 1 보다 크거나 같은 값입니다.  
  
 *colorInterpolationGamma*  
 어떤 색 그라데이션 중지점 사이의 보간을 수행 되는 공간입니다.  
  
 *extendMode*  
 [0, 1]의 표준화 된 범위를 벗어난 그라데이션의 동작입니다.  
  
 *pBrushProperties*  
 불투명도 및 브러시의 변환에 대 한 포인터입니다.  
  
 *bAutoDestroy*  
 개체를 소유자 (pParentTarget)에 의해 폐기 수를 나타냅니다.  
  
##  <a name="destroy"></a>  CD2DGradientBrush::Destroy  
 CD2DGradientBrush 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy();
```  
  
##  <a name="m_argradientstops"></a>  CD2DGradientBrush::m_arGradientStops  
 D2D1_GRADIENT_STOP 구조체의 배열입니다.  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="m_colorinterpolationgamma"></a>  CD2DGradientBrush::m_colorInterpolationGamma  
 어떤 색 그라데이션 중지점 사이의 보간을 수행 되는 공간입니다.  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="m_extendmode"></a>  CD2DGradientBrush::m_extendMode  
 [0, 1]의 표준화 된 범위를 벗어난 그라데이션의 동작입니다.  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="m_pgradientstops"></a>  CD2DGradientBrush::m_pGradientStops  
 D2D1_GRADIENT_STOP 구조의 배열에 대 한 포인터입니다.  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)
