---
title: "CD2DSolidColorBrush 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSolidColorBrush
- afxrendertarget/CD2DSolidColorBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DSolidColorBrush class
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
caps.latest.revision: 16
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
ms.openlocfilehash: 5b6cbd6a6a5557f5ea23c0556a4b87011b510411
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush 클래스
ID2D1SolidColorBrush에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|오버로드됨. CD2DSolidColorBrush 개체를 만듭니다.|  
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|소멸자입니다. D2D 단색 브러시 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSolidColorBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|  
|[CD2DSolidColorBrush::Create](#create)|CD2DSolidColorBrush를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DSolidColorBrush::Destroy](#destroy)|CD2DSolidColorBrush 개체를 소멸 시킵니다. (재정의 [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DSolidColorBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DSolidColorBrush::Get](#get)|반환 ID2D1SolidColorBrush 인터페이스|  
|[CD2DSolidColorBrush::GetColor](#getcolor)|단색 브러시의 색을 검색|  
|[CD2DSolidColorBrush::SetColor](#setcolor)|이 단색 브러시의 색을 지정합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|반환 ID2D1SolidColorBrush 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|단색 브러시입니다.|  
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush 개체에 대 한 포인터를 저장합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2DSolidColorBrush:: ~ CD2DSolidColorBrush  
 소멸자입니다. D2D 단색 브러시 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DSolidColorBrush();
```  
  
##  <a name="a-nameattacha--cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2DSolidColorBrush::Attach  
 기존 개체에 대 한 리소스 인터페이스를 연결.  
  
```  
void Attach(ID2D1SolidColorBrush* pResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pResource`  
 기존 리소스 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="a-namecd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2DSolidColorBrush::CD2DSolidColorBrush  
 CD2DSolidColorBrush 개체를 만듭니다.  
  
```  
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    D2D1_COLOR_F color,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    COLORREF color,  
    int nAlpha = 255,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
 `color`  
 브러시의 색의 빨강, 녹색, 파란색 및 알파 값입니다.  
  
 `pBrushProperties`  
 불투명도 및 브러시의 변환에 대 한 포인터입니다.  
  
 `bAutoDestroy`  
 개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.  
  
 `nAlpha`  
 브러시의 색의 불투명도입니다.  
  
##  <a name="a-namecreatea--cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2DSolidColorBrush::Create  
 CD2DSolidColorBrush를 만듭니다.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="a-namedestroya--cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2DSolidColorBrush::Destroy  
 CD2DSolidColorBrush 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2DSolidColorBrush::Detach  
 개체에서 리소스 인터페이스를 분리합니다.  
  
```  
ID2D1SolidColorBrush* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 리소스 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namegeta--cd2dsolidcolorbrushget"></a><a name="get"></a>CD2DSolidColorBrush::Get  
 반환 ID2D1SolidColorBrush 인터페이스  
  
```  
ID2D1SolidColorBrush* Get();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1SolidColorBrush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namegetcolora--cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2DSolidColorBrush::GetColor  
 단색 브러시의 색을 검색  
  
```  
D2D1_COLOR_F GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 단색 브러시의 색  
  
##  <a name="a-namemcolorsolida--cd2dsolidcolorbrushmcolorsolid"></a><a name="m_colorsolid"></a>CD2DSolidColorBrush::m_colorSolid  
 단색 브러시입니다.  
  
```  
D2D1_COLOR_F m_colorSolid;  
```  
  
##  <a name="a-namempsolidcolorbrusha--cd2dsolidcolorbrushmpsolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2DSolidColorBrush::m_pSolidColorBrush  
 ID2D1SolidColorBrush 개체에 대 한 포인터를 저장합니다.  
  
```  
ID2D1SolidColorBrush* m_pSolidColorBrush;  
```  
  
##  <a name="a-nameoperatorid2d1solidcolorbrushstara--cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2DSolidColorBrush::operator ID2D1SolidColorBrush *  
 반환 ID2D1SolidColorBrush 인터페이스  
  
```  
operator ID2D1SolidColorBrush*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1SolidColorBrush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namesetcolora--cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2DSolidColorBrush::SetColor  
 이 단색 브러시의 색을 지정합니다.  
  
```  
void SetColor(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 이 단색 브러시의 색  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

