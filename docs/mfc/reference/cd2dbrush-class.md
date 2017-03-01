---
title: "CD2DBrush 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrush
- afxrendertarget/CD2DBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
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
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>CD2DBrush 클래스
ID2D1Brush에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|CD2DBrush 개체를 만듭니다.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|소멸자입니다. D2D 브러시 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|  
|[CD2DBrush::Destroy](#destroy)|CD2DBrush 개체를 소멸 시킵니다. (재정의 [CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DBrush::Get](#get)|반환 ID2D1Brush 인터페이스|  
|[CD2DBrush::GetOpacity](#getopacity)|이 브러시의 불투명도 수준을 가져옵니다.|  
|[CD2DBrush::GetTransform](#gettransform)|렌더링 대상의 현재 변환을 가져옵니다.|  
|[CD2DBrush::IsValid](#isvalid)|리소스 유효성 검사 (재정의 [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|이 브러시의 불투명도 수준을 설정합니다.|  
|[CD2DBrush::SetTransform](#settransform)|기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|반환 ID2D1Brush 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|ID2D1Brush 개체에 대 한 포인터를 저장합니다.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|브러시 속성입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dbrusha--cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a>CD2DBrush:: ~ CD2DBrush  
 소멸자입니다. D2D 브러시 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="a-nameattacha--cd2dbrushattach"></a><a name="attach"></a>CD2DBrush::Attach  
 기존 개체에 대 한 리소스 인터페이스를 연결.  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pResource`  
 기존 리소스 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="a-namecd2dbrusha--cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 CD2DBrush 개체를 만듭니다.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
 `pBrushProperties`  
 불투명도 및 브러시의 변환에 대 한 포인터입니다.  
  
 `bAutoDestroy`  
 개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.  
  
##  <a name="a-namedestroya--cd2dbrushdestroy"></a><a name="destroy"></a>CD2DBrush::Destroy  
 CD2DBrush 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dbrushdetach"></a><a name="detach"></a>CD2DBrush::Detach  
 개체에서 리소스 인터페이스를 분리합니다.  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 리소스 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namegeta--cd2dbrushget"></a><a name="get"></a>CD2DBrush::Get  
 반환 ID2D1Brush 인터페이스  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1Brush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namegetopacitya--cd2dbrushgetopacity"></a><a name="getopacity"></a>CD2DBrush::GetOpacity  
 이 브러시의 불투명도 수준을 가져옵니다.  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0에서 브러시의 불투명도 나타내는 1 사이의 값입니다. 이 값은 선형으로 브러시에 의해 채워진 모든 픽셀의 알파 값을 조정 하는 상수 승수입니다. 불투명도 값은 고정 됩니다. 0에서 1 사이의 서로 곱하기 전에  
  
##  <a name="a-namegettransforma--cd2dbrushgettransform"></a><a name="gettransform"></a>CD2DBrush::GetTransform  
 렌더링 대상의 현재 변환을 가져옵니다.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `transform`  
 를 반환 하는 경우에 렌더링 대상의 현재 변환을 포함 되어 있습니다. 이 매개 변수는 초기화 되지 않은 상태로 전달 됩니다.  
  
##  <a name="a-nameisvalida--cd2dbrushisvalid"></a><a name="isvalid"></a>CD2DBrush::IsValid  
 리소스 유효성 검사  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 리소스는 올바르지 않습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="a-namempbrusha--cd2dbrushmpbrush"></a><a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 ID2D1Brush 개체에 대 한 포인터를 저장합니다.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="a-namempbrushpropertiesa--cd2dbrushmpbrushproperties"></a><a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 브러시 속성입니다.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="a-nameoperatorid2d1brushstara--cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a>CD2DBrush::operator ID2D1Brush *  
 반환 ID2D1Brush 인터페이스  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1Brush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="a-namesetopacitya--cd2dbrushsetopacity"></a><a name="setopacity"></a>CD2DBrush::SetOpacity  
 이 브러시의 불투명도 수준을 설정합니다.  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>매개 변수  
 `opacity`  
 0에서 브러시의 불투명도 나타내는 1 사이의 값입니다. 이 값은 선형으로 브러시에 의해 채워진 모든 픽셀의 알파 값을 조정 하는 상수 승수입니다. 불투명도 값은 고정 됩니다. 0에서 1 사이의 서로 곱하기 전에  
  
##  <a name="a-namesettransforma--cd2dbrushsettransform"></a><a name="settransform"></a>CD2DBrush::SetTransform  
 기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>매개 변수  
 `transform`  
 렌더링 대상에 적용할 변환  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

