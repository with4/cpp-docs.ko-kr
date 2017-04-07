---
title: "CRenderTarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget class
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
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
ms.openlocfilehash: 6f77d482e7ee3bf0798ad488067893b3712aac62
ms.lasthandoff: 02/24/2017

---
# <a name="crendertarget-class"></a>CRenderTarget 클래스
ID2D1RenderTarget에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|CRenderTarget 개체를 만듭니다.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|소멸자입니다. 렌더링 대상 개체가 소멸 될 때 호출 됩니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|기존 연결 개체를 대상 인터페이스를 렌더링 합니다.|  
|[CRenderTarget::BeginDraw](#begindraw)|이 렌더링 대상에 그리기를 시작 합니다.|  
|[CRenderTarget::Clear](#clear)|지정 된 색을 그리기 영역을 지웁니다.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|GDI 색상 및 알파 값 D2D1_COLOR_F 개체로 변환합니다.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|현재 렌더링 대상과 호환 되는 중간 오프 스크린 그리기 하는 동안 사용 하기 위해 새 비트맵 렌더링 대상을 만듭니다.|  
|[CRenderTarget::Destroy](#destroy)|하나 이상의 리소스를 삭제합니다.|  
|[CRenderTarget::Detach](#detach)|렌더링 대상 인터페이스 개체에서 분리|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|지정된 된 IDWriteTextLayout 개체에서 설명 된 서식 있는 텍스트를 그립니다.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|지정된 된 스트로크 스타일을 사용 하 여 지정된 된 타원의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|지정된 된 스트로크 스타일을 사용 하 여 지정 된 기 하 도형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|지정 된 문자 모양을 그립니다.|  
|[CRenderTarget::DrawLine](#drawline)|지정된 된 스트로크 스타일을 사용 하 여 지정 된 점 사이의 선을 그립니다.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|지정 된 크기 및 선 스타일 들어 있는 사각형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|지정된 된 스트로크 스타일을 사용 하 여 지정된 된 모퉁이가 둥근된 사각형의 윤곽선을 그립니다.|  
|[CRenderTarget::DrawText](#drawtext)|IDWriteTextFormat 개체에서 제공 하는 형식 정보를 사용 하 여 지정된 된 텍스트를 그립니다.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|지정된 된 IDWriteTextLayout 개체에서 설명 된 서식 있는 텍스트를 그립니다.|  
|[CRenderTarget::EndDraw](#enddraw)|렌더링 대상에 대 한 그리기 작업을 종료 하 고 현재 오류 상태와 연결 된 태그를 나타냅니다.|  
|[CRenderTarget::FillEllipse](#fillellipse)|지정된 된 타원의 내부를 그립니다.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|지정 된 기 하 도형의 내부를 그립니다.|  
|[CRenderTarget::FillMesh](#fillmesh)|지정된 된 메시의 내부를 그립니다.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|브러시에 지정한 비트맵에서 설명 된 불투명 마스크를 적용 하 고 렌더링 대상의 영역을 그리는 해당 브러시를 사용 하 여 키를 누릅니다.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|지정된 된 사각형의 내부를 그립니다.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|지정된 된 모퉁이가 둥근된 사각형의 내부를 그립니다.|  
|[CRenderTarget::Flush](#flush)|모든 보류 중인 그리기 명령을 실행합니다.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|텍스트가 아닌 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드를 검색합니다.|  
|[CRenderTarget::GetDpi](#getdpi)|렌더링 대상의 dpi (인치당 도트)을 반환|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|렌더링 대상에서 지 원하는 한 비트맵 차원의의 장치 독립적 단위 (픽셀)의 최대 크기를 가져옵니다.|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|렌더링 대상의 픽셀 형식 및 알파 모드를 검색합니다.|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|(장치 픽셀)에서 렌더링 대상의 크기를 반환합니다.|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|반환 ID2D1RenderTarget 인터페이스|  
|[CRenderTarget::GetSize](#getsize)|장치 독립적 픽셀의 렌더링 대상의 크기를 반환합니다.|  
|[CRenderTarget::GetTags](#gettags)|이후 그리기 작업에 대 한 레이블을 가져옵니다.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|텍스트 및 문자 모양 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드를 가져옵니다.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|렌더링 대상의 현재 텍스트 렌더링 옵션을 검색합니다.|  
|[CRenderTarget::GetTransform](#gettransform)|기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생 합니다.|  
|[CRenderTarget::IsSupported](#issupported)|렌더링 대상에서 지정된 된 속성을 지원 하는지 여부를 나타냅니다.|  
|[CRenderTarget::IsValid](#isvalid)|리소스 유효성 검사|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다. 이 메서드를 호출한 후에 있는 클립은 더 이상 다음 그리기 작업에 적용 됩니다.|  
|[CRenderTarget::PopLayer](#poplayer)|그리기 작업을 마지막 PushLayer로 지정 된 계층으로 리디렉션하는를 호출 합니다.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다. 이 메서드를 호출한 후에 있는 클립은 더 이상 다음 그리기 작업에 적용 됩니다.|  
|[CRenderTarget::PushLayer](#pushlayer)|PopLayer를 호출할 때까지 이후의 모든 그리기 작업을 받을 수 있도록 렌더링 대상에 지정 된 계층을 추가 합니다.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|지정 된 ID2D1DrawingStateBlock의 렌더링 대상의 그리기 상태를 설정합니다.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|지정 된 ID2D1DrawingStateBlock에 현재 그리기 상태를 저장합니다.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|렌더링 대상의 앨리어싱 사용 안 함 모드를 설정합니다. 앤티 앨리어싱 모드 이후의 모든 그리기 작업, 텍스트 및 문자 모양 그리기 작업 제외에 적용 됩니다.|  
|[CRenderTarget::SetDpi](#setdpi)|렌더링 대상의 (DPI) 인치당 도트를 설정합니다.|  
|[CRenderTarget::SetTags](#settags)|이후 그리기 작업에 대 한 레이블을 지정합니다.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|이후 텍스트 및 문자 모양 그리기 작업을 사용 하는 앨리어싱 사용 안 함 모드를 지정 합니다.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|모든 후속 텍스트와 문자 모양 그리기 작업에 적용할 텍스트 렌더링 옵션을 지정 합니다.|  
|[CRenderTarget::SetTransform](#settransform)|오버로드됨. 기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|CD2DResource 개체 validity; 확인 아직 하지 않은 경우 해당 개체를 만듭니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|반환 ID2D1RenderTarget 인터페이스|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|목록 CD2DResource 개체에 대 한 포인터입니다.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|ID2D1RenderTarget 개체에 대 한 포인터입니다.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|기본 텍스트 서식을 포함 하는 CD2DTextFormat 개체에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>CRenderTarget:: ~ CRenderTarget  
 소멸자입니다. 렌더링 대상 개체가 소멸 될 때 호출 됩니다.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>CRenderTarget::Attach  
 기존 연결 개체를 대상 인터페이스를 렌더링 합니다.  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pRenderTarget`  
 기존 렌더링 대상 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="begindraw"></a>CRenderTarget::BeginDraw  
 이 렌더링 대상에 그리기를 시작 합니다.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>CRenderTarget::Clear  
 지정 된 색을 그리기 영역을 지웁니다.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 그리기 영역 지워져 색입니다.  
  
##  <a name="colorref_to_d2dcolor"></a>CRenderTarget::COLORREF_TO_D2DCOLOR  
 GDI 색상 및 알파 값 D2D1_COLOR_F 개체로 변환합니다.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 RGB 값입니다.  
  
 `nAlpha`  
  
### <a name="return-value"></a>반환 값  
 D2D1_COLOR_F 값입니다.  
  
##  <a name="createcompatiblerendertarget"></a>CRenderTarget::CreateCompatibleRenderTarget  
 현재 렌더링 대상과 호환 되는 중간 오프 스크린 그리기 하는 동안 사용 하기 위해 새 비트맵 렌더링 대상을 만듭니다.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bitmapTarget`  
 이 메서드가 반환 될 때 새 비트맵 렌더링 대상에 대 한 포인터의 주소를 포함 합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.  
  
 `sizeDesired`  
 원하는 크기의 장치 독립적 픽셀 원래 달라 야 하는 경우 새 렌더링 대상의 렌더링 대상 또는 NULL입니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 `sizePixelDesired`  
 원하는 크기 (픽셀 단위)는 원래 달라 야 하는 경우 새 렌더링 대상의 렌더링 대상 또는 NULL입니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
 `desiredFormat`  
 원하는 픽셀 형식 및 새 알파 모드 렌더링 대상과, 또는 NULL입니다. 픽셀 형식은 DXGI_FORMAT_UNKNOWN로 설정 된 경우 또는이 매개 변수가 null 이면 원래 렌더링 대상으로 새 렌더링 대상 같은 픽셀 형식을 사용 합니다. 이 매개 변수는 NULL 또는 알파 모드가 D2D1_ALPHA_MODE_UNKNOWN 경우 새 렌더링 대상의 알파 모드 D2D1_ALPHA_MODE_PREMULTIPLIED를 기본값으로 합니다. 지원 되는 픽셀 형식에 대 한 내용은 지원 되는 픽셀 형식 및 Alpha 모드를 참조 하십시오.  
  
 `options`  
 새로운 렌더링 대상이 있는지 여부를 지정 하는 값은 GDI와 호환 되어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.  
  
##  <a name="crendertarget"></a>CRenderTarget::CRenderTarget  
 CRenderTarget 개체를 만듭니다.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>CRenderTarget::Destroy  
 하나 이상의 리소스를 삭제합니다.  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDeleteResources`  
 BDeleteResources 결과가 TRUE 이면 m_lstResources에 있는 모든 리소스는 자동으로 소멸 됩니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환  
  
##  <a name="detach"></a>CRenderTarget::Detach  
 렌더링 대상 인터페이스 개체에서 분리  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>반환 값  
 분리에 대 한 포인터는 대상 인터페이스를 렌더링 합니다.  
  
##  <a name="drawbitmap"></a>CRenderTarget::DrawBitmap  
 지정된 된 IDWriteTextLayout 개체에서 설명 된 서식 있는 텍스트를 그립니다.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBitmap`  
 렌더링 하는 비트맵입니다.  
  
 `rectDest`  
 장치 독립적 픽셀 비트맵을 그리면 영역의 렌더링 대상의 좌표 공간에서의 위치와 크기입니다. 사각형 잘 정렬 되지 않은 경우 아무 것도 그려지지, 있지만 렌더링 대상의 오류 상태에 들어가지 않습니다.  
  
 `fOpacity`  
 비트맵;에 적용할 불투명도 값을 지정 하는 0.0 f 사이의 1.0 f 까지의 값 비트맵의 내용 알파 값에 대해이 값을 곱합니다.  
  
 `interpolationMode`  
 비트맵을 크기 조정 또는 회전 그리기 작업 하는 경우를 사용 하는 보간 모드입니다.  
  
 `pRectSrc`  
 크기와 위치를 그릴 비트맵 내에서 영역의 비트맵의 좌표 공간에서 장치 독립적 픽셀 단위로 합니다.  
  
##  <a name="drawellipse"></a>CRenderTarget::DrawEllipse  
 지정된 된 스트로크 스타일을 사용 하 여 지정된 된 타원의 윤곽선을 그립니다.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `ellipse`  
 위치 및 장치 독립적 픽셀에 그릴 타원의 반지름입니다.  
  
 `pBrush`  
 타원의 개요를 그리는 데 사용 되는 브러시입니다.  
  
 `fStrokeWidth`  
 타원의 선 두께입니다. 스트로크는 타원의 개요에 가운데 표시 됩니다.  
  
 `strokeStyle`  
 타원의 윤곽선 또는 단색 스트로크를 그리는 데 NULL에 적용할 선의 스타일입니다.  
  
##  <a name="drawgeometry"></a>CRenderTarget::DrawGeometry  
 지정된 된 스트로크 스타일을 사용 하 여 지정 된 기 하 도형의 윤곽선을 그립니다.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pGeometry`  
 그릴 기하학입니다.  
  
 `pBrush`  
 기 하 도형의 스트로크를 그리는 데 사용 되는 브러시입니다.  
  
 `fStrokeWidth`  
 기 하 도형의 스트로크 두께입니다. 스트로크에 기 하 도형의 윤곽선 가운데 표시 됩니다.  
  
 `strokeStyle`  
 기 하 도형의 윤곽선 또는 단색 스트로크를 그리는 데 NULL에 적용할 선의 스타일입니다.  
  
##  <a name="drawglyphrun"></a>CRenderTarget::DrawGlyphRun  
 지정 된 문자 모양을 그립니다.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptBaseLineOrigin`  
 장치 독립적 픽셀 문자 모양 기준의 원본입니다.  
  
 `glyphRun`  
 렌더링 하는 문자 모양입니다.  
  
 `pForegroundBrush`  
 지정 된 문자 모양을 그리는 데 사용 되는 브러시입니다.  
  
 `measuringMode`  
 서식을 지정할 때 텍스트를 측정 하 문자 모양 메트릭을 사용 하는 방법을 나타내는 값입니다. 기본값은 DWRITE_MEASURING_MODE_NATURAL 합니다.  
  
##  <a name="drawline"></a>CRenderTarget::DrawLine  
 지정된 된 스트로크 스타일을 사용 하 여 지정 된 점 사이의 선을 그립니다.  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptFrom`  
 장치 독립적 픽셀에서 줄의 시작 지점입니다.  
  
 `ptTo`  
 장치 독립적 픽셀에서 선의 끝점입니다.  
  
 `pBrush`  
 선의 스트로크를 그리는 데 사용 되는 브러시입니다.  
  
 `fStrokeWidth`  
 선의 두께 지정 하는 0.0 f 보다 크거나 같은 값입니다. 이 매개 변수를 지정 하지 않으면 기본값으로 사용 1.0 f로 설정 됩니다. 스트로크는 선 가운데에 있습니다.  
  
 `strokeStyle`  
 그림판 또는 NULL 실선 그릴 선의 스타일입니다.  
  
##  <a name="drawrectangle"></a>CRenderTarget::DrawRectangle  
 지정 된 크기 및 선 스타일 들어 있는 사각형의 윤곽선을 그립니다.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 장치 독립적 픽셀에 그릴 사각형의 크기  
  
 `pBrush`  
 사각형의 스트로크를 그리는 데 사용 되는 브러시  
  
 `fStrokeWidth`  
 사각형의 스트로크 너비를 지정 하는 0.0 f 보다 크거나 같은 값입니다. 스트로크는 사각형의 개요에 가운데 표시 됩니다.  
  
 `strokeStyle`  
 그림판 또는 NULL 단색 스트로크를 그리는 선의 스타일입니다.  
  
##  <a name="drawroundedrectangle"></a>CRenderTarget::DrawRoundedRectangle  
 지정된 된 스트로크 스타일을 사용 하 여 지정된 된 모퉁이가 둥근된 사각형의 윤곽선을 그립니다.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `rectRounded`  
 장치 독립적 픽셀에 그릴 모서리가 둥근된 사각형의 크기입니다.  
  
 `pBrush`  
 모퉁이가 둥근된 사각형의 개요를 그리는 데 사용 되는 브러시입니다.  
  
 `fStrokeWidth`  
 모퉁이가 둥근된 사각형의 스트로크 너비입니다. 스트로크는 가운데 모퉁이가 둥근된 사각형의 개요에 표시 됩니다. 기본값은 1.0 f로 설정 합니다.  
  
 `strokeStyle`  
 모퉁이가 둥근된 사각형의 선 또는 단색 스트로크를 그리는 데 NULL의 스타일입니다. 기본값은 NULL입니다.  
  
##  <a name="drawtext"></a>CRenderTarget::DrawText  
 IDWriteTextFormat 개체에서 제공 하는 형식 정보를 사용 하 여 지정된 된 텍스트를 그립니다.  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>매개 변수  
 `strText`  
 그릴 유니코드 문자 배열에 대 한 포인터입니다.  
  
 `rect`  
 텍스트를 그리는 영역의 위치와 크기입니다.  
  
 `pForegroundBrush`  
 텍스트를 그리는 데 사용 되는 브러시입니다.  
  
 `textFormat`  
 서식의 텍스트를 그릴, 글꼴, 글꼴 크기, 방향 등의 세부 사항을 설명 하는 개체입니다.  
  
 `options`  
 픽셀 경계에 텍스트 맞춰야 하는지 여부 및 레이아웃 사각형에 텍스트 잘림을 있는지 여부를 나타내는 값입니다. 기본값은 D2D1_DRAW_TEXT_OPTIONS_NONE 텍스트 픽셀 경계에 맞춰야 하 고 레이아웃 사각형에 잘릴 수를 의미 합니다.  
  
 `measuringMode`  
 서식을 지정할 때 텍스트를 측정 하 문자 모양 메트릭을 사용 하는 방법을 나타내는 값입니다. 기본값은 DWRITE_MEASURING_MODE_NATURAL 합니다.  
  
##  <a name="drawtextlayout"></a>CRenderTarget::DrawTextLayout  
 지정된 된 IDWriteTextLayout 개체에서 설명 된 서식 있는 텍스트를 그립니다.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptOrigin`  
 장치 독립적 픽셀, textLayout으로 설명 하는 텍스트의 왼쪽 위 모퉁이 그릴 있는 점입니다.  
  
 `textLayout`  
 서식이 지정 된 그릴 텍스트입니다. ID2D1Resource에서 상속 하지 않는 모든 그리기 효과 무시 됩니다. 브러시 없는 ID2D1Resource에서 상속 하는 그리기 효과 없으면이 메서드는 실패 하 고 렌더링 대상의 오류 상태에 저장 됩니다.  
  
 `pBrushForeground`  
 그리기 효과 (IDWriteTextLayout::SetDrawingEffect 메서드에 의해 지정 됨)로 연결 된 브러시를 아직 포함 되지 않은 textLayout에 텍스트를 그리는 데 사용 되는 브러시입니다.  
  
 `options`  
 픽셀 경계에 텍스트 맞춰야 하는지 여부 및 레이아웃 사각형에 텍스트 잘림을 있는지 여부를 나타내는 값입니다. 기본값은 D2D1_DRAW_TEXT_OPTIONS_NONE 텍스트 픽셀 경계에 맞춰야 하 고 레이아웃 사각형에 잘릴 수를 의미 합니다.  
  
##  <a name="enddraw"></a>CRenderTarget::EndDraw  
 렌더링 대상에 대 한 그리기 작업을 종료 하 고 현재 오류 상태와 연결 된 태그를 나타냅니다.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK가 반환 됩니다. 그렇지 않으면 HRESULT 오류 코드를 반환합니다.  
  
##  <a name="fillellipse"></a>CRenderTarget::FillEllipse  
 지정된 된 타원의 내부를 그립니다.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `ellipse`  
 위치 및 장치 독립적 픽셀을 그릴 타원의 반지름입니다.  
  
 `pBrush`  
 타원의 내부를 그리는 데 사용 되는 브러시입니다.  
  
##  <a name="fillgeometry"></a>CRenderTarget::FillGeometry  
 지정 된 기 하 도형의 내부를 그립니다.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pGeometry`  
 그리는 데 기하학입니다.  
  
 `pBrush`  
 기 하 도형을 그리는 데 사용 되는 브러시의 내부입니다.  
  
 `pOpacityBrush`  
 불투명 마스크; 기 하 도형에 적용 하려면 불투명도 마스크가 없는 대해 NULL입니다. 불투명 마스크 (opacityBrush 매개 변수)를 지정 하는 경우 브러시는 D2D1_EXTEND_MODE_CLAMP로 설정 하는 해당 x 및 y 확장 모드는 ID2D1BitmapBrush 이어야 합니다. 자세한 내용은 설명 섹션을 참조하세요.  
  
##  <a name="fillmesh"></a>CRenderTarget::FillMesh  
 지정된 된 메시의 내부를 그립니다.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMesh`  
 그리는 데 메시입니다.  
  
 `pBrush`  
 메시를 그리는 데 사용 되는 브러시입니다.  
  
##  <a name="fillopacitymask"></a>CRenderTarget::FillOpacityMask  
 브러시에 지정한 비트맵에서 설명 된 불투명 마스크를 적용 하 고 렌더링 대상의 영역을 그리는 해당 브러시를 사용 하 여 키를 누릅니다.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 `pOpacityMask`  
 위치 및 장치 독립적 픽셀을 그릴 타원의 반지름입니다.  
  
 `pBrush`  
 DestinationRectangle로 지정 된 렌더링 대상의 영역을 그리는 데 사용 되는 브러시입니다.  
  
 `content`  
 불투명 마스크 콘텐츠의 형식을 포함합니다. 불투명 마스크 혼합 되는 색 공간을 결정 하는 값 사용 됩니다.  
  
 `rectDest`  
 장치 독립적 픽셀 그릴 렌더링 대상의 지역입니다.  
  
 `rectSrc`  
 불투명 마스크 (장치 독립적 픽셀 단위)로 사용할 비트맵의 지역입니다.  
  
##  <a name="fillrectangle"></a>CRenderTarget::FillRectangle  
 지정된 된 사각형의 내부를 그립니다.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 장치 독립적 픽셀에서 그릴 사각형의 차원입니다.  
  
 `pBrush`  
 사각형을 그리는 데 사용 되는 브러시의 내부입니다.  
  
##  <a name="fillroundedrectangle"></a>CRenderTarget::FillRoundedRectangle  
 지정된 된 모퉁이가 둥근된 사각형의 내부를 그립니다.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `rectRounded`  
 장치 독립적 픽셀 그릴 모서리가 둥근된 사각형의 크기입니다.  
  
 `pBrush`  
 모퉁이가 둥근된 사각형의 내부를 그리는 데 사용 되는 브러시입니다.  
  
##  <a name="flush"></a>CRenderTarget::Flush  
 모든 보류 중인 그리기 명령을 실행합니다.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `tag1`  
 오류가 있는 경우 오류 또는 0을 초래한 그리기 작업에 대 한 태그를 포함 합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.  
  
 `tag2`  
 오류가 있는 경우 오류 또는 0을 초래한 그리기 작업에 대 한 태그를 포함 합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다.  
  
##  <a name="getantialiasmode"></a>CRenderTarget::GetAntialiasMode  
 텍스트가 아닌 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드를 검색합니다.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 텍스트가 아닌 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드입니다.  
  
##  <a name="getdpi"></a>CRenderTarget::GetDpi  
 렌더링 대상의 dpi (인치당 도트)을 반환  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>반환 값  
 렌더링 대상의 dpi (인치당 도트).  
  
##  <a name="getmaximumbitmapsize"></a>CRenderTarget::GetMaximumBitmapSize  
 렌더링 대상에서 지 원하는 한 비트맵 차원의의 장치 독립적 단위 (픽셀)의 최대 크기를 가져옵니다.  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 렌더링 대상에서 지 원하는 한 비트맵 차원의 픽셀 단위로 최대 크기  
  
##  <a name="getpixelformat"></a>CRenderTarget::GetPixelFormat  
 렌더링 대상의 픽셀 형식 및 알파 모드를 검색합니다.  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>반환 값  
 렌더링 대상의 픽셀 형식 및 알파 모드  
  
##  <a name="getpixelsize"></a>CRenderTarget::GetPixelSize  
 (장치 픽셀)에서 렌더링 대상의 크기를 반환합니다.  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 (장치 픽셀)에서 렌더링 대상의 크기  
  
##  <a name="getrendertarget"></a>CRenderTarget::GetRenderTarget  
 반환 ID2D1RenderTarget 인터페이스  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1RenderTarget 인터페이스에 대 한 포인터입니다.  
  
##  <a name="getsize"></a>CRenderTarget::GetSize  
 장치 독립적 픽셀의 렌더링 대상의 크기를 반환합니다.  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 장치 독립적 픽셀의 렌더링 대상의 현재 크기  
  
##  <a name="gettags"></a>CRenderTarget::GetTags  
 이후 그리기 작업에 대 한 레이블을 가져옵니다.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `tag1`  
 이후 그리기 작업에 대 한 첫 번째 레이블을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다. NULL을 지정 하는 경우이 매개 변수 값이 없는 검색 됩니다.  
  
 `tag2`  
 이후 그리기 작업에 대 한 두 번째 레이블을 포함합니다. 이 매개 변수는 초기화되지 않은 상태로 전달됩니다. NULL을 지정 하는 경우이 매개 변수 값이 없는 검색 됩니다.  
  
##  <a name="gettextantialiasmode"></a>CRenderTarget::GetTextAntialiasMode  
 텍스트 및 문자 모양 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드를 가져옵니다.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 텍스트 및 문자 모양 그리기 작업에 대 한 현재 앨리어싱 사용 안 함 모드입니다.  
  
##  <a name="gettextrenderingparams"></a>CRenderTarget::GetTextRenderingParams  
 렌더링 대상의 현재 텍스트 렌더링 옵션을 검색합니다.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>매개 변수  
 `textRenderingParams`  
 이 메서드가 반환 하는 경우 렌더링 대상에 대 한 포인터의 주소 textRenderingParamscontains의 현재 텍스트 렌더링 옵션입니다.  
  
##  <a name="gettransform"></a>CRenderTarget::GetTransform  
 기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생 합니다.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>매개 변수  
 `transform`  
 렌더링 대상에 적용할 변환입니다.  
  
##  <a name="issupported"></a>CRenderTarget::IsSupported  
 렌더링 대상에서 지정된 된 속성을 지원 하는지 여부를 나타냅니다.  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `renderTargetProperties`  
 테스트 하려면 렌더링 대상 속성  
  
### <a name="return-value"></a>반환 값  
 이 렌더링 대상;에서 지정 된 렌더링 대상 속성 지 원하는 경우 TRUE입니다. 그렇지 않으면 FALSE  
  
##  <a name="isvalid"></a>CRenderTarget::IsValid  
 리소스 유효성 검사  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 리소스는 올바르지 않습니다. 그렇지 않으면 FALSE입니다.  
  
##  <a name="m_lstresources"></a>CRenderTarget::m_lstResources  
 목록 CD2DResource 개체에 대 한 포인터입니다.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>CRenderTarget::m_pRenderTarget  
 ID2D1RenderTarget 개체에 대 한 포인터입니다.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>CRenderTarget::m_pTextFormatDefault  
 기본 텍스트 서식을 포함 하는 CD2DTextFormat 개체에 대 한 포인터입니다.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>CRenderTarget::operator ID2D1RenderTarget *  
 반환 ID2D1RenderTarget 인터페이스  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1RenderTarget 인터페이스에 대 한 포인터입니다.  
  
##  <a name="popaxisalignedclip"></a>CRenderTarget::PopAxisAlignedClip  
 렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다. 이 메서드를 호출한 후에 있는 클립은 더 이상 다음 그리기 작업에 적용 됩니다.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>CRenderTarget::PopLayer  
 그리기 작업을 마지막 PushLayer로 지정 된 계층으로 리디렉션하는를 호출 합니다.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>CRenderTarget::PushAxisAlignedClip  
 렌더링 대상에서 마지막 축에 맞춰진 클립을 제거합니다. 이 메서드를 호출한 후에 있는 클립은 더 이상 다음 그리기 작업에 적용 됩니다.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>매개 변수  
 `rectClip`  
 크기 및 장치 독립적 픽셀에서 위치는 클리핑 영역입니다.  
  
 `mode`  
 장면 콘텐츠를 사용 하 여 클립을 혼합 하 여 사용 하 고 하위 픽셀 경계에 있는 클립 rects의 가장자리를 그리는 데 사용 되는 앨리어싱 사용 안 함 모드입니다. 혼합이 수행 하는 PopAxisAlignedClip 메서드가 호출 되 고 계층 내 각 기본 형식에 적용 되지 않는 경우.  
  
##  <a name="pushlayer"></a>CRenderTarget::PushLayer  
 PopLayer를 호출할 때까지 이후의 모든 그리기 작업을 받을 수 있도록 렌더링 대상에 지정 된 계층을 추가 합니다.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>매개 변수  
 `layerParameters`  
 내용 경계, 기하학적 마스크, 불투명도, 불투명 마스크와 계층에 대 한 앤티 앨리어싱 옵션입니다.  
  
 `layer`  
 이후 그리기 작업을 수신 하는 계층입니다.  
  
##  <a name="restoredrawingstate"></a>CRenderTarget::RestoreDrawingState  
 지정 된 ID2D1DrawingStateBlock의 렌더링 대상의 그리기 상태를 설정합니다.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>매개 변수  
 `drawingStateBlock`  
 렌더링 대상의 새 드로잉 상태입니다.  
  
##  <a name="savedrawingstate"></a>CRenderTarget::SaveDrawingState  
 지정 된 ID2D1DrawingStateBlock에 현재 그리기 상태를 저장합니다.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `drawingStateBlock`  
 이 메서드가 반환 하는 경우 렌더링 대상의 현재 그리기 상태를 포함 합니다. 이 매개 변수를 메서드에 전달 하기 전에 초기화 되어야 합니다.  
  
##  <a name="setantialiasmode"></a>CRenderTarget::SetAntialiasMode  
 렌더링 대상의 앨리어싱 사용 안 함 모드를 설정합니다. 앤티 앨리어싱 모드 이후의 모든 그리기 작업, 텍스트 및 문자 모양 그리기 작업 제외에 적용 됩니다.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `antialiasMode`  
 그리기 작업을 나중에 대 한 앤티 앨리어싱 모드입니다.  
  
##  <a name="setdpi"></a>CRenderTarget::SetDpi  
 렌더링 대상의 (DPI) 인치당 도트를 설정합니다.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>매개 변수  
 `sizeDPI`  
 렌더링 대상의 수평/수직 Dpi를 지정 하는&0; 보다 크거나 같은 값입니다.  
  
##  <a name="settags"></a>CRenderTarget::SetTags  
 이후 그리기 작업에 대 한 레이블을 지정합니다.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>매개 변수  
 `tag1`  
 다음 그리기 작업에 적용 하는 레이블.  
  
 `tag2`  
 다음 그리기 작업에 적용 하는 레이블.  
  
##  <a name="settextantialiasmode"></a>CRenderTarget::SetTextAntialiasMode  
 이후 텍스트 및 문자 모양 그리기 작업을 사용 하는 앨리어싱 사용 안 함 모드를 지정 합니다.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `textAntialiasMode`  
 이후 텍스트 및 문자 모양 그리기 작업에 사용할 앨리어싱 사용 안 함 모드입니다.  
  
##  <a name="settextrenderingparams"></a>CRenderTarget::SetTextRenderingParams  
 모든 후속 텍스트와 문자 모양 그리기 작업에 적용할 텍스트 렌더링 옵션을 지정 합니다.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `textRenderingParams`  
 모든 후속 텍스트와 문자 모양 그리기 작업;에 적용할 텍스트 렌더링 옵션 현재 텍스트 렌더링 옵션의 선택을 취소 하려면 NULL입니다.  
  
##  <a name="settransform"></a>CRenderTarget::SetTransform  
 기존 변환을 대체 렌더링 대상에 지정된 된 변환을 적용 합니다. 이후의 모든 그리기 작업은 변환 된 공간에서 발생 합니다.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>매개 변수  
 `transform`  
 렌더링 대상에 적용할 변환입니다.  
  
##  <a name="verifyresource"></a>CRenderTarget::VerifyResource  
 CD2DResource 개체 validity; 확인 아직 하지 않은 경우 해당 개체를 만듭니다.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `pResource`  
 CD2DResource 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 True 이면 개체가 청소 하는 경우 그렇지 않으면 FALSE입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

