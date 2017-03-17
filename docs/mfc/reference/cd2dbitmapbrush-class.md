---
title: "CD2DBitmapBrush 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush class
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
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
ms.openlocfilehash: a9ab15dcae8715b98cc9f723a710b64e83649bf9
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush 클래스
ID2D1BitmapBrush에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|오버로드됨. 파일에서 CD2DBitmapBrush 개체를 만듭니다.|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|소멸자입니다. D2D 비트맵 브러시 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|기존 개체에 대 한 리소스 인터페이스를 연결.|  
|[CD2DBitmapBrush::Create](#create)|CD2DBitmapBrush를 만듭니다. (재정의 [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::Destroy](#destroy)|CD2DBitmapBrush 개체를 소멸 시킵니다. (재정의 [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::Detach](#detach)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DBitmapBrush::Get](#get)|반환 ID2D1BitmapBrush 인터페이스|  
|[CD2DBitmapBrush::GetBitmap](#getbitmap)|이 브러시를 그릴 때 사용 하는 비트맵의 소스를 가져옵니다.|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|브러시가 비트맵을 지 나 확장 되는 영역 가로 바둑판식는 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|브러시가 비트맵을 지 나 확장 되는 영역 세로 바둑판식는 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 메서드를 가져옵니다.|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|이 브러시를 그릴 때 사용 하는 비트맵의 소스를 지정 합니다.|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|브러시가 비트맵을 지 나 확장 되는 영역을 수평으로 바둑판식으로 표시 되는 방법을 지정 합니다.|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방법을 지정 합니다.|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 모드를 지정 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|개체를 초기화합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|반환 ID2D1BitmapBrush 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|CD2DBitmap 개체에 대 한 포인터를 저장합니다.|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush 개체에 대 한 포인터를 저장합니다.|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|브러시 속성은 비트맵입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 소멸자입니다. D2D 비트맵 브러시 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>CD2DBitmapBrush::Attach  
 기존 개체에 대 한 리소스 인터페이스를 연결.  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pResource`  
 기존 리소스 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
 CD2DBitmapBrush 개체를 만듭니다.  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
 `pBitmapBrushProperties`  
 확장 모드 및 비트맵 브러시의 보간 모드에 대 한 포인터입니다.  
  
 `pBrushProperties`  
 불투명도 및 브러시의 변환에 대 한 포인터입니다.  
  
 `bAutoDestroy`  
 개체 소유자 (pParentTarget)에 의해 소멸 되는 것을 나타냅니다.  
  
 `uiResID`  
 리소스의 리소스 ID.  
  
 `lpszType`  
 리소스 종류를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `sizeDest`  
 비트맵의 대상 크기입니다.  
  
 `lpszImagePath`  
 파일의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
##  <a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 개체를 초기화합니다.  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBitmapBrushProperties`  
 비트맵 브러시 속성에 대 한 포인터입니다.  
  
##  <a name="create"></a>CD2DBitmapBrush::Create  
 CD2DBitmapBrush를 만듭니다.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 렌더링 대상에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="destroy"></a>CD2DBitmapBrush::Destroy  
 CD2DBitmapBrush 개체를 소멸 시킵니다.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmapBrush::Detach  
 개체에서 리소스 인터페이스를 분리합니다.  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리 된 리소스 인터페이스에 대 한 포인터입니다.  
  
##  <a name="get"></a>CD2DBitmapBrush::Get  
 반환 ID2D1BitmapBrush 인터페이스  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1BitmapBrush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="getbitmap"></a>CD2DBitmapBrush::GetBitmap  
 이 브러시를 그릴 때 사용 하는 비트맵의 소스를 가져옵니다.  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>반환 값  
 CD2DBitmap 개체 또는 개체가 아직 초기화 되지 않은 경우에 NULL에 대 한 포인터입니다.  
  
##  <a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 브러시가 비트맵을 지 나 확장 되는 영역 가로 바둑판식는 메서드를 가져옵니다.  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>반환 값  
 브러시가 비트맵을 지 나 확장 되는 영역을 수평으로 바둑판식으로 표시 되는 방법을 지정 하는 값  
  
##  <a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 브러시가 비트맵을 지 나 확장 되는 영역 세로 바둑판식는 메서드를 가져옵니다.  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>반환 값  
 브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방법을 지정 하는 값  
  
##  <a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 메서드를 가져옵니다.  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 메서드  
  
##  <a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 CD2DBitmap 개체에 대 한 포인터를 저장합니다.  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 ID2D1BitmapBrush 개체에 대 한 포인터를 저장합니다.  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 브러시 속성은 비트맵입니다.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::operator ID2D1BitmapBrush *  
 반환 ID2D1BitmapBrush 인터페이스  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1BitmapBrush 인터페이스에 대 한 포인터입니다.  
  
##  <a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 이 브러시를 그릴 때 사용 하는 비트맵의 소스를 지정 합니다.  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBitmap`  
 브러시에 사용 되는 비트맵 소스  
  
##  <a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 브러시가 비트맵을 지 나 확장 되는 영역을 수평으로 바둑판식으로 표시 되는 방법을 지정 합니다.  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>매개 변수  
 `extendModeX`  
 브러시가 비트맵을 지 나 확장 되는 영역을 수평으로 바둑판식으로 표시 되는 방법을 지정 하는 값  
  
##  <a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방법을 지정 합니다.  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>매개 변수  
 `extendModeY`  
 브러시가 비트맵을 지 나 확장 되는 영역을 세로로으로 바둑판식으로 표시 되는 방법을 지정 하는 값  
  
##  <a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 모드를 지정 합니다.  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `interpolationMode`  
 브러시 비트맵을 크기 조정 또는 회전 때 사용 되는 보간 모드  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

