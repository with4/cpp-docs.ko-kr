---
title: "CMFCToolBarImages 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::CMFCToolBarImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::AdaptColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::AddImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::CleanUp
- AFXTOOLBARIMAGES/CMFCToolBarImages::Clear
- AFXTOOLBARIMAGES/CMFCToolBarImages::ConvertTo32Bits
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyImageToClipboard
- AFXTOOLBARIMAGES/CMFCToolBarImages::CopyTo
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateFromImageList
- AFXTOOLBARIMAGES/CMFCToolBarImages::CreateRegionFromImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::DeleteImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Draw
- AFXTOOLBARIMAGES/CMFCToolBarImages::DrawEx
- AFXTOOLBARIMAGES/CMFCToolBarImages::EnableRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::EndDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::ExtractIcon
- AFXTOOLBARIMAGES/CMFCToolBarImages::FillDitheredRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetBitsPerPixel
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetCount
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWell
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetImageWellLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLastImageRect
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetMask
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetResourceOffset
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetScale
- AFXTOOLBARIMAGES/CMFCToolBarImages::GetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::GrayImages
- AFXTOOLBARIMAGES/CMFCToolBarImages::Is32BitTransparencySupported
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsRTL
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsReadOnly
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsScaled
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsUserImagesList
- AFXTOOLBARIMAGES/CMFCToolBarImages::IsValid
- AFXTOOLBARIMAGES/CMFCToolBarImages::Load
- AFXTOOLBARIMAGES/CMFCToolBarImages::LoadStr
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapFromSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapTo3dColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::MapToSysColorAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::Mirror
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmap
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorBitmapVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::MirrorVert
- AFXTOOLBARIMAGES/CMFCToolBarImages::OnSysColorChange
- AFXTOOLBARIMAGES/CMFCToolBarImages::PrepareDrawImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::Save
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetAlwaysLight
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetDisabledImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetFadedImageAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetImageSize
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetLightPercentage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetMapTo3DColors
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetPreMultiplyAutoCheck
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetSingleImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::SetTransparentColor
- AFXTOOLBARIMAGES/CMFCToolBarImages::SmoothResize
- AFXTOOLBARIMAGES/CMFCToolBarImages::UpdateImage
- AFXTOOLBARIMAGES/CMFCToolBarImages::PreMultiplyAlpha
- AFXTOOLBARIMAGES/CMFCToolBarImages::m_bDisableTrueColorAlpha
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarImages class
ms.assetid: d4e50518-9ffc-406f-9996-f79e5cd38155
caps.latest.revision: 31
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ff94497108033b17d52b79594fdbe30e8ed7da03
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarimages-class"></a>CMFCToolBarImages 클래스
도구 모음에 이미지를 지정 합니다. `CMFCToolBarImages` 클래스는 파일 또는 응용 프로그램 리소스에서 로드 된 도구 모음 이미지를 관리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarImages : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarImages::CMFCToolBarImages](#cmfctoolbarimages)|`CMFCToolBarImages` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarImages::AdaptColors](#adaptcolors)||  
|[CMFCToolBarImages::AddIcon](#addicon)|도구 모음 이미지 아이콘을 추가 합니다.|  
|[CMFCToolBarImages::AddImage](#addimage)|도구 모음 이미지에 비트맵을 추가합니다.|  
|[CMFCToolBarImages::CleanUp](#cleanup)||  
|[CMFCToolBarImages::Clear](#clear)|이 개체에 할당 된 시스템 리소스를 해제 합니다.|  
|[CMFCToolBarImages::ConvertTo32Bits](#convertto32bits)|변환에는 비트맵을을 32 bpp 이미지 밑줄이 그어집니다.|  
|[CMFCToolBarImages::CopyImageToClipboard](#copyimagetoclipboard)||  
|[CMFCToolBarImages::CopyTo](#copyto)||  
|[CMFCToolBarImages::CreateFromImageList](#createfromimagelist)|이미지 목록에서 도구 모음 이미지를 초기화 합니다 ( [CImageList 클래스](../../mfc/reference/cimagelist-class.md)).|  
|[CMFCToolBarImages::CreateRegionFromImage](#createregionfromimage)||  
|[CMFCToolBarImages::DeleteImage](#deleteimage)|도구 모음 이미지의이 집합에는 사용자 지정 이미지가 포함 된 경우 도구 모음 이미지의 지정된 된 인덱스에 있는 이미지를 삭제 합니다.|  
|[CMFCToolBarImages::Draw](#draw)|하나의 도구 모음 이미지 (단추)를 그립니다.|  
|[CMFCToolBarImages::DrawEx](#drawex)||  
|[CMFCToolBarImages::EnableRTL](#enablertl)||  
|[CMFCToolBarImages::EndDrawImage](#enddrawimage)|도구 모음 이미지를 그릴 후 시스템 리소스를 해제 합니다.|  
|[CMFCToolBarImages::ExtractIcon](#extracticon)|도구 모음 이미지에서 지정 된 이미지 인덱스를 가진 아이콘을 반환 합니다.|  
|[CMFCToolBarImages::FillDitheredRect](#fillditheredrect)|도구 모음 배경 색이 포함 하는 브러시를 사용 하 여 사각형을 채웁니다.|  
|[CMFCToolBarImages::GetAlwaysLight](#getalwayslight)||  
|[CMFCToolBarImages::GetBitsPerPixel](#getbitsperpixel)|밑줄이 그어진된 이미지의 현재 해상도 반환합니다.|  
|[CMFCToolBarImages::GetCount](#getcount)|도구 모음 이미지의 수를 반환합니다.|  
|[CMFCToolBarImages::GetDisabledImageAlpha](#getdisabledimagealpha)|비활성화 된 이미지에 사용 되는 알파 채널을 반환 합니다.|  
|[CMFCToolBarImages::GetFadedImageAlpha](#getfadedimagealpha)||  
|[CMFCToolBarImages::GetImageSize](#getimagesize)|메모리 (원본 크기)에 저장 되어 있는 도구 모음 이미지의 크기 또는 화면 (대상 크기)에 그려진 도구 모음 이미지의 크기를 검색 합니다.|  
|[CMFCToolBarImages::GetImageWell](#getimagewell)|모든 도구 모음 이미지를 포함 하는 비트맵에 핸들을 반환 합니다.|  
|[CMFCToolBarImages::GetImageWellLight](#getimagewelllight)||  
|[CMFCToolBarImages::GetLastImageRect](#getlastimagerect)||  
|[CMFCToolBarImages::GetLightPercentage](#getlightpercentage)||  
|[CMFCToolBarImages::GetMapTo3DColors](#getmapto3dcolors)||  
|[CMFCToolBarImages::GetMask](#getmask)||  
|[CMFCToolBarImages::GetResourceOffset](#getresourceoffset)|지정 된 리소스 ID에 대 한 이미지 인덱스를 반환합니다.|  
|[CMFCToolBarImages::GetScale](#getscale)|밑줄이 그어진된 이미지의 현재 크기 조정 비율을 반환합니다.|  
|[CMFCToolBarImages::GetTransparentColor](#gettransparentcolor)||  
|[CMFCToolBarImages::GrayImages](#grayimages)|도구 모음 이미지를 사용할 수 없는 보이도록 할 회색으로 표시 합니다.|  
|[CMFCToolBarImages::Is32BitTransparencySupported](#is32bittransparencysupported)|운영 체제 32 비트 알파 혼합을 지원 하는지 여부를 결정 합니다.|  
|[CMFCToolBarImages::IsPreMultiplyAutoCheck](#ispremultiplyautocheck)||  
|[CMFCToolBarImages::IsRTL](#isrtl)|오른쪽에서 왼쪽 (RTL) 지원 사용 되는지 여부를 결정 합니다.|  
|[CMFCToolBarImages::IsReadOnly](#isreadonly)|도구 모음 이미지 읽기 전용인 지 여부를 결정 합니다.|  
|[CMFCToolBarImages::IsScaled](#isscaled)|여부 밑줄이 그어진된 이미지는 크기가 조정 여부를 알려 줍니다.|  
|[CMFCToolBarImages::IsUserImagesList](#isuserimageslist)|이미지 사용자 지정 도구 모음 이미지의이 집합에 포함 되는지 여부를 결정 합니다.|  
|[CMFCToolBarImages::IsValid](#isvalid)|이 도구 모음 이미지이 집합이 유효한 도구 모음 이미지에 포함 되는지 여부를 결정 합니다.|  
|[CMFCToolBarImages::Load](#load)|파일 또는 시스템 리소스에서 도구 모음 이미지를 로드합니다.|  
|[CMFCToolBarImages::LoadStr](#loadstr)||  
|[CMFCToolBarImages::MapFromSysColor](#mapfromsyscolor)||  
|[CMFCToolBarImages::MapTo3dColors](#mapto3dcolors)||  
|[CMFCToolBarImages::MapToSysColor](#maptosyscolor)||  
|[CMFCToolBarImages::MapToSysColorAlpha](#maptosyscoloralpha)||  
|[CMFCToolBarImages::Mirror](#mirror)|모든 도구 모음 이미지를 가로 방향으로 반영 됩니다.|  
|[CMFCToolBarImages::MirrorBitmap](#mirrorbitmap)|가로 방향으로 비트맵을 미러링합니다.|  
|[CMFCToolBarImages::MirrorBitmapVert](#mirrorbitmapvert)||  
|[CMFCToolBarImages::MirrorVert](#mirrorvert)||  
|[CMFCToolBarImages::OnSysColorChange](#onsyscolorchange)||  
|[CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)|지정된 된 크기에서 도구 모음 이미지를 그리는 데 필요한 리소스를 할당 합니다.|  
|[CMFCToolBarImages::Save](#save)|도구 모음 이미지의이 집합에는 사용자 지정 이미지가 포함 된 경우 도구 모음 이미지 파일에 저장 합니다.|  
|[CMFCToolBarImages::SetAlwaysLight](#setalwayslight)||  
|[CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha)|비활성화 된 이미지에 사용 되는 알파 채널 값을 설정 합니다.|  
|[CMFCToolBarImages::SetFadedImageAlpha](#setfadedimagealpha)||  
|[CMFCToolBarImages::SetImageSize](#setimagesize)|도구 모음 이미지 (원본 크기)의 크기를 설정합니다.|  
|[CMFCToolBarImages::SetLightPercentage](#setlightpercentage)||  
|[CMFCToolBarImages::SetMapTo3DColors](#setmapto3dcolors)||  
|[CMFCToolBarImages::SetPreMultiplyAutoCheck](#setpremultiplyautocheck)||  
|[CMFCToolBarImages::SetSingleImage](#setsingleimage)||  
|[CMFCToolBarImages::SetTransparentColor](#settransparentcolor)|도구 모음 이미지의 투명 한 색을 설정합니다.|  
|[CMFCToolBarImages::SmoothResize](#smoothresize)|밑줄이 그어진된 이미지를 원활 하 게 크기가 조정 됩니다.|  
|[CMFCToolBarImages::UpdateImage](#updateimage)|비트맵에서 도구 모음 사용자 지정 이미지를 업데이트합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarImages::PreMultiplyAlpha](#premultiplyalpha)||  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarImages::m_bDisableTrueColorAlpha](#m_bdisabletruecoloralpha)|`TRUE`truecolor 알파 혼합 (32 비트 색상)은 사용할 수 없습니다.|  
  
## <a name="remarks"></a>주의  
 관리 하는 도구 모음 이미지의 전체 비트맵 `CMFCToolbarImages` 하나 이상의 작은 도구 모음 이미지 (단추)의 크기가 고정 되어 구성 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 방법을 보여 줍니다.는 `CMFCToolBarImages` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCToolBarImages` 클래스입니다. 도구 모음 이미지의 크기를 설정, 이미지를 로드 하 고, 이미지의 투명 한 색을 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&32;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&33;](../../mfc/codesnippet/cpp/cmfctoolbarimages-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCToolBarImages`   
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarimages.h  
  
##  <a name="adaptcolors"></a>CMFCToolBarImages::AdaptColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AdaptColors(
    COLORREF clrBase,  
    COLORREF clrTone);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `clrBase`  
 [in] `clrTone`  
  
### <a name="remarks"></a>주의  
  
##  <a name="addicon"></a>CMFCToolBarImages::AddIcon  
 도구 모음 이미지의 목록에 아이콘을 추가 합니다.  
  
```  
int AddIcon(
    HICON hIcon,  
    BOOL bAlphaBlend=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hIcon`  
 추가 될 아이콘에 대 한 핸들입니다.  
  
 [in] `bAlphaBlend`  
 `TRUE`알파 혼합; 사용 되는이 아이콘은 그렇지 않으면 `FALSE`합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 추가 된 도구 모음 이미지의&0;부터 시작 하는 인덱스 그렇지 않으면-1입니다.  
  
##  <a name="addimage"></a>CMFCToolBarImages::AddImage  
 도구 모음 이미지에 비트맵을 추가합니다.  
  
```  
int AddImage(
    HBITMAP hbmp,  
    BOOL bSetBitPerPixel=FALSE);

int AddImage(
    const CMFCToolBarImages& imageList,  
    int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hbmp`  
 추가를 비트맵에 대 한 핸들입니다.  
  
 [in] `bSetBitPerPixel`  
 `TRUE`하는 경우는 `CMFCToolBarImages` 개체가 새 이미지의 색 농도 (픽셀 당 비트)를 사용 합니다. `FALSE` 경우는 `CMFCToolbarImages` 현재 색 농도 보관 합니다.  
  
 [in] `imageList`  
 에 대 한 참조는 `CMFCToolbarImages` 추가할 이미지를 포함 하는 개체입니다.  
  
 [in] `nIndex`  
 원본에 대 한 인덱스 `CMFCToolbarImages` 추가할 이미지의 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 도구 모음 수가 이미지를 `CMFCToolBarImages` 새로운 비트맵 성공적으로 추가 된 후 개체를 유지 관리 작업에 실패 한 경우-1입니다.  
  
##  <a name="cleanup"></a>CMFCToolBarImages::CleanUp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall CleanUp();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="clear"></a>CMFCToolBarImages::Clear  
 시스템 리소스를 해제 하는 [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) 할당 된 개체입니다.  
  
```  
void Clear();
```  
  
##  <a name="cmfctoolbarimages"></a>CMFCToolBarImages::CMFCToolBarImages  
 `CMFCToolBarImages` 개체를 생성합니다.  
  
```  
CMFCToolBarImages();
```  
  
### <a name="remarks"></a>주의  
 생성 된 `CMFCToolBarImages` 개체의 렌더링 엔진을 초기화 하 고 16 x 15 픽셀 이미지 크기를 기본값으로 설정 합니다. 사용 하 여 [CMFCToolBarImages::SetImageSize](#setimagesize) 이미지를 추가 하기 전에 이미지 크기를 변경 합니다.  
  
##  <a name="copyimagetoclipboard"></a>CMFCToolBarImages::CopyImageToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyImageToClipboard(int iImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iImage`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="copyto"></a>CMFCToolBarImages::CopyTo  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyTo(CMFCToolBarImages& imageList);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `imageList`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="createfromimagelist"></a>CMFCToolBarImages::CreateFromImageList  
 도구 모음 이미지를 초기화 한 [CImageList 클래스](../../mfc/reference/cimagelist-class.md) 개체입니다.  
  
```  
BOOL CreateFromImageList(const CImageList& imageList);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `imageList`  
 도구 모음 이미지에 대 한 원본으로 사용할 이미지 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하 여 신속 하 게 외부 이미지 목록에서 도구 모음 이미지 목록 초기화 합니다.  
  
##  <a name="createregionfromimage"></a>CMFCToolBarImages::CreateRegionFromImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static HRGN __stdcall CreateRegionFromImage(
    HBITMAP bmp,  
    COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bmp`  
 [in] `clrTransparent`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="deleteimage"></a>CMFCToolBarImages::DeleteImage  
 도구 모음 이미지의 지정된 된 인덱스에는 사용자 지정 이미지를 삭제 합니다.  
  
```  
BOOL DeleteImage(int iImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iImage`  
 삭제 하려면 이미지의&0;부터 시작 하는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지를 성공적으로 삭제 하는 경우 `FALSE` 이미지 인덱스 올바르지는 `CMFCToolbarImages` 개체는 일시적 이며는 `CMFCToolbarImages` 개체 사용자 지정 이미지를 포함 하지 않거나 다른 경우 오류가 발생 합니다.  
  
##  <a name="draw"></a>CMFCToolBarImages::Draw  
 하나의 도구 모음 이미지를 그립니다.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int x,  
    int y,  
    int iImageIndex,  
    BOOL bHilite=FALSE,  
    BOOL bDisabled=FALSE,  
    BOOL bIndeterminate=FALSE,  
    BOOL bShadow=FALSE,  
    BOOL bInactive=FALSE,  
    BYTE alphaSrc=255);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `x`  
 이미지를 그릴 사각형의 왼쪽의 X 좌표입니다.  
  
 [in] `y`  
 이미지를 그릴 사각형의 위쪽의 Y 좌표입니다.  
  
 [in] `iImageIndex`  
 표시할 이미지의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `bHilite`  
 `TRUE`경우 이미지를 강조 표시 합니다. 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bDisabled`  
 `TRUE`이미지를 사용할 수 없는 스타일;에 그릴 경우 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bIndeterminate`  
 `TRUE`이미지가는 상태임 스타일;에 그릴 경우 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bShadow`  
 `TRUE`이미지가는 그림자를 그릴 경우 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bInactive`  
 `TRUE`이미지가 비활성 상태 스타일;에 그릴 경우 그렇지 않으면 `FALSE`합니다.  
  
 [in] `alphaSrc`  
 알파 채널 (opacity) 값입니다. 값이 255 의미 이미지가 그려지는 불투명 하 게 됩니다. 값이 0 이면 이미지 투명 그려집니다. 이 값은 32 비트 컬러 이미지에 대해서만 및 Windows Vista 유리 스타일을 표시 하는 이미지를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정된 된 이미지는 성공적으로 표시 된 경우 `FALSE` 이미지 인덱스 잘못 되었거나 다른 몇 가지 오류가 발생 한 경우.  
  
##  <a name="drawex"></a>CMFCToolBarImages::DrawEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    CRect rect,  
    int iImageIndex,  
    ImageAlignHorz horzAlign = ImageAlignHorzLeft,  
    ImageAlignVert vertAlign = ImageAlignVertTop,  
    CRect rectSrc = CRect(0,
    0,
    0,
    0),  
    BYTE alphaSrc = 255);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 [in] `rect`  
 [in] `iImageIndex`  
 [in] `horzAlign`  
 [in] `vertAlign`  
 [in] `rectSrc`  
 [in] `0`  
 [in] `0)`  
 [in] `alphaSrc`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="enablertl"></a>CMFCToolBarImages::EnableRTL  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall EnableRTL(BOOL bIsRTL = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bIsRTL`  
  
### <a name="remarks"></a>주의  
  
##  <a name="enddrawimage"></a>CMFCToolBarImages::EndDrawImage  
 시스템 리소스를 해제 하는 [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage) 를 호출 하 여 도구 모음 이미지를 그린 후 할당 [CMFCToolBarImages::Draw](#draw)합니다.  
  
```  
void EndDrawImage(CAfxDrawState& ds);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ds`  
 에 대 한 참조는 `CAfxDrawState` 에 전달 된 개체는 `PrepareDrawImage` 메서드.  
  
##  <a name="extracticon"></a>CMFCToolBarImages::ExtractIcon  
 도구 모음 이미지에서 지정 된 이미지 인덱스를 가진 아이콘을 반환 합니다.  
  
```  
HICON ExtractIcon(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nIndex`  
 아이콘으로 추출할은 이미지가 이미지 목록에서&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 추출 된 아이콘에 대 한 핸들 또는 `NULL` 경우 `nIndex` 범위를 벗어났습니다.  
  
##  <a name="fillditheredrect"></a>CMFCToolBarImages::FillDitheredRect  
 도구 모음 배경 색으로 사각형을 채웁니다.  
  
```  
static void FillDitheredRect(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rect`  
 채울 사각형의 좌표입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 시스템 색 COLOR_BTNFACE 및 COLOR_BTNHIGHLIGHT의 평균을 색으로 사각형을 채웁니다. 시스템 256 색을 사용 하는 경우 사각형이 채워집니다 디더링된 패턴 이러한 두 가지 색을 대신 합니다.  
  
##  <a name="getalwayslight"></a>CMFCToolBarImages::GetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetAlwaysLight() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getcount"></a>CMFCToolBarImages::GetCount  
 도구 모음 이미지 목록의 이미지의 수를 반환합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이미지 수는 `CMFCToolBarImages` 개체입니다.  
  
##  <a name="getdisabledimagealpha"></a>CMFCToolBarImages::GetDisabledImageAlpha  
 비활성화 된 이미지에 사용 되는 알파 채널 (opacity) 값을 반환 합니다.  
  
```  
static BYTE GetDisabledImageAlpha();
```  
  
### <a name="return-value"></a>반환 값  
 현재 알파 채널 값입니다.  
  
### <a name="remarks"></a>주의  
 호출할 수 있습니다 [CMFCToolBarImages::SetDisabledImageAlpha](#setdisabledimagealpha) 알파 채널 값을 변경 합니다.  
  
##  <a name="getfadedimagealpha"></a>CMFCToolBarImages::GetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BYTE __stdcall GetFadedImageAlpha();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getimagesize"></a>CMFCToolBarImages::GetImageSize  
 메모리 (원본 크기)에 저장 되어 있는 도구 모음 이미지의 크기 또는 화면 (대상 크기)에 그려진 도구 모음 이미지의 크기를 검색 합니다.  
  
```  
SIZE GetImageSize(BOOL bDest=FALSE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bDest`  
 `TRUE`검색할 대상 크기입니다. `FALSE` 소스 이미지 크기를 검색 하도록 합니다.  
  
### <a name="return-value"></a>반환 값  
 A `SIZE` 구조를 이미지의 크기를 픽셀 단위로 지정 합니다.  
  
### <a name="remarks"></a>주의  
 원본 이미지의 크기는에 저장 된 이미지의 크기는 [CMFCToolbarImages](../../mfc/reference/cmfctoolbarimages-class.md) 개체입니다. 호출할 수 있습니다 [CMFCToolBarImages::SetImageSize](#setimagesize) 원본 크기를 설정 합니다. 기본값은 16 x 15 픽셀입니다.  
  
 기본적으로 대상 이미지 크기는 0x0입니다. 호출할 때 대상 크기를 지정 [CMFCToolBarImages::PrepareDrawImage](#preparedrawimage)합니다. [CMFCToolBarImages::EndDrawImage](#enddrawimage) 메서드는 대상 크기를 기본값으로 다시 설정 합니다.  
  
##  <a name="getimagewell"></a>CMFCToolBarImages::GetImageWell  
 모든 도구 모음 이미지를 포함 하는 비트맵에 핸들을 반환 합니다.  
  
```  
HBITMAP GetImageWell() const;  
```  
  
### <a name="return-value"></a>반환 값  
 도구 모음 이미지를 포함 하는 비트맵에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 도구 모음 이미지 라고 하는 단일 비트맵의 행에 저장 되어 있는 *이미지 잘*합니다. 이미지 웰을 도구 모음 이미지를 찾으려면 도구 모음 이미지의 너비에 따라 이미지의 인덱스를 곱하기 (참조 [CMFCToolBarImages::GetImageSize](#getimagesize))도 이미지 내에 있는 이미지의 가로 오프셋을 얻을 수 있습니다.  
  
##  <a name="getimagewelllight"></a>CMFCToolBarImages::GetImageWellLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetImageWellLight() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getlastimagerect"></a>CMFCToolBarImages::GetLastImageRect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CRect GetLastImageRect() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getlightpercentage"></a>CMFCToolBarImages::GetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetLightPercentage() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getmapto3dcolors"></a>CMFCToolBarImages::GetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL GetMapTo3DColors() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getmask"></a>CMFCToolBarImages::GetMask  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
HBITMAP GetMask(int iImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iImage`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="getresourceoffset"></a>CMFCToolBarImages::GetResourceOffset  
 지정 된 리소스 ID에 대 한 이미지 인덱스를 반환합니다.  
  
```  
int GetResourceOffset(UINT uiResId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResId`  
 이미지 리소스 id입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 이미지 인덱스 지정 된 리소스 ID 사용 하 여 이미지에 존재 하지 않는 경우-1입니다.  
  
##  <a name="gettransparentcolor"></a>CMFCToolBarImages::GetTransparentColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
COLORREF GetTransparentColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="grayimages"></a>CMFCToolBarImages::GrayImages  
 도구 모음 이미지를 사용할 수 없는 보이도록 할 회색으로 표시 합니다.  
  
```  
BOOL GrayImages(int nGrayImageLuminancePercentage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nGrayImageLuminancePercentage`  
 광도 비율입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`성공적으로 선택할 수 없게 된 이미지 컬렉션에 있는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 각 픽셀의 빨간색, 녹색 및 파랑 구성 요소를 평균 하 고 결과 곱한 여 도구 모음 이미지를 수정 합니다. `nGrayImageLuminancePercentage` 100으로 나눈 값입니다. 경우 `nGrayImageLuminancePercentage` 가 0 또는 음수, 130의 기본값 대신 사용 됩니다.  
  
> [!NOTE]
>  변경 내용을 취소 하려면 원본에서 이미지를 다시 로드 해야 합니다. 호출 하 여 수행할 수 있습니다 [CMFCToolBarImages::Load](#load) 또는 [CMFCToolBarImages::UpdateImage](#updateimage) (만 이미지에 대 한 사용자 정의)를 호출 하 여 [CMFCToolBarImages::Clear](#clear) 를 호출 하 여 이미지를 다시 추가 하 고 [CMFCToolBarImages::AddIcon](#addicon) 또는 [CMFCToolBarImages::AddImage](#addimage)합니다.  
  
##  <a name="is32bittransparencysupported"></a>CMFCToolBarImages::Is32BitTransparencySupported  
 운영 체제 32 비트 알파 혼합을 지원 하는지 여부를 지정 합니다.  
  
```  
static BOOL Is32BitTransparencySupported();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`알파 혼합 32 비트 지원 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 정적 메서드를 사용 하 여 운영 체제 32 비트 알파 혼합을 지원 하는지 여부를 런타임에 결정 합니다. 이 기능이 지원 [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 이상 버전.  
  
##  <a name="ispremultiplyautocheck"></a>CMFCToolBarImages::IsPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsPreMultiplyAutoCheck() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="isreadonly"></a>CMFCToolBarImages::IsReadOnly  
 도구 모음 이미지 읽기 전용인 지 여부를 지정 합니다.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구 모음 이미지 되며 읽기 전용 이며, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `CMFCToolbarImages` 개체는 읽기 전용 비트맵을 사용 하 여 복사한 하거나 도구 모음 이미지를 사용 하 여 비트맵에서 읽기 전용 파일에서 로드 된 경우는 `CMFCToolBarImages::CopyTemp` 메서드.  
  
##  <a name="isrtl"></a>CMFCToolBarImages::IsRTL  
 오른쪽에서 왼쪽 (RTL) 지원 사용 되는지 여부를 지정 합니다.  
  
```  
static BOOL IsRTL();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`RTL 지원을 활성화 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 RTL 지원 응용 프로그램은 오른쪽에서 왼쪽으로 아랍어, 히브리어, 페르시아어, 우르두어 등에서 읽을 수 있는 언어를 지역화 하는 경우에 사용 됩니다.  
  
##  <a name="isuserimageslist"></a>CMFCToolBarImages::IsUserImagesList  
 이미지 사용자 지정 도구 모음 이미지의이 집합에 포함 되는지 여부를 지정 합니다.  
  
```  
BOOL IsUserImagesList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하는 경우는 `CMFCToolBarImages` 도구 모음 사용자 지정 이미지를 포함 하는 개체 고, 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="isvalid"></a>CMFCToolBarImages::IsValid  
 유효한 도구 모음 이미지 도구 모음 이미지의이 집합에 포함 되어 있는지 여부를 나타냅니다.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우에 `CMFCToolBarImages` 개체는 유효 하 고, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 `CMFCToolBarImages` 도구 모음 이미지를 사용 하 여 비트맵을 해당 핸들은 개체가 유효 하지 않습니다 `NULL`합니다.  
  
##  <a name="load"></a>CMFCToolBarImages::Load  
 파일 또는 시스템 리소스에서 도구 모음 이미지를 로드합니다.  
  
```  
BOOL Load(
    UINT uiResID,  
    HINSTANCE hinstRes=NULL,  
    BOOL bAdd=FALSE);

BOOL Load(
    LPCTSTR lpszBmpFileName,   
    DWORD nMaxFileSize = 819200);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `uiResID`  
 비트맵 리소스의 ID입니다.  
  
 [in] `hinstRes`  
 리소스 DLL의 인스턴스입니다.  
  
 [in] `bAdd`  
 `TRUE`기존 비트맵에 로드 된 비트맵을 추가 하려면 또는 `FALSE` 기존 비트맵 이미지를 바꿔야 합니다.  
  
 [in] `lpszBmpFileName`  
 비트맵을 로드 하는 디스크 파일 경로입니다.  
  
 [in] `nMaxFileSize`  
 비트맵 파일에 바이트의 최대 수 또는 파일 크기에 관계 없이 비트맵을 로드 하는 0을 지정 합니다. 메서드가 반환 하는 경우 파일의 크기가이 최대 크기를 초과 하면 `FALSE` 비트맵을 로드 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`비트맵을 성공적으로 로드 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 파일에 읽기 전용 특성을 읽기 전용으로 이미지 목록이 표시 됩니다.  
  
##  <a name="loadstr"></a>CMFCToolBarImages::LoadStr  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL LoadStr(
    LPCTSTR lpszResourceName,  
    HINSTANCE hinstRes = NULL,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszResourceName`  
 [in] `hinstRes`  
 [in] `bAdd`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="mapfromsyscolor"></a>CMFCToolBarImages::MapFromSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapFromSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="mapto3dcolors"></a>CMFCToolBarImages::MapTo3dColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MapTo3dColors(
    BOOL bUseRGBQUAD = TRUE,  
    COLORREF clrSrc = (COLORREF)-1,  
    COLORREF clrDest = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bUseRGBQUAD`  
 [in] `clrSrc`  
 [in] `clrDest`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="maptosyscolor"></a>CMFCToolBarImages::MapToSysColor  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColor(
    COLORREF color,  
    BOOL bUseRGBQUAD = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
 [in] `bUseRGBQUAD`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="maptosyscoloralpha"></a>CMFCToolBarImages::MapToSysColorAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static COLORREF __stdcall MapToSysColorAlpha(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `color`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="mirror"></a>CMFCToolBarImages::Mirror  
 도구 모음 이미지를 가로 미러 이미지를 바꿉니다.  
  
```  
BOOL Mirror();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지 미러링 성공적으로 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 오른쪽에서 왼쪽 문자 체계를 지 원하는 데 사용 됩니다.  
  
##  <a name="mirrorbitmap"></a>CMFCToolBarImages::MirrorBitmap  
 가로 미러 이미지는 비트맵을으로 바꿉니다.  
  
```  
static BOOL MirrorBitmap(
    HBITMAP& hbmp,  
    int cxImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `hbmp`  
 미러링 하는 비트맵에 대 한 핸들입니다.  
  
 [in] `cxImage`  
 픽셀 단위로 이미지의 너비입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지를 성공적으로 미러링 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 오른쪽에서 왼쪽 문자 체계를 지 원하는 데 사용 됩니다.  
  
##  <a name="mirrorbitmapvert"></a>CMFCToolBarImages::MirrorBitmapVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall MirrorBitmapVert(
    HBITMAP& hbmp,  
    int cyImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hbmp`  
 [in] `cyImage`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="mirrorvert"></a>CMFCToolBarImages::MirrorVert  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL MirrorVert();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="onsyscolorchange"></a>CMFCToolBarImages::OnSysColorChange  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void OnSysColorChange();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="premultiplyalpha"></a>CMFCToolBarImages::PreMultiplyAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static BOOL __stdcall PreMultiplyAlpha(
    HBITMAP hbmp,  
    BOOL bAutoCheckPremlt);

BOOL PreMultiplyAlpha(HBITMAP hbmp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `hbmp`  
 [in] `bAutoCheckPremlt`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="m_bdisabletruecoloralpha"></a>CMFCToolBarImages::m_bDisableTrueColorAlpha  
 `TRUE`truecolor 알파 혼합 (32 비트 색상)은 사용할 수 없습니다.  
  
```  
static BOOL m_bDisableTrueColorAlpha;  
```  
  
### <a name="remarks"></a>주의  
 이 멤버 변수를 설정 `FALSE` 도구 모음 이미지에 대 한 알파 혼합 truecolor 사용할 수 있도록 합니다.  
  
 기본값은 `TRUE` 이전 버전과 호환성에 대 한 합니다.  
  
##  <a name="preparedrawimage"></a>CMFCToolBarImages::PrepareDrawImage  
 지정된 된 크기에서 도구 모음 이미지를 그리는 데 필요한 리소스를 할당 합니다.  
  
```  
BOOL PrepareDrawImage(
    CAfxDrawState& ds,  
    CSize sizeImageDest=CSize(0,
    0)  
    BOOL bFadeInactive=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ds`  
 에 대 한 참조 `CAfxDrawState` 이미지 렌더링 단계 간에 할당 된 리소스를 저장 하는 구조입니다.  
  
 [in] `sizeImageDest`  
 대상 이미지의 크기를 지정합니다.  
  
 [in] `bFadeInactive`  
 `TRUE`비활성 원하는 이미지를 그릴 실패 합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구 모음 이미지를 그리는 데 필요한 리소스가 성공적으로 할당 그렇지 않은 경우 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 호출한 후 호출할 수 있습니다 [CMFCToolBarImages::Draw](#draw) 임의의 횟수입니다. 호출 해야 드로잉을 마친 후 [CMFCToolBarImages::EndDrawImage](#enddrawimage) 에서 할당 된 리소스를 해제 하려면 `PrepareDrawImage`합니다.  
  
##  <a name="save"></a>CMFCToolBarImages::Save  
 도구 모음 이미지의이 집합에는 사용자 지정 이미지가 포함 된 경우 도구 모음 이미지 파일에 저장 합니다.  
  
```  
BOOL Save(LPCTSTR lpszBmpFileName=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszBmpFileName`  
 디스크 파일 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`도구 모음 이미지는 성공적으로 저장 된 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 디스크 파일에 사용자 지정 이미지를 저장 하려면이 메서드를 호출 합니다. 경우 `lpszBmpFileName` 는 `NULL`, 있는 비트맵으로 로드 된 파일에 비트맵을 저장 하는 메서드는 [CMFCToolBarImages::Load](#load) 메서드.  
  
##  <a name="setalwayslight"></a>CMFCToolBarImages::SetAlwaysLight  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetAlwaysLight(BOOL bAlwaysLight = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAlwaysLight`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setdisabledimagealpha"></a>CMFCToolBarImages::SetDisabledImageAlpha  
 비활성화 된 이미지에 사용 되는 알파 채널 (opacity) 값을 설정 합니다.  
  
```  
static void SetDisabledImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nValue`  
 알파 채널의 새 값입니다.  
  
### <a name="remarks"></a>주의  
 비활성화 된 이미지에 대 한 사용자 지정 알파 값을 설정 하려면이 메서드를 사용 합니다. 기본값은 반투명 하 비활성화 된 단추 이미지에 이르게 127입니다. 값 0 설정 하는 경우 사용할 수 없는 이미지 완전히 투명 하 게 됩니다. 값이 255로 설정 하면 사용할 수 없는 이미지를 완전히 불투명 하 게 됩니다.  
  
##  <a name="setfadedimagealpha"></a>CMFCToolBarImages::SetFadedImageAlpha  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static void __stdcall SetFadedImageAlpha(BYTE nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nValue`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setimagesize"></a>CMFCToolBarImages::SetImageSize  
 각 도구 모음 이미지 (원본 크기)의 크기를 설정합니다.  
  
```  
void SetImageSize(
    SIZE sizeImage,  
    BOOL bUpdateCount=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `sizeImage`  
 도구 모음 이미지의 새 크기입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 도구 모음 이미지의 크기는 16 x 15 픽셀입니다. 다른 크기의 도구 모음 이미지를 사용 하려는 경우이 메서드를 호출 합니다.  
  
##  <a name="setlightpercentage"></a>CMFCToolBarImages::SetLightPercentage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetLightPercentage(int nValue);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nValue`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setmapto3dcolors"></a>CMFCToolBarImages::SetMapTo3DColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetMapTo3DColors(BOOL bMapTo3DColors);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMapTo3DColors`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setpremultiplyautocheck"></a>CMFCToolBarImages::SetPreMultiplyAutoCheck  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetPreMultiplyAutoCheck(BOOL bAuto = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bAuto`  
  
### <a name="remarks"></a>주의  
  
##  <a name="setsingleimage"></a>CMFCToolBarImages::SetSingleImage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SetSingleImage();
```  
  
### <a name="remarks"></a>주의  
  
##  <a name="settransparentcolor"></a>CMFCToolBarImages::SetTransparentColor  
 도구 모음 이미지의 투명 한 색을 설정합니다.  
  
```  
COLORREF SetTransparentColor(COLORREF clrTransparent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `clrTransparent`  
 RGB 값입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 투명색입니다.  
  
### <a name="remarks"></a>주의  
 또는 프레임 워크 호출 하는 경우 [CMFCToolBarImages::Draw](#draw), 메서드는 지정 된 색과 일치 하는 모든 픽셀을 그리지 않습니다 `clrTransparent`합니다.  
  
##  <a name="updateimage"></a>CMFCToolBarImages::UpdateImage  
 비트맵에서 도구 모음 사용자 지정 이미지를 업데이트합니다.  
  
```  
BOOL UpdateImage(
    int iImage,  
    HBITMAP hbmp);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iImage`  
 업데이트할 이미지의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `hbmp`  
 이미지를 업데이트 하려는 비트맵에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지는 성공적으로 업데이트 된 경우 `FALSE` 이미지 목록을 사용자 정의 또는 임시 없는 경우.  
  
##  <a name="convertto32bits"></a>CMFCToolBarImages::ConvertTo32Bits  
 변환에는 비트맵을을 32 bpp 이미지 밑줄이 그어집니다.  
  
```  
BOOL ConvertTo32Bits(COLORREF clrTransparent = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrTransparent`  
 밑줄이 그어진된 비트맵의 투명 한 색을 지정합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getbitsperpixel"></a>CMFCToolBarImages::GetBitsPerPixel  
 밑줄이 그어진된 이미지의 현재 해상도 반환합니다.  
  
```  
int GetBitsPerPixel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 총&24;bpp (픽셀당) 비트에서 밑줄이 있는 이미지의 현재 해상도 나타내는 정수 값입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="getscale"></a>CMFCToolBarImages::GetScale  
 밑줄이 그어진된 이미지의 현재 크기 조정 비율을 반환합니다.  
  
```  
double GetScale() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 비율을 나타내는 값입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="isscaled"></a>CMFCToolBarImages::IsScaled  
 여부 밑줄이 그어진된 이미지는 크기가 조정 여부를 알려 줍니다.  
  
```  
BOOL IsScaled () const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`밑줄이 그어진된 이미지 크기를 조정 하 고 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="smoothresize"></a>CMFCToolBarImages::SmoothResize  
 밑줄이 그어진된 이미지를 원활 하 게 크기가 조정 됩니다.  
  
```  
BOOL SmoothResize(double dblImageScale);
```  
  
### <a name="parameters"></a>매개 변수  
 `dblImageScale`  
 크기 조정 비율입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`크기 조정 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton 클래스](../../mfc/reference/cmfctoolbarbutton-class.md)

