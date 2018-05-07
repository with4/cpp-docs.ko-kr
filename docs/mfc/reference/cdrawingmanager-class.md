---
title: CDrawingManager 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
dev_langs:
- C++
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9a0255bae48ad61f140bdc8aa8a6091cf10bc77
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdrawingmanager-class"></a>CDrawingManager 클래스
`CDrawingManager` 클래스 복합 그리기 알고리즘을 구현 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|`CDrawingManager` 개체를 생성합니다.|  
|`CDrawingManager::~CDrawingManager`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|응용 프로그램에 직접 쓸 수 있는 32 비트 장치 독립적 비트맵 DIB ()을 만듭니다.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|투명 하 게 또는 반투명 픽셀로 있는 비트맵을 표시 합니다.|  
|[CDrawingManager::DrawRotated](#drawrotated)|원본 DC + /-90도에서 지정된 된 사각형 내에 콘텐츠를 회전|  
|[CDrawingManager::DrawEllipse](#drawellipse)|제공 된 테두리 및 채우기 색으로는 타원을 그립니다.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|링 그리고 색 그라데이션을 사용 하 여 채웁니다.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|선을 그립니다.|  
|[CDrawingManager::DrawRect](#drawrect)|제공 된 테두리 및 채우기 색 사각형을 그립니다.|  
|[CDrawingManager::DrawShadow](#drawshadow)|사각형 영역에 대 한 그림자를 그립니다.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|두 개의 색 그라데이션을 사각형 영역을 채웁니다.|  
|[CDrawingManager::FillGradient](#fillgradient)|지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다. 그라데이션 색상 변경의 방향을 지정 됩니다.|  
|[CDrawingManager::GrayRect](#grayrect)|사각형에 지정 된 회색 색으로 채웁니다.|  
|[CDrawingManager::HighlightRect](#highlightrect)|사각형 영역을 강조 표시합니다.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|HLS 표현에서 색을 RGB 표현으로 변환 합니다.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|HLS 표현에서 색을 RGB 표현으로 변환 합니다.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|HSV 표현에서 색을 RGB 표현으로 변환 합니다.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|빨간색, 녹색 또는 파란색 구성 요소에는 색상을 나타내는 값을 변환 하는 도우미 메서드.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|사각형 영역 대칭 이동합니다.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|반투명 픽셀에 대 한 최종 색상을 결정 하는 도우미 메서드.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|그림자도 사용할 수 있는 비트맵을 만듭니다.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|RGB 표현에서 색을 HSL 표현으로 변환 합니다.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|RGB 표현에서 색을 HSV 표현으로 변환 합니다.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|부분적으로 투명 한 비트맵의 픽셀 색을 지정 하는 도우미 메서드.|  
|[CDrawingManager::SetPixel](#setpixel)|단일 픽셀 비트맵에 지정된 된 색을 변경 하는 도우미 메서드.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|가중치가 적용 된 비율에 따라 두 가지 색을 결합 합니다.|  
  
## <a name="remarks"></a>설명  
 `CDrawingManager` 클래스 그림자, 색 그라데이션 및 강조 표시 된 사각형 그리기에 대 한 함수를 제공 합니다. 알파 혼합도 수행합니다. 응용 프로그램의 UI를 직접 변경 하려면이 클래스를 사용할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager  
 생성 된 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) 개체입니다.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dc`  
 장치 컨텍스트에 대 한 참조입니다. `CDrawingManager` 그리기에 대 한이 컨텍스트를 사용 합니다.  
  
##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32  
 응용 프로그램에 직접 쓸 수 있는 32 비트 장치 독립적 비트맵 DIB ()을 만듭니다.  
  
```  
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,  
    void** pBits);
 
static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,  
    COLORREF clrTransparent = -1);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `size`|A [CSize](../../atl-mfc-shared/reference/csize-class.md) 비트맵의 크기를 나타내는 매개 변수입니다.|  
|[out] `pBits`|DIB의 위치를 수신 하는 데이터 포인터에 대 한 포인터 비트 값입니다.|  
|`bitmap`|원래 비트맵에 대 한 핸들|  
|`clrTransparent`|원래 비트맵 이미지의 투명 한 색을 지정 하는 RGB 값입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 새로 만든된 DIB 비트맵에 대 한 핸들 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 DIB 비트맵을 만드는 방법에 대 한 자세한 내용은 참조 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491)합니다.  
  
##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha  
 투명 하 게 또는 반투명 픽셀로 있는 비트맵을 표시 합니다.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDstDC`  
 대상 장치 컨텍스트에 대 한 포인터입니다.  
  
 [in] `rectDst`  
 대상 사각형입니다.  
  
 [in] `pSrcDC`  
 장치 컨텍스트 원본에 대 한 포인터입니다.  
  
 [in] `rectSrc`  
 소스 사각형입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드 두 비트맵의 알파 혼합을 수행합니다. 알파 혼합 하는 방법에 대 한 자세한 내용은 참조 [로드](http://msdn.microsoft.com/library/windows/desktop/dd183351) Windows sdk에서입니다.  
  
##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse  
 제공 된 테두리 및 채우기 색으로는 타원을 그립니다.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 타원에 대 한 경계 사각형입니다.  
  
 [in] `clrFill`  
 이 메서드는 타원을 채우는 데 사용 되는 색입니다.  
  
 [in] `clrLine`  
 이 방법은 타원의 경계를 사용 하는 색입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 색상 중 하나가-1로 설정 되어 있으면 타원 그리기 하지 않고 반환 합니다. 경계 사각형의 크기 0 이면 타원 그리기 없이 반환 합니다.  
  
##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing  
 링 그리고 색 그라데이션을 사용 하 여 채웁니다.  
  
```  
BOOL DrawGradientRing(
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    COLORREF colorBorder,  
    int nAngle,  
    int nWidth,  
    COLORREF clrFace = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md) 그라데이션 링에 대 한 경계를 지정 하는 매개 변수입니다.  
  
 [in] `colorStart`  
 첫 번째 그라데이션 색입니다.  
  
 [in] `colorFinish`  
 그라데이션의 마지막 색입니다.  
  
 [in] `colorBorder`  
 테두리의 색입니다.  
  
 [in] `nAngle`  
 초기 그라데이션 그리기 각도 지정 하는 매개 변수입니다. 이 값은 0에서 360 사이 여야 합니다.  
  
 [in] `nWidth`  
 링에 대 한 테두리의 너비입니다.  
  
 [in] `clrFace`  
 내부 링의 색입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 정의 된 사각형 `rect` 최소 5 픽셀 너비와 5 픽셀 이어야 합니다.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine, CDrawingManager::DrawLineA  
 선을 그립니다.  
  
```  
void DrawLine(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    COLORREF clrLine);
 
void DrawLineA(
    double x1,  
    double y1,  
    double x2,  
    double y2,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `x1`|줄의 시작 위치 x 좌표입니다.|  
|[in] `y1`|줄의 시작 위치 y 좌표입니다.|  
|[in] `x2`|줄이 끝나는 x 좌표입니다.|  
|[in] `y2`|줄이 끝나는 y 좌표입니다.|  
|[in] `clrLine`|줄의 색입니다.|  
  
### <a name="remarks"></a>설명  
 이 메서드는 실패 하는 경우 `clrLine` 가-1입니다.  
  
##  <a name="drawrect"></a>  CDrawingManager::DrawRect  
 제공 된 테두리 및 채우기 색 사각형을 그립니다.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 사각형의 경계입니다.  
  
 [in] `clrFill`  
 이 메서드는 사각형을 채우는 데 사용 되는 색입니다.  
  
 [in] `clrLine`  
 사각형의 테두리에 대 한이 메서드는 사용 되는 색입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 색상 중 하나가-1로 설정 되어 있으면 유지 하지 않고 반환 합니다. 사각형의 크기는 0도 반환 합니다.  
  
##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow  
 사각형 영역에 대 한 그림자를 그립니다.  
  
```  
BOOL DrawShadow(
    CRect rect,  
    int nDepth,  
    int iMinBrightness = 100,  
    int iMaxBrightness = 50,  
    CBitmap* pBmpSaveBottom = NULL,  
    CBitmap* pBmpSaveRight = NULL,  
    COLORREF clrBase = (COLORREF)-1,  
    BOOL bRightShadow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 응용 프로그램에서 사각형 영역입니다. 그리기 관리자는이 영역 아래의 그림자를 그릴 됩니다.  
  
 [in] `nDepth`  
 그림자의 높이 너비입니다.  
  
 [in] `iMinBrightness`  
 그림자의 최소 밝기입니다.  
  
 [in] `iMaxBrightness`  
 그림자의 최대 밝기입니다.  
  
 [in] `pBmpSaveBottom`  
 그림자의 아래쪽 부분에 대 한 이미지를 포함 하는 비트맵에 대 한 포인터입니다.  
  
 [in] `pBmpSaveRight`  
 사각형의 오른쪽에 그려진 그림자에 대 한 이미지를 포함 하는 비트맵에 대 한 포인터입니다.  
  
 [in] `clrBase`  
 그림자의 색입니다.  
  
 [in] `bRightShadow`  
 그림자를 그리는 방법을 나타내는 부울 매개 변수입니다. 경우 `bRightShadow` 은 `TRUE`, `DrawShadow` 사각형의 오른쪽에 그림자를 그립니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 매개 변수를 사용 하 여 아래쪽 및 오른쪽 그림자에 대 한 두 개의 올바른 비트맵을 제공할 수 있습니다 `pBmpSaveBottom` 및 `pBmpSaveRight`합니다. 이러한 경우 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체는 연결 된 GDI 개체 `DrawShadow` 그림자도 해당 비트맵을 사용 합니다. 경우는 `CBitmap` 매개 변수에 연결 된 GDI 개체 없는 `DrawShadow` 그림자를 그리는 만들고 매개 변수를 비트맵에 연결 합니다. 에 대 한 호출 이후 `DrawShadow`, 그리기 작업 속도를 높이려면 이러한 비트맵을 제공할 수 있습니다. 에 대 한 자세한 내용은 `CBitmap` 클래스 및 참조 GDI 개체 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
 이러한 매개 변수 중 하나에 해당 하는 경우 `NULL`, `DrawShadow` 그림자를 자동으로 그려집니다.  
  
 설정한 경우 `bRightShadow` 를 `FALSE`, 아래 있으며 사각형 영역 왼쪽에 그림자를 그릴 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 사용 하는 `DrawShadow` 의 메서드는 `CDrawingManager` 클래스. 이 코드 조각은의 일부인는 [Prop 시트 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient  
 두 개의 색 그라데이션을 사각형 영역을 채웁니다.  
  
```  
void Fill4ColorsGradient(
    CRect rect,  
    COLORREF colorStart1,  
    COLORREF colorFinish1,  
    COLORREF colorStart2,  
    COLORREF colorFinish2,  
    BOOL bHorz = TRUE,  
    int nPercentage = 50);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 채울 사각형입니다.  
  
 [in] `colorStart1`  
 첫 번째 색 그라데이션에 대 한 초기 색입니다.  
  
 [in] `colorFinish1`  
 첫 번째 색 그라데이션의 마지막 색입니다.  
  
 [in] `colorStart2`  
 두 번째 색 그라데이션에 대 한 초기 색입니다.  
  
 [in] `colorFinish2`  
 두 번째 색 그라데이션의 마지막 색입니다.  
  
 [in] `bHorz`  
 나타내는 부울 매개 변수 여부 `Fill4ColorsGradient` 가로 또는 세로 그라데이션 색을 지정 합니다. `TRUE` 가로 그라데이션을 나타냅니다.  
  
 [in] `nPercentage`  
 0에서 100 사이의 정수입니다. 이 값을 첫 번째 색 그라데이션을 사용 하 여 채울 사각형의 백분율을 나타냅니다.  
  
### <a name="remarks"></a>설명  
 서로 위에 있는 이거나, 값에 따라 다음 두 가지 색 그라데이션이 있는 사각형 가득 차면 `bHorz`합니다. 각 색 그라데이션을 메서드와 함께 독립적으로 계산 됩니다 [CDrawingManager::FillGradient](#fillgradient)합니다.  
  
 이 메서드는 경우 어설션 오류가 생성 `nPercentage` 가 0 보다 작거나 100을 넘는 합니다.  
  
##  <a name="fillgradient"></a>  CDrawingManager::FillGradient  
 지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.  
  
```  
void FillGradient(
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    BOOL bHorz = TRUE,  
    int nStartFlatPercentage = 0,  
    int nEndFlatPercentage = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 채울 사각형 영역입니다.  
  
 [in] `colorStart`  
 첫 번째 그라데이션 색입니다.  
  
 [in] `colorFinish`  
 그라데이션의 마지막 색입니다.  
  
 [in] `bHorz`  
 지정 하는 부울 매개 변수 여부 `FillGradient` 가로 또는 세로 그라데이션을 그리는 해야 합니다.  
  
 [in] `nStartFlatPercentage`  
 사각형의 백분율 있는 `FillGradient` 채웁니다 `colorStart` 하는 그라데이션의 시작 되기 전에 합니다.  
  
 [in] `nEndFlatPercentage`  
 사각형의 백분율 있는 `FillGradient` 채웁니다 `colorFinish` 그라데이션 완료 된 후입니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 사용 하는 `FillGradient` 의 메서드는 `CDrawingManager` 클래스. 이 코드 조각은의 일부인는 [MS Office 2007 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2  
 지정 된 색 그라데이션을 사용 하 여 사각형 영역을 채웁니다.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 채울 사각형 영역입니다.  
  
 [in] `colorStart`  
 그라데이션의 첫 번째 색입니다.  
  
 [in] `colorFinish`  
 그라데이션의 마지막 색입니다.  
  
 [in] `nAngle`  
 0부터 360 사이의 정수입니다. 이 매개 변수는 색 그라데이션의 방향을 지정합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `nAngle` 색 그라데이션의 방향을 지정할 수 있습니다. 색 그라데이션의 방향을 지정 하면 지정할 있습니다 색 그라데이션의 시작 위치입니다. 값이 0에 대 한 `nAngle` 그라데이션 사각형의 위쪽에서 시작을 나타냅니다. 로 `nAngle` 증가 하면 시작 되는 위치에 기울기 각도에 따라 시계 반대 방향에서 이동 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 사용 하는 `FillGradient2` 의 메서드는 `CDrawingManager` 클래스. 이 코드 조각은의 일부인는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>  CDrawingManager::GrayRect  
 사각형에 지정 된 회색 색으로 채웁니다.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 채울 사각형 영역입니다.  
  
 [in] `nPercentage`  
 사각형에 포함 하려는 회색의 비율입니다.  
  
 [in] `clrTransparent`  
 투명 한 색입니다.  
  
 [in] `clrDisabled`  
 디 채도 대 한 경우이 메서드를 사용 하는 색 `nPercentage` -1로 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 매개 변수에 대해 `nPercentage`, 값이 작을수록 더 어두운 색을 나타냅니다.  
  
 에 대 한 최대값 `nPercentage` 는 200 개입니다. 200 보다 큰 값에는 사각형의 모양을 변경 되지 않습니다. 값이-1 이면이 메서드는 사용 `clrDisabled` 사각형의 채도 제한할 수 있습니다.  
  
##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect  
 사각형 영역을 강조 표시합니다.  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 강조 표시 사각형 영역입니다.  
  
 [in] `nPercentage`  
 투명도 강조 해야 나타내는 백분율입니다.  
  
 [in] `clrTransparent`  
 투명 한 색입니다.  
  
 [in] `nTolerance`  
 색 허용 오차를 나타내는 0에서 255 사이의 정수입니다.  
  
 [in] `clrBlend`  
 혼합에 대 한 기본 색입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 경우 `nPercentage` 0에서 99 사이의 `HighlightRect` 알파 혼합 알고리즘을 사용 합니다. 알파 혼합 하는 방법에 대 한 자세한 내용은 참조 [알파 혼합 선 및 채우기](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)합니다. 경우 `nPercentage` -1 이면이 메서드는 기본 강조 표시 수준을 사용 합니다. 경우 `nPercentage` 은 100,이 메서드는 아무 작업도 수행 하 고 반환 `TRUE`합니다.  
  
 매개 변수를 사용 하는 메서드가 `nTolerance` 사각형 영역을 강조 표시 여부를 결정 합니다. 사각형을 응용 프로그램의 배경색 간의 차이 강조 표시 및 `clrTransparent` 이어야 미만 `nTolerance` (빨강, 녹색 및 파랑)에 각 색의 구성 요소에서 합니다.  
  
##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE  
 HLS 표현에서 색을 RGB 표현으로 변환 합니다.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `H`  
 색상을 나타내는 색을 나타내는 0과 1 사이의 숫자입니다.  
  
 [in] `L`  
 색에 대 한 명도 나타내는 0과 1 사이의 숫자입니다.  
  
 [in] `S`  
 색 채도 나타내는 0과 1 사이의 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 제공 된 HLS 색의 RGB 표현입니다.  
  
### <a name="remarks"></a>설명  
 HSV (예: 색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 [색](http://go.microsoft.com/fwlink/p/?linkid=119126)합니다.  
  
 이 메서드는 및 `CDrawingManager::HLStoRGB_TWO` 메서드 같은 작업을 수행 하지만 서로 다른 값이 필요는 `H` 매개 변수입니다. 이 방법에서는 `H` 은 원 백분율로 표시 됩니다. 에 `CDrawingManager::HLStoRGB_TWO` 메서드를 `H` 0을 모두 나타내는 빨간색 360 사이의 각도 값은입니다. 예를 들어, `HLStoRGB_ONE`에 대 한 0.25 `H` 가 값이 90와 같음 `HLStoRGB_TWO`합니다.  
  
##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO  
 HLS 표현에서 색을 RGB 표현으로 변환 합니다.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `H`  
 색에 대 한 색상을 나타내는 0부터 360 사이의 숫자입니다.  
  
 [in] `L`  
 색에 대 한 명도 나타내는 0과 1 사이의 숫자입니다.  
  
 [in] `S`  
 색 채도 나타내는 0과 1 사이의 숫자입니다.  
  
### <a name="return-value"></a>반환 값  
 제공 된 HLS 색의 RGB 표현입니다.  
  
### <a name="remarks"></a>설명  
 HSV (예: 색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 [색](http://go.microsoft.com/fwlink/p/?linkid=119126)합니다.  
  
 이 메서드는 및 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) 메서드 같은 작업을 수행 하지만 서로 다른 값이 필요는 `H` 매개 변수입니다. 이 방법에서는 `H` 0을 모두 나타내는 빨간색 360 사이의 각도 값은입니다. 에 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) 메서드를 `H` 은 원 백분율로 표시 됩니다. 예를 들어, `HLStoRGB_ONE`에 대 한 0.25 `H` 가 값이 90와 같음 `HLStoRGB_TWO`합니다.  
  
##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB  
 HSV 표현에서 색을 RGB 표현으로 변환 합니다.  
  
```  
static COLORREF __stdcall HSVtoRGB(
    double H,  
    double S,  
    double V);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `H`|색에 대 한 색상을 나타내는 0부터 360 사이의 숫자입니다.|  
|[in] `S`|색 채도 나타내는 0과 1 사이의 숫자입니다.|  
|[in] `V`|0과 1 사이의 숫자 색에 대 한 값을 나타냅니다.|  
  
### <a name="return-value"></a>반환 값  
 제공 된 HSV 색의 RGB 표현입니다.  
  
### <a name="remarks"></a>설명  
 HSV (예: 색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 [색](http://go.microsoft.com/fwlink/p/?linkid=119126)합니다.  
  
##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB  
 빨간색, 녹색 또는 파란색 구성 요소에 색상을 나타내는 값을 변환합니다.  
  
```  
static double __stdcall HuetoRGB(
    double m1,  
    double m2,  
    double h);

 
static BYTE __stdcall HueToRGB(
    float rm1,  
    float rm2,  
    float rh);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `m1`  
 설명 부분을 참조하세요.  
  
 [in] `m2`  
 설명 부분을 참조하세요.  
  
 [in] `h`  
 설명 부분을 참조하세요.  
  
 [in] `rm1`  
 설명 부분을 참조하세요.  
  
 [in] `rm2`  
 설명 부분을 참조하세요.  
  
 [in] `rh`  
 설명 부분을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 제공 된 색상에 대 한 개별 빨간색, 녹색 또는 파란색 구성 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 도우미 메서드는는 `CDrawingManager` 클래스가 HSV 또는 HSL 표현에 있는 색의 개별 빨간색, 녹색 및 파랑 구성 요소를 계산 하는 데 사용 하 합니다. 이 메서드는 프로그래머는 직접 호출을 설계 되지 않았습니다. 입력된 매개 변수는 변환 알고리즘에 의존 하는 값입니다.  
  
 HSV 또는 HSL 색 RGB 표현으로 변환 하려면 다음 방법 중 하나를 호출 합니다.  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect  
 사각형 영역 대칭 이동합니다.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 대칭 영역의 경계 사각형입니다.  
  
 [in] `bHorz`  
 사각형 가로 또는 세로로 대칭 이동 하는지 여부를 나타내는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 소유한 장치 컨텍스트의 영역 대칭 이동할 수는 `CDrawingManager` 클래스입니다. 경우 `bHorz` 로 설정 된 `TRUE`,이 메서드는 영역을 가로로 대칭 이동 합니다. 그렇지 않으면 것 상하 대칭 이동 하는 영역입니다.  
  
##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha  
 반투명 픽셀에 대 한 최종 색을 계산합니다.  
  
```  
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    int percent);
 
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    double percentR,  
    double percentG,  
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    COLORREF dstPixel,  
    int percent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `srcPixel`  
 픽셀에 대 한 초기 색입니다.  
  
 [in] `percent`  
 투명도의 백분율을 나타내는 0에서 100 사이의 숫자입니다. 값이 100 초기 색상 완전히 투명 하 게 임을 나타냅니다.  
  
 [in] `percentR`  
 투명도 빨강 구성 요소에 대 한 백분율을 나타내는 0에서 100 사이의 숫자입니다.  
  
 [in] `percentG`  
 투명도 녹색 구성 요소에 대 한 백분율을 나타내는 0에서 100 사이의 숫자입니다.  
  
 [in] `percentB`  
 투명도 파랑 구성 요소에 대 한 백분율을 나타내는 0에서 100 사이의 숫자입니다.  
  
 [in] `dstPixel`  
 픽셀에 대 한 기본 색입니다.  
  
### <a name="return-value"></a>반환 값  
 반투명 픽셀에 대 한 마지막 색입니다.  
  
### <a name="remarks"></a>설명  
 반투명 비트맵 색 지정에 대 한 도우미 클래스 이며 프로그래머는 직접 호출 하도록 설계 되지 않았습니다.  
  
 변수가 있는 메서드의 버전을 사용 하는 경우 `dstPixel`, 최종 색은의 조합 `dstPixel` 및 `srcPixel`합니다. `srcPixel` 색은 부분적으로 투명 한 색의 기본 색상을 통해 `dstPixel`합니다.  
  
##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask  
 그림자도 사용할 수 있는 비트맵을 만듭니다.  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nDepth`  
 그림자의 높이 너비입니다.  
  
 [in] `clrBase`  
 그림자의 색입니다.  
  
 [in] `iMinBrightness`  
 그림자의 최소 밝기입니다.  
  
 [in] `iMaxBrightness`  
 그림자의 최대 밝기입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 성공 하는 경우 만든된 비트맵에 대 한 핸들 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>설명  
 경우 `nDepth` 가이 메서드는 0으로 설정 종료 되 고 반환 `NULL`합니다. 경우 `nDepth` 3 보다 작은 이면 그림자의 높이 너비를 3 픽셀로 설정 됩니다.  
  
##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL  
 색상, 채도 및 밝기 (HSL) 표현 색을 빨간색, 녹색 및 파란색 (RGB) 표현에서 변환합니다.  
  
```  
static void __stdcall RGBtoHSL(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* L);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `rgb`|RGB 값의 색입니다.|  
|[out] `H`|메서드는 색에 대 한 색상을 저장 하는 double 데이터에 대 한 포인터입니다.|  
|[out] `S`|Double 메서드 색 채도 저장 하는 위치에 대 한 포인터입니다.|  
|[out] `L`|Double 메서드 밝기 색에 대 한 저장 위치에 대 한 포인터입니다.|  
  
### <a name="remarks"></a>설명  
 HSV (예: 색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 [색](http://go.microsoft.com/fwlink/p/?linkid=119126)합니다.  
  
 반환된 된 값에 대 한 `H` 0 위치 0과 1을 모두 나타내며 빨간색 1 사이의 소수 값으로 표현 됩니다. 반환 된 값에 대 한 `S` 및 `L` 는 0과 1 사이의 숫자입니다.  
  
##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV  
 RGB 표현에서 색을 HSV 표현으로 변환 합니다.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rgb`  
 RGB 표현에서 변환 하는 색입니다.  
  
 [out] `H`  
 이 메서드는 색상을 나타내는 색에 대 한 결과 저장 하는 double 데이터에 대 한 포인터입니다.  
  
 [out] `S`  
 이 메서드는 색에 대 한 결과 채도 저장 하는 double 데이터에 대 한 포인터입니다.  
  
 [out] `V`  
 이 메서드는 색에 대 한 결과 값을 저장 하는 double 데이터에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 HSV (예: 색상, 채도 및 값), (색상, 채도 및 명도), HSL 또는 RGB (빨강, 녹색 및 파랑) 색을 나타낼 수 있습니다. 색의 다양 한 표현에 대 한 자세한 내용은 참조 [색](http://go.microsoft.com/fwlink/p/?linkid=119126)합니다.  
  
 반환된 된 값에 대 한 `H` 는 0부터 360 사이의 숫자 0에서 360 모두 여기서 빨간색을 나타냅니다. 반환 값에 대 한 `S` 및 `V` 는 0과 1 사이의 숫자입니다.  
  
##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel  
 투명 한 비트맵의 픽셀을 색을 지정 합니다.  
  
```  
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,  
    CRect rect,  
    int x,  
    int y,  
    int percent,  
    int iShadowSize,  
    COLORREF clrBase = (COLORREF)-1,  
    BOOL bIsRight = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBits`  
 비트맵 비트 값에 대 한 포인터입니다.  
  
 [in] `rect`  
 응용 프로그램에서 사각형 영역입니다. 그리기 관리자는 아래와이 영역의 오른쪽에 그림자를 그립니다.  
  
 [in] `x`  
 가로 좌표는 픽셀 색입니다.  
  
 [in] `y`  
 색상을 픽셀의 세로 좌표입니다.  
  
 [in] `percent`  
 투명도의 비율입니다.  
  
 [in] `iShadowSize`  
 그림자의 높이 너비입니다.  
  
 [in] `clrBase`  
 그림자의 색입니다.  
  
 [in] `bIsRight`  
 어떤 픽셀 색을 나타내는 부울 매개 변수입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="remarks"></a>설명  
 이 메서드는에서 사용 되는 도우미 메서드는 [CDrawingManager::DrawShadow](#drawshadow) 메서드. 그림자를 그릴 경우 호출 하는 것이 좋습니다 `CDrawingManager::DrawShadow` 대신 합니다.  
  
 경우 `bIsRight` 로 설정 된 `TRUE`, 색상을 픽셀은 측정 `x` 의 오른쪽 가장자리에서 픽셀 `rect`합니다. 이 경우 `FALSE`, 색상을 픽셀은 측정 `x` 의 왼쪽된 가장자리에서 픽셀 `rect`합니다.  
  
##  <a name="setpixel"></a>  CDrawingManager::SetPixel  
 단일 픽셀 비트맵에 지정된 된 색을 변경합니다.  
  
```  
static void __stdcall SetPixel(
    COLORREF* pBits,  
    int cx,  
    int cy,  
    int x,  
    int y,  
    COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pBits`|비트맵의 비트 값에 대 한 포인터입니다.|  
|[in] `cx`|비트맵의 전체 너비입니다.|  
|[in] `cy`|비트맵의 총 높이입니다.|  
|[in] `x`|변경할 경우 비트맵의 픽셀의 x 좌표입니다.|  
|[in] `y`|변경할 경우 비트맵의 픽셀의 y 좌표입니다.|  
|[in] `color`|제공 된 좌표로 식별 되는 픽셀에 대 한 새로운 색입니다.|  
  
##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors  
 가중치가 적용 된 비율에 따라 두 가지 색을 결합 합니다.  
  
```  
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,  
    COLORREF color2,  
    double dblLumRatio = 1.,  
    int k1 = 1,  
    int k2 = 1);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `color1`|첫 번째 색을 혼합 합니다.|  
|[in] `color2`|두 번째 색을 혼합 합니다.|  
|[in] `dblLumRatio`|새 색의 명도 대 한 비율입니다. `SmartMixColors` 최종 색상을 결정 하기 전에이 비율에 따라 혼합 된 색의 명도 곱합니다.|  
|[in] `k1`|첫 번째 색에 대 한 가중치가 적용 된 비율입니다.|  
|[in] `k2`|두 번째 색에 대 한 가중치가 적용 된 비율입니다.|  
  
### <a name="return-value"></a>반환 값  
 제공 된 색의 가중치가 적용 된 혼합을 나타내는 색입니다.  
  
### <a name="remarks"></a>설명  
 어느 경우이 방법이 실패 하면 오류가 발생 하 여 `k1` 또는 `k2` 가 0 보다 작습니다. 메서드가 반환 하는 경우에 0으로 설정 되어 이러한 매개 변수를 모두, `RGB(0, 0, 0)`합니다.  
  
 가중치가 적용 된 비율이 다음 수식을 사용 하 여 계산 됩니다: (color1 * k1 + color2 \* k2) /(k1 + k2) 합니다. 가중치가 적용 된 비율을 결정 메서드 혼합된 색의 명도 계산 합니다. 여 명도 곱한 다음 `dblLumRatio`합니다. 값 1.0 보다 큰 경우 메서드 명도 혼합된 색에 대 한 새 값으로 설정 합니다. 그렇지 않으면 명도 1.0으로 설정 됩니다.  
  
##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated  
 지정된 된 사각형 내에 DC 콘텐츠 원본으로 90도 회전 합니다.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>매개 변수  
 `rectDest`  
 대상 사각형입니다.  
  
 `dcSrc`  
 소스 장치 컨텍스트에 합니다.  
  
 `bClockWise`  
 `TRUE` + 90도 회전; 나타냅니다. `FALSE` 90도 회전을 나타냅니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)
