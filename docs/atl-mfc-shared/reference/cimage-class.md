---
title: "CImage 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
dev_langs: C++
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2720fb2b1e558b564615e1589735fe84688374b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cimage-class"></a>CImage 클래스
`CImage`향상 된 비트맵 지원, 로드 및 이미지를 JPEG, GIF, BMP, 및 PNG 이동식 네트워크 그래픽 () 형식으로 저장 하는 기능을 포함 하 여 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CImage
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CImage::CImage](#cimage)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CImage::AlphaBlend](#alphablend)|투명 하 게 또는 반투명 픽셀로 있는 비트맵을 표시 합니다.|  
|[CImage::Attach](#attach)|연결 된 `HBITMAP` 에 `CImage` 개체입니다. 비 DIB 섹션 비트맵 또는 DIB 섹션 비트맵과 함께 사용할 수 있습니다.|  
|[CImage::BitBlt](#bitblt)|이 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사합니다.|  
|[CImage::Create](#create)|DIB 섹션 비트맵을 만들고에 이전에 생성 된 연결 `CImage` 개체입니다.|  
|[CImage::CreateEx](#createex)|추가 매개 변수) (사용 하 여 DIB 섹션 비트맵을 만들고이를 이전에 생성 된 연결 `CImage` 개체입니다.|  
|[CImage::Destroy](#destroy)|비트맵을 분리는 `CImage` 개체 하 고 비트맵을 제거 합니다.|  
|[CImage::Detach](#detach)|비트맵을 분리 한 `CImage` 개체입니다.|  
|[CImage::Draw](#draw)|소스 사각형에서 대상 사각형으로 비트맵을 복사합니다. **그리기** 또는 확장 하 고, 필요한 경우 대상 사각형의 크기에 맞게 비트맵을 압축 하 고, 알파 혼합 및 투명 한 색을 처리 합니다.|  
|[CImage::GetBits](#getbits)|비트맵의 실제 픽셀 값에 대 한 포인터를 검색합니다.|  
|[CImage::GetBPP](#getbpp)|픽셀 당 비트를 검색합니다.|  
|[CImage::GetColorTable](#getcolortable)|색상표에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색 합니다.|  
|[CImage::GetDC](#getdc)|현재 비트맵을 선택 하는 장치 컨텍스트를 검색 합니다.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 보려면을 찾습니다.|  
|[CImage::GetHeight](#getheight)|현재 픽셀의 이미지의 높이 검색합니다.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 보려면을 찾습니다.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|색상표에 있는 항목의 최대 수를 검색 합니다.|  
|[CImage::GetPitch](#getpitch)|현재 이미지 (바이트)에서의 피치를 검색합니다.|  
|[CImage::GetPixel](#getpixel)|지정 된 픽셀의 색을 검색 *x* 및 *y*합니다.|  
|[CImage::GetPixelAddress](#getpixeladdress)|지정된 된 픽셀의 주소를 검색 합니다.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|색상표에서 투명 한 색의 위치를 검색합니다.|  
|[CImage::GetWidth](#getwidth)|현재 픽셀의 이미지의 너비를 검색합니다.|  
|[CImage::IsDIBSection](#isdibsection)|연결 된 비트맵 DIB 섹션 인지 여부를 확인 합니다.|  
|[CImage::IsIndexed](#isindexed)|비트맵의 색 인덱싱된 팔레트에 매핑되는 것을 나타냅니다.|  
|[CImage::IsNull](#isnull)|소스 비트맵 현재 로드 된 경우를 나타냅니다.|  
|[CImage::IsTransparencySupported](#istransparencysupported)|응용 프로그램 투명 한 비트맵 지원 여부 및 Windows 2000 이상 컴파일된 나타냅니다.|  
|[CImage::Load](#load)|지정된 된 파일에서 이미지를 로드합니다.|  
|[CImage::LoadFromResource](#loadfromresource)|지정된 된 리소스에서 이미지를 로드합니다.|  
|[CImage::MaskBlt](#maskblt)|지정 된 마스크 및 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.|  
|[CImage::PlgBlt](#plgblt)|대상 장치 컨텍스트에 평행 사변형에 원본 장치 컨텍스트의 사각형에서 비트 블록 전송을 수행합니다.|  
|[CImage::ReleaseDC](#releasedc)|사용 하 여 검색 된 장치 컨텍스트를 해제 [CImage::GetDC](#getdc)합니다.|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI +에서 사용 하는 리소스를 해제 합니다. 전역에서 만든 리소스를 호출 해야 `CImage` 개체입니다.|  
|[CImage::Save](#save)|지정된 된 형식으로 이미지를 저장합니다. **저장** 이미지 옵션을 지정할 수 없습니다.|  
|[CImage::SetColorTable](#setcolortable)|빨간색, 녹색, 파란색 RGB 설정) 색상 DIB 섹션의 색상표에 있는 항목의 범위에는 값입니다.|  
|[CImage::SetPixel](#setpixel)|지정된 된 색을 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|색 색상표에서 지정된 된 인덱스에 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetPixelRGB](#setpixelrgb)|지정한 빨강, 녹색, 파란색 (RGB) 값으로 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetTransparentColor](#settransparentcolor)|투명 하 게 처리 되도록 하려면 색의 인덱스를 설정 합니다. 한 가지 색 으로만 색상표에서 투명 하 게 될 수 있습니다.|  
|[CImage::StretchBlt](#stretchblt)|소스 사각형에서 필요한 경우 대상 사각형의 크기에 맞게 비트맵을 늘이거나 대상 사각형으로 비트맵을 복사 합니다.|  
|[CImage::TransparentBlt](#transparentblt)|이 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 투명 한 색을 사용 하 여 비트맵을 복사합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HBITMAP CImage::operator](#operator_hbitmap)|에 연결 된 Windows 핸들을 반환 된 `CImage` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CImage`비트맵 또는 부정은 어느 장치 독립적 비트맵 (DIB) 섹션을 사용 합니다. 사용할 수 있습니다 [만들기](#create) 또는 [CImage::Load](#load) DIB 섹션만 사용 합니다. 비 DIB 섹션 비트맵을 연결할 수 있습니다는 `CImage` 개체 사용 하 여 [연결](#attach), 하지만 다음 사용할 수 없는 있습니다 `CImage` DIB 섹션 비트맵만을 지원 하는 메서드:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 연결 된 비트맵 DIB 섹션 인지를 확인 하려면 호출 [IsDibSection](#isdibsection)**합니다.**  
  
> [!NOTE]
> **참고** 에서 Visual Studio.NET 2003에서이 클래스의 숫자의 수를 유지 `CImage` 생성 된 개체입니다. 횟수가 0이 되 때마다 **수가** GDI +에서 사용 하는 리소스를 해제 하기 위해 자동으로 호출 됩니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 제대로 소멸 있는지 **수가** 에서 호출 하지 않으면 `DllMain`합니다.  
  
> [!NOTE]
>  사용 하 여 전역 `CImage` 개체를 DLL에서 권장 되지 않습니다. 전역 사용 해야 할 경우 `CImage` dll로 호출 개체 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 하는 리소스를 해제 합니다.  
  
 `CImage`새 선택할 수 없는 [CDC](../../mfc/reference/cdc-class.md)합니다. `CImage`자체 만듭니다 **HDC** 이미지에 대 한 합니다. 때문에 프로그램 `HBITMAP` 하나에 선택할 수 있습니다 **HDC** 한 번에는 `HBITMAP` 연관는 `CImage` 다른 파티션으로 선택할 수 없습니다 **HDC**합니다. 필요한 경우는 `CDC`, 검색 된 **HDC** 에서 `CImage` 되 고 나면 [CDC::FromHandle] (... /.. /mfc/reference/cdc-class.md#cdc__fromhandle 합니다.  
  
## <a name="example"></a>예  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 사용 하는 경우 `CImage` MFC 프로젝트를 프로젝트에는 멤버 함수에 대 한 포인터를 기대 사항을 유의 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체입니다. 사용 하려는 경우 `CImage` 이러한 함수 처럼 [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)를 사용 하 여 [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), 전달 프로그램 `CImage` `HBITMAP`, 반환 된 를사용하여`CBitmap*`.  

  
## <a name="example"></a>예  
```cpp  
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
  UNREFERENCED_PARAMETER(nFlags);

  CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
  m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
  ClientToScreen(&point);
  m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x, 
  point.y, this);
}
```  

  
 통해 `CImage`, DIB 섹션의 실제 비트에 액세스할 수 있습니다. 사용할 수는 `CImage` Win32 HBITMAP 또는 DIB 섹션 이전에 사용한 모든 위치 개체입니다.  
  
> [!NOTE]
>  다음 `CImage` 메서드 사용에 대 한 제한이 있습니다.  
  
|메서드|제한|  
|------------|----------------|  
|[PlgBlt](#plgblt)|만 Windows NT 4.0 이상 작동 합니다. 이상 Windows 95/98에서 실행 중인 응용 프로그램에서 작동 하지 않습니다.|  
|[MaskBlt](#maskblt)|만 Windows NT 4.0 이상 작동 합니다. 이상 Windows 95/98에서 실행 중인 응용 프로그램에서 작동 하지 않습니다.|  
|[로드](#alphablend)|Windows 2000, Windows 98 및 이상 시스템에서 작동 합니다.|  
|[지연 해야](#transparentblt)|Windows 2000, Windows 98 및 이상 시스템에서 작동 합니다.|  
|[그리기](#draw)|Windows 2000, Windows 98 및 이후 시스템과 상호 투명도 지원합니다.|  
  
 사용할 수 있습니다 `CImage` MFC 또는 ATL.에서  
  
> [!NOTE]
>  사용 하 여 프로젝트를 만들 때 `CImage`를 정의 해야 `CString` 포함 하기 전에 `atlimage.h`합니다. 프로젝트에서 ATL 없이 MFC 사용 하는 경우 포함 `atlstr.h` 포함 하기 전에 `atlimage.h`합니다. 프로젝트에서 MFC (또는 ATL 프로젝트 MFC 지 원하는 경우)을 사용 하는 경우 포함 `afxstr.h` 포함 하기 전에 `atlimage.h`합니다.  
>   
>  마찬가지로, 포함 해야 `atlimage.h` 포함 하기 전에 `atlimpl.cpp`합니다. 이 수행 하기 쉽게 포함 `atlimage.h` 에 프로그램 `stdafx.h`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlimage.h  
  
##  <a name="alphablend"></a>CImage::AlphaBlend  
 투명 하 게 또는 반투명 픽셀로 있는 비트맵을 표시 합니다.  
  
```
BOOL AlphaBlend(
 HDC hDestDC,
 int xDest,
 int yDest,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
 HDC hDestDC,
 const POINT& pointDest,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 BYTE bSrcAlpha = 0xff,
 BYTE bBlendOp = AC_SRC_OVER);
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 장치 컨텍스트에 대 한 핸들입니다.  
  
 `xDest`  
 x-좌표 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y-좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 *bSrcAlpha*  
 전체 소스 비트맵에 사용할 수는 알파 투명도 값입니다. 기본 0xff (255) 이미지는 불투명 픽셀당 알파 값만을 사용 하도록 한다고 가정 합니다.  
  
 `bBlendOp`  
 원본 및 대상 비트맵, 전체 소스 비트맵 및 소스 비트맵에 대 한 형식 정보에 적용 될 전역 알파 값에 대 한 알파 혼합 함수입니다. 원본 및 대상 blend 함수는 현재 제한 **AC_SRC_OVER**합니다.  
  
 `pointDest`  
 에 대 한 참조는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
 `nDestWidth`  
 대상 사각형의 논리 단위로 너비입니다.  
  
 `nDestHeight`  
 대상 사각형의 논리 단위에서 높이입니다.  
  
 `xSrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `nSrcWidth`  
 논리 단위를 소스 사각형의 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위에서 높이입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조, 대상을 식별 합니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 원본을 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 알파 혼합 비트맵 픽셀 단위로에서 색 혼합을 지원 합니다.  
  
 때 `bBlendOp` 기본값인으로 설정 되어 **AC_SRC_OVER**, 소스 비트맵 소스 픽셀의 알파 값을 기반으로 대상 비트맵을 통해 배치 됩니다.  

##  <a name="attach"></a>CImage::Attach  
 연결 `hBitmap` 에 `CImage` 개체입니다.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hBitmap`  
 에 대 한 핸들은 `HBITMAP`합니다.  
  
 *eOrientation*  
 비트맵의 방향을 지정합니다. 다음 중 하나일 수 있습니다.  
  
- **DIBOR_DEFAULT** 방향으로 비트맵의 운영 체제에 의해 결정 됩니다. 그러나이 없을 수 있습니다 항상 의도 한 결과 모든 운영 체제에서. 이 대 한 자세한 내용은 다음 기술 자료 문서를 참조 하십시오. ( **Q186586**): PRB: getobject () 항상 반환 양의 높이 대 한 DIB 섹션.  
  
- **DIBOR_BOTTOMUP** 줄 비트맵의 역순으로 되어 있습니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 끝 부분에서 포인터를 반환할 및 [CImage::GetPitch](#getpitch) 음수 값이 반환 되도록 합니다.  
  
- **DIBOR_TOPDOWN** 비트맵 선은 위에서 아래 순입니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 첫 번째 바이트에 대 한 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 으로 양의 숫자를 반환 하 합니다.  
  
### <a name="remarks"></a>설명  
 비트맵 아닌 DIB 섹션 비트맵 또는 DIB 섹션 비트맵 수 있습니다. 참조 [IsDIBSection](#isdibsection) DIB 에서만 사용할 수 있는 메서드의 목록에 대 한 비트맵 섹션.  
  
##  <a name="bitblt"></a>CImage::BitBlt  
 이 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사합니다.  
  
```
BOOL BitBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 const POINT& pointDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const POINT& pointSrc,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 **HDC**합니다.  
  
 `xDest`  
 대상 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `yDest`  
 대상 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `dwROP`  
 수행할 래스터 연산을 합니다. 래스터 작업 코드 (현재 선택 된 브러시에 의해 정의 됨) 처럼 대상 만들기 위해 원본, 대상 및 패턴의 비트를 결합 하는 방법에 정의 합니다. 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) 다른 래스터 연산을 코드 목록과 해당 설명을 보려면 Windows sdk에서입니다.  
  
 `pointDest`  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `nDestWidth`  
 대상 사각형의 논리 단위로 너비입니다.  
  
 `nDestHeight`  
 대상 사각형의 논리 단위에서 높이입니다.  
  
 `xSrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `rectDest`  
 A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 대상 사각형을 나타내는 구조입니다.  
  
 `pointSrc`  
 A **지점** 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) Windows sdk에서입니다.  
  
##  <a name="cimage"></a>CImage::CImage  
 `CImage` 개체를 생성합니다.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>설명  
 개체를 생성 한 후 호출 [만들기](#create), [부하](#load), [LoadFromResource](#loadfromresource), 또는 [연결](#attach) 비트맵 개체에 연결 합니다.  
  
 **참고** Nvisual Studio에서는이 클래스의 숫자의 수를 유지 `CImage` 생성 된 개체입니다. 횟수가 0이 되 때마다 **수가** GDI +에서 사용 하는 리소스를 해제 하기 위해 자동으로 호출 됩니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 제대로 소멸 있는지 **수가** DllMain에서 호출 되지 않습니다.  
  
 사용 하 여 전역 `CImage` 개체를 DLL에서 권장 되지 않습니다. 전역 사용 해야 할 경우 `CImage` dll로 호출 개체 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 하는 리소스를 해제 합니다.  
  
##  <a name="create"></a>CImage::Create  
 만듭니다는 `CImage` 비트맵을 연결 하는 이전에 생성 된 `CImage` 개체입니다.  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 너비는 `CImage` 비트맵 (픽셀)에서입니다.  
  
 `nHeight`  
 높이 `CImage` 비트맵 (픽셀)에서입니다. 경우 `nHeight` 가 비트맵 상향식 DIB 이며 원점은 왼쪽된 아래 모서리에는 양수입니다. 경우 `nHeight` 음수인 경우 비트맵은 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
 `nBPP`  
 비트맵의 픽셀 당 비트의 번호입니다. 일반적으로 4, 8, 16, 24 또는 32입니다. 단색 비트맵 또는 마스크에 대 한 1을 수 있습니다.  
  
 `dwFlags`  
 Bitmap 개체 알파 채널이 있는지 여부를 지정 합니다. 0 개 이상의 다음 값의 조합 될 수 있습니다.  
  
- **createAlphaChannel** 경우에 사용할 수 있습니다 `nBPP` 는 32, 및 `eCompression` 은 **BI_RGB**합니다. 를 지정 하는 경우 만들어진된 이미지에 알파 (투명도) 값 (영숫자가 아닌 32 비트 이미지에 사용 되지 않는) 각 픽셀의 네 번째 바이트에 저장 된 각 픽셀에 대 한 합니다. 호출할 때이 알파 채널이 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.  
  
> [!NOTE]
>  에 대 한 호출에서 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 알파 자동으로 대상으로 혼합 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="createex"></a>CImage::CreateEx  
 만듭니다는 `CImage` 비트맵을 연결 하는 이전에 생성 된 `CImage` 개체입니다.  
  
```
BOOL CreateEx(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD eCompression,
 const DWORD* pdwBitmasks = NULL,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 너비는 `CImage` 비트맵 (픽셀)에서입니다.  
  
 `nHeight`  
 높이 `CImage` 비트맵 (픽셀)에서입니다. 경우 `nHeight` 가 비트맵 상향식 DIB 이며 원점은 왼쪽된 아래 모서리에는 양수입니다. 경우 `nHeight` 음수인 경우 비트맵은 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
 `nBPP`  
 비트맵의 픽셀 당 비트의 번호입니다. 일반적으로 4, 8, 16, 24 또는 32입니다. 단색 비트맵 또는 마스크에 대 한 1을 수 있습니다.  
  
 `eCompression`  
 (위에서 아래로 Dib를 압축할 수 없습니다.) 압축 된 상향식 비트맵에 대 한 압축 유형을 지정 합니다. 다음 값 중 하나입니다.  
  
- **BI_RGB** 형식이 압축 되지 않습니다. 호출할 때이 값을 지정 하 `CImage::CreateEx` 호출과 같습니다 `CImage::Create`합니다.  
  
- **BI_BITFIELDS** 형식은 압축 된 고 색 테이블은 3 개의 이루어져 `DWORD` 빨간색으로 지정 하는 색 마스크, 녹색 및 파랑 구성 요소의 시작 각각 각 픽셀의 합니다. 16 및 32 bpp 비트맵와 함께 사용할 경우에 유효 합니다.  
  
 *pdwBitfields*  
 경우에 사용 `eCompression` 로 설정 된 **BI_BITFIELDS**, 그렇지 않으면 이어야 합니다 **NULL**합니다. 세 개인 배열에 대 한 포인터 `DWORD` 빨강, 비트를 각 픽셀의 사용은 지정 하는 비트 마스크 녹색, 표시 되는 색의 구성 요소는 각각 및 파랑입니다. 비트 필드에 대 한 제한 사항에 대 한 자세한 내용은 참조 하십시오. [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) Windows sdk에서입니다.  
  
 `dwFlags`  
 Bitmap 개체 알파 채널이 있는지 여부를 지정 합니다. 0 개 이상의 다음 값의 조합 될 수 있습니다.  
  
- **createAlphaChannel** 경우에 사용할 수 있습니다 `nBPP` 는 32, 및 `eCompression` 은 **BI_RGB**합니다. 를 지정 하는 경우 만들어진된 이미지에 알파 (투명도) 값 (영숫자가 아닌 32 비트 이미지에 사용 되지 않는) 각 픽셀의 네 번째 바이트에 저장 된 각 픽셀에 대 한 합니다. 호출할 때이 알파 채널이 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.  
  
    > [!NOTE]
    >  에 대 한 호출에서 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 알파 자동으로 대상으로 혼합 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 성공 하는 경우. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="example"></a>예  
 다음 예제에는 16 비트를 사용 하 여 각 픽셀을 인코딩하는 데 100 x 100 픽셀 비트맵을 만듭니다. 지정된 된 16 비트 픽셀 0-3 비트 빨강 구성 요소를 인코딩하, 4-7 비트 녹색, 인코딩 및 8-11 비트 인코딩 파랑 합니다. 나머지 4 비트가 사용 되지 않습니다.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>CImage::Destroy  
 비트맵을 분리는 `CImage` 개체 하 고 비트맵을 제거 합니다.  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>CImage::Detach  
 비트맵을 분리 한 `CImage` 개체입니다.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 분리 비트맵에 대 한 핸들 또는 **NULL** 비트맵이 없습니다 연결 된 경우.  
  
##  <a name="draw"></a>CImage::Draw  
 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사합니다.  
  
```
BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight) const throw();

BOOL Draw(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc) const throw();

BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest) const throw();

BOOL Draw(
 HDC hDestDC,
 const POINT& pointDest) const throw();

BOOL Draw(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight) const throw();

BOOL Draw(
 HDC hDestDC,
 const RECT& rectDest) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 장치 컨텍스트에 대 한 핸들입니다.  
  
 `xDest`  
 x-좌표 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y-좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 대상 사각형의 논리 단위로 너비입니다.  
  
 `nDestHeight`  
 대상 사각형의 논리 단위에서 높이입니다.  
  
 `xSrc`  
 x-좌표 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y-좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 논리 단위를 소스 사각형의 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위에서 높이입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조, 대상을 식별 합니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 원본을 식별 합니다.  
  
 `pointDest`  
 에 대 한 참조는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 **그리기** 와 동일한 작업을 수행 [StretchBlt](#stretchblt)이미지 투명색 또는 알파 채널이 포함 되어 있지 않으면입니다. 이 경우 **그리기** 으로 동일한 작업을 수행 [지연 해야](#transparentblt) 또는 [로드](#alphablend) 필요에 따라 합니다.  
  
 버전에 대 한 **그리기** 소스 사각형을 지정 하지 않으면, 전체 원본 이미지의 크기는 기본값입니다. 버전에 대 한 **그리기** 대상 사각형에 대 한 크기를 지정 하지 않는, 기본 및 확장 하지 않는 원본 이미지의 크기는 또는 발생을 축소 합니다.  
  
##  <a name="getbits"></a>CImage::GetBits  
 비트맵의 각된 픽셀의 실제 비트 값에 대 한 포인터를 검색합니다.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>반환 값  
 비트맵 버퍼에 대 한 포인터입니다. 비트맵 상향식 DIB 이면 포인터가 가리키는 버퍼의 끝을 부분입니다. 이면 비트맵 상-DIB 버퍼의 첫 번째 바이트를 가리키는 포인터입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 값과 함께이 포인터를 사용 하 여 [GetPitch](#getpitch)를 찾아 하 고 개별 픽셀 이미지에서 변경할 수 있습니다.  
  
> [!NOTE]
>  이 방법은 지원만 DIB 섹션 비트맵; 따라서의 픽셀을 액세스 하는 `CImage` DIB 섹션의 픽셀을 동일한 동일한 방식으로 개체입니다. 반환된 된 포인터 위치 (0, 0)에 있는 픽셀을 가리킵니다.  
  
##  <a name="getbpp"></a>CImage::GetBPP  
 픽셀 당 비트 값을 검색합니다.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 당 비트 수입니다.  
  
### <a name="remarks"></a>설명  
 이 값 각 픽셀을 정의 하는 비트 수와 비트맵에서 색의 최대 수를 결정 합니다.  
  
 1, 4, 8, 16, 24 또는 32 비트 / 픽셀 일반적으로 합니다. 참조는 **biBitCount** 소속 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 이 값에 대 한 자세한 내용은 Windows sdk입니다.  
  
##  <a name="getcolortable"></a>CImage::GetColorTable  
 DIB 섹션의 팔레트에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색 합니다.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iFirstColor`  
 색 테이블을 가져오려는 첫 번째 항목의 인덱스입니다.  
  
 `nColors`  
 검색할 색 테이블 항목의 수입니다.  
  
 `prgbColors`  
 배열에 대 한 포인터 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 색을 검색 하려면 구조 테이블 항목입니다.  
  
##  <a name="getdc"></a>CImage::GetDC  
 현재에 선택한 이미지에 있는 장치 컨텍스트를 검색 합니다.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 장치 컨텍스트에 대한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 각 호출에 대 한 `GetDC`, 한 후속 호출에 있어야 [ReleaseDC](#releasedc)합니다.  
  
##  <a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
 이미지 저장에 사용할 수 있는 이미지 형식을 찾습니다.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>매개 변수  
 *strExporters*  
 에 대 한 참조는 **CSimpleString** 개체입니다. 참조 **주의** 자세한 정보에 대 한 합니다.  
  
 `aguidFileTypes`  
 문자열에는 파일 형식 중 하나에 해당 하는 각 요소와 배열 Guid입니다. 예제에서 `pszAllFilesDescription` 아래 `aguidFileTypes`[0]은 `GUID_NULL` 나머지 배열 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식 및 합니다.  
  
> [!NOTE]
>  상수 목록은 전체 참조 **이미지 파일 형식 상수** Windows sdk에서입니다.  
  
 `pszAllFilesDescription`  
 이 매개 변수가 없으면 **NULL**, 필터 문자열 목록 맨 앞에 하나의 추가 필터를 갖습니다. 이 필터의 현재 값을 갖습니다 `pszAllFilesDescription` 해당 설명에 대 한 하 고 목록에서 다른 내보내기에서에서 지 원하는 모든 확장명의 파일을 허용 합니다.  
  
 예:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그 됩니다.  
  
- **excludeGIF** = 0x01 제외 GIF 파일입니다.  
  
- **excludeBMP** = 0x02 제외 BMP (Windows 비트맵) 파일입니다.  
  
- **excludeEMF** = 0x04 제외 EMF (확장 메타 파일) 파일입니다.  
  
- **excludeWMF** = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.  
  
- **excludeJPEG** = 0x10 제외 JPEG 파일입니다.  
  
- **excludePNG** = 0x20 제외 하는 PNG 파일입니다.  
  
- **excludeTIFF** = 0x40 제외 TIFF 파일입니다.  
  
- **excludeIcon** = 0x80 제외 ICO (Windows 아이콘) 파일입니다.  
  
- **excludeOther** = 0x80000000 위에 나열 되지 않은 다른 모든 파일 형식을 제외 합니다.  
  
- **excludeDefaultLoad** = 부하, 형식이 기본적으로 포함 된 모든 파일에 대 한 0  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** 저장에 대 한 이러한 파일은 기본적으로 제외 일반적으로 특별 한 요구 사항이 했기 때문에 있습니다.  
  
 `chSeparator`  
 이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 자세한 정보에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
### <a name="remarks"></a>설명  
 MFC 프로그램에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 다른 이름으로 저장 대화 상자에서 사용할 수 있는 이미지의 파일 확장명을 노출 하는 개체 형식을 지정 합니다.  
  
 매개 변수 *strExporter* 형식은 같습니다.  
  
 파일 description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*.ext1 &#124;... 파일 설명  *n* &#124;\*합니다. ext  *n* &#124; &#124;  
  
 여기서 ' &#124;'에서 지정 하는 구분 기호 `chSeparator`합니다. 예:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 기본 구분 기호를 사용 하 여 ' &#124;'에 MFC이이 문자열을 전달 하는 경우 `CFileDialog` 개체입니다. 일반 파일 저장 대화 상자에이 문자열을 전달 하는 경우 null 구분 기호 '\0'를 사용 합니다.  
  
##  <a name="getheight"></a>CImage::GetHeight  
 픽셀 이미지의 높이 검색합니다.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 이미지의 높이입니다.  
  
##  <a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
 이미지를 로드 하는 것에 대 한 이미지 형식을 사용할 수 있는 찾습니다.  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>매개 변수  
 *strImporters*  
 에 대 한 참조는 **CSimpleString** 개체입니다. 참조 **주의** 자세한 정보에 대 한 합니다.  
  
 `aguidFileTypes`  
 문자열에는 파일 형식 중 하나에 해당 하는 각 요소와 배열 Guid입니다. 예제에서 `pszAllFilesDescription` 아래 `aguidFileTypes`[0]은 `GUID_NULL` 나머지 배열 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식입니다.  
  
> [!NOTE]
>  상수 목록은 전체 참조 **이미지 파일 형식 상수** Windows sdk에서입니다.  
  
 `pszAllFilesDescription`  
 이 매개 변수가 없으면 **NULL**, 필터 문자열 목록 맨 앞에 하나의 추가 필터를 갖습니다. 이 필터의 현재 값을 갖습니다 `pszAllFilesDescription` 해당 설명에 대 한 하 고 목록에서 다른 내보내기에서에서 지 원하는 모든 확장명의 파일을 허용 합니다.  
  
 예:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그 됩니다.  
  
- **excludeGIF** = 0x01 제외 GIF 파일입니다.  
  
- **excludeBMP** = 0x02 제외 BMP (Windows 비트맵) 파일입니다.  
  
- **excludeEMF** = 0x04 제외 EMF (확장 메타 파일) 파일입니다.  
  
- **excludeWMF** = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.  
  
- **excludeJPEG** = 0x10 제외 JPEG 파일입니다.  
  
- **excludePNG** = 0x20 제외 하는 PNG 파일입니다.  
  
- **excludeTIFF** = 0x40 제외 TIFF 파일입니다.  
  
- **excludeIcon** = 0x80 제외 ICO (Windows 아이콘) 파일입니다.  
  
- **excludeOther** = 0x80000000 위에 나열 되지 않은 다른 모든 파일 형식을 제외 합니다.  
  
- **excludeDefaultLoad** = 부하, 형식이 기본적으로 포함 된 모든 파일에 대 한 0  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF** 저장에 대 한 이러한 파일은 기본적으로 제외 일반적으로 특별 한 요구 사항이 했기 때문에 있습니다.  
  
 `chSeparator`  
 이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 자세한 정보에 대 한 합니다.  
  
### <a name="remarks"></a>설명  
 MFC 프로그램에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 의 사용 가능한 이미지의 파일 확장명을 노출 하는 개체 형식은 **파일 열기** 대화 상자.  
  
 매개 변수 *strImporter* 형식은 같습니다.  
  
 파일 description0 &#124; \*.ext0 &#124; filedescription1 &#124; \*.ext1 &#124;... 파일 설명  *n* &#124;\*합니다. ext  *n* &#124; &#124;  
  
 여기서 ' &#124;'에서 지정 하는 구분 기호 `chSeparator`합니다. 예:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 기본 구분 기호를 사용 하 여 ' &#124;'에 MFC이이 문자열을 전달 하는 경우 `CFileDialog` 개체입니다. 공용으로이 문자열을 전달 하는 경우 null 구분 기호 '\0'를 사용 하 여 **파일 열기** 대화 상자.  
  
##  <a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 색상표에 있는 항목의 최대 수를 검색 합니다.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 색상표에 있는 항목의 수입니다.  
  
### <a name="remarks"></a>설명  
 이 방법은 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="getpitch"></a>CImage::GetPitch  
 이미지의 피치를 검색합니다.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이미지의 피치 합니다. 반환 값이 음수 이면 비트맵 상향식 DIB 이며 원점은 왼쪽된 아래 모서리 합니다. 반환 값이 양수 이면 비트맵 상-DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
### <a name="remarks"></a>설명  
 피치 한 비트맵 줄의 시작 부분을 나타내는 두 개의 메모리 주소 및 다음 비트맵 줄의 시작 사이의 바이트 단위의 거리입니다. 피치, 바이트 단위로 측정 하기 때문에 이미지의 피치를 사용 하는 픽셀 형식을 확인할 수 있습니다. 피치 비트맵용으로 예약 하는 추가 메모리를 포함할 수도 있습니다.  
  
 사용 하 여 `GetPitch` 와 [GetBits](#getbits) 개별 이미지 픽셀을 찾을 수 있습니다.  
  
> [!NOTE]
>  이 방법은 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="getpixel"></a>CImage::GetPixel  
 지정 된 위치에 있는 픽셀의 색을 검색 *x* 및 *y*합니다.  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 픽셀의 x 좌표입니다.  
  
 *y*  
 픽셀의 y 좌표입니다.  
  
### <a name="return-value"></a>반환 값  
 빨간색, 녹색, 파란색 (RGB) 픽셀의 값입니다. 반환 값은 현재 클리핑 영역 외부의 픽셀 이면 **CLR_INVALID**합니다.  
  
##  <a name="getpixeladdress"></a>CImage::GetPixelAddress  
 정확한 픽셀의 주소를 검색합니다.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 픽셀의 x 좌표입니다.  
  
 *y*  
 픽셀의 y 좌표입니다.  
  
### <a name="remarks"></a>설명  
 주소는 픽셀 좌표, 비트맵 및 픽셀 당 비트의 피치에 따라 결정 됩니다.  
  
 픽셀 당 8 비트 보다 적은 형식에 대 한이 메서드는 픽셀을 포함 하는 바이트의 주소를 반환 합니다. 예를 들어 이미지 형식 픽셀 당 4 비트 `GetPixelAddress` 반환 된 바이트에서 첫 번째 픽셀의 주소는 바이트 당 2 픽셀에 대 한 계산 해야 합니다.  
  
> [!NOTE]
>  이 방법은 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 색상표에서 투명 한 색의 인덱싱된 위치를 검색합니다.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 투명 한 색의 인덱스입니다.  
  
##  <a name="getwidth"></a>CImage::GetWidth  
 픽셀 이미지의 너비를 검색합니다.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 비트맵의 너비입니다.  
  
##  <a name="isdibsection"></a>CImage::IsDIBSection  
 연결 된 비트맵 DIB 섹션 인지 여부를 확인 합니다.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** DIB 섹션 경우 연결 된 비트맵입니다. 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>설명  
 비트맵이 DIB 섹션에서 다음을 사용할 수 없습니다 `CImage` DIB 섹션 비트맵만을 지원 하는 메서드:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>CImage::IsIndexed  
 비트맵의 픽셀 색 팔레트에 매핑되는 여부를 결정 합니다.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 인덱싱된 되지 않으면 **false**합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 **true** 비트맵 8 비트 일 경우에 (256 색)이 있습니다.  
  
> [!NOTE]
>  이 방법은 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="isnull"></a>CImage::IsNull  
 비트맵 현재 로드 된 경우를 결정 합니다.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 **True** 비트맵 있지 않으면 현재 로드 된 경우 **False**합니다.  
  
##  <a name="istransparencysupported"></a>CImage::IsTransparencySupported  
 응용 프로그램 투명 한 비트맵 지원 여부 및 Windows 2000 이상 컴파일된 나타냅니다.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 플랫폼에서 투명도 지원 하는 경우에 0이 아닙니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 0이 아닌 경우 및 투명도 지원 되는 경우에 대 한 호출 [로드](#alphablend), [지연 해야](#transparentblt), 또는 [그리기](#draw) 투명 색상을 처리 합니다.  
  
 응용 프로그램이 Windows 2000 또는 Windows 98 이전 운영 체제와 함께 사용할 컴파일될, 하는 경우이 메서드는 0, 최신 운영 체제에도 항상 반환 됩니다.  
  

##  <a name="load"></a>CImage::Load  
 이미지를 로드합니다.  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pszFileName`  
 로드할 이미지 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `pStream`  
 로드할 이미지 파일의 이름을 포함 하는 스트림에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 이미지를 로드 *pszFileName* 또는 `pStream`합니다.  
  
 올바른 이미지 유형은 BMP, GIF, JPEG, PNG 및 TIFF입니다.  
  
##  <a name="loadfromresource"></a>CImage::LoadFromResource  
 이미지를 로드 하는 `BITMAP` 리소스입니다.  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstance`  
 로드할 이미지를 포함 하는 모듈의 인스턴스를 처리 합니다.  
  
 `pszResourceName`  
 로드할 이미지를 포함 하는 리소스의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nIDResource`  
 로드할 리소스의 ID입니다.  
  
### <a name="remarks"></a>설명  
 리소스 형식 이어야 합니다 `BITMAP`합니다.  
  
##  <a name="maskblt"></a>CImage::MaskBlt  
 지정 된 마스크 및 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.  
  
```
BOOL MaskBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 HBITMAP hbmMask,
 int xMask,
 int yMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const POINT& pointSrc,
 HBITMAP hbmMask,
 const POINT& pointMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 HBITMAP hbmMask,
 DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
 HDC hDestDC,
 const POINT& pointDest,
 HBITMAP hbmMask,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 인 실행 파일 리소스를 포함 하는 모듈에 대 한 핸들입니다.  
  
 `xDest`  
 x-좌표 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y-좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형 및 소스 비트맵의 너비입니다.  
  
 `nDestHeight`  
 대상 사각형 및 소스 비트맵의 논리 단위에서 높이입니다.  
  
 `xSrc`  
 원본 비트맵의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 원본 비트맵의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `hbmMask`  
 소스 장치 컨텍스트에 색 비트맵 함께 단색 마스크 비트맵에 대 한 핸들입니다.  
  
 `xMask`  
 로 지정 된 마스크 비트맵에 대 한 가로 픽셀 오프셋의 `hbmMask` 매개 변수입니다.  
  
 `yMask`  
 로 지정 된 마스크 비트맵에 대 한 세로 픽셀 오프셋의 `hbmMask` 매개 변수입니다.  
  
 `dwROP`  
 한 원본 및 대상 데이터를 제어 하는 메서드에서 사용 하는 삼항 래스터 연산 코드 둘 다 전경색과 배경색을 지정 합니다. 배경 래스터 연산 코드는이 값;의 상위 단어의 상위 바이트에 저장 됩니다. 전경 래스터 연산 코드는이 값;의 상위 단어의 낮은 순서 바이트에 저장 됩니다. 이 값의 하위 단어는 무시 되 고 0 이어야 합니다. 전경색과 배경색이 메서드의 컨텍스트에서 논의 알려면 `MaskBlt` Windows sdk에서입니다. 목록이 공통 래스터 연산 코드에 대 한 참조 `BitBlt` Windows sdk에서입니다.  
  
 `rectDest`  
 에 대 한 참조는 `RECT` 구조, 대상을 식별 합니다.  
  
 `pointSrc`  
 A `POINT` 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `pointMask`  
 A **지점** 마스크 비트맵의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `pointDest`  
 에 대 한 참조는 **지점** 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 Windows NT 4.0 이상만 해당 버전에 적용 됩니다.  
  
##  <a name="operator_hbitmap"></a>HBITMAP CImage::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CImage` 개체입니다. 이 연산자는의 직접 사용을 지원 하려면 캐스팅 연산자는 `HBITMAP` 개체입니다.  
  
##  <a name="plgblt"></a>CImage::PlgBlt  
 대상 장치 컨텍스트에 평행 사변형에 원본 장치 컨텍스트의 사각형에서 비트 블록 전송을 수행합니다.  
  
```
BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 HBITMAP hbmMask = NULL,
 int xMask = 0,
 int yMask = 0) const throw();

BOOL PlgBlt(
 HDC hDestDC,
 const POINT* pPoints,
 const RECT& rectSrc,
 HBITMAP hbmMask = NULL,
 const POINT& pointMask = CPoint(0, 0)) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 장치 컨텍스트에 대 한 핸들입니다.  
  
 *pPoints*  
 대상 평행 사변형의 세 모퉁이 식별 하는 논리에 세 개의 점 배열에 대 한 포인터입니다. 소스 사각형의 왼쪽된 위 모서리가이 배열,이 배열에 있는 두 번째 요소를 오른쪽 위 모서리 및 세 번째 데이터 요소를 왼쪽된 아래 모서리에서 첫 번째 요소와 매핑됩니다. 소스 사각형의 오른쪽 아래 모퉁이 평행 사변형에 암시적 네 번째 요소와 매핑됩니다.  
  
 `hbmMask`  
 소스 사각형의 색을 마스크 하는 데 사용 되는 선택적 흑백 비트맵에 대 한 핸들입니다.  
  
 `xSrc`  
 x-좌표 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y-좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 논리 단위를 소스 사각형의 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위에서 높이입니다.  
  
 `xMask`  
 흑백 비트맵의 왼쪽된 위 모퉁이의 x 좌표입니다.  
  
 `yMask`  
 흑백 비트맵의 왼쪽된 위 모퉁이의 y 좌표입니다.  
  
 `rectSrc`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 소스 사각형의 좌표를 지정 하는 구조입니다.  
  
 `pointMask`  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 마스크 비트맵의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우 `hbmMask` 유효한 단색 비트맵을 식별 **PlgBit** 소스 사각형의 색 데이터 비트를 마스크 하기 위해이 비트맵을 사용 합니다.  
  
 이 메서드는 Windows NT 4.0 이상만 해당 버전에 적용 됩니다. 참조 [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) 자세한 내용을 보려면 Windows sdk에서입니다.  
  
##  <a name="releasedc"></a>CImage::ReleaseDC  
 장치 컨텍스트를 해제 합니다.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>설명  
 한 번에 하나의 비트맵 장치 컨텍스트로 선택할 수 있습니다, 때문에 호출 해야 `ReleaseDC` 호출에 대해 각각 [GetDC](#getdc)합니다.  
  
##  <a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 GDI +에서 사용 하는 리소스를 해제 합니다.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 전역에 의해 할당 된 리소스를 호출 해야 합니다 `CImage` 개체입니다. 참조 [CImage::CImage](#cimage)합니다.  
  
##  <a name="save"></a>CImage::Save  
 지정 된 스트림 또는 디스크에 파일 이미지를 저장합니다.  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pStream`  
 파일 이미지 데이터를 포함 하는 COM IStream 개체에 대 한 포인터입니다.  
  
 *pszFileName*  
 이미지에 대 한 파일 이름에 대 한 포인터입니다.  
  
 `guidFileType`  
 으로 이미지를 저장할 파일 형식입니다. 다음 중 하나일 수 있습니다.  
  
- **ImageFormatBMP** 압축 되지 않은 비트맵 이미지입니다.  
  
- **ImageFormatPNG** 압축 된 이미지는 PNG 이동식 네트워크 그래픽 ().  
  
- **ImageFormatJPEG** A JPEG 압축 된 이미지입니다.  
  
- **ImageFormatGIF** A GIF 압축 된 이미지입니다.  
  
> [!NOTE]
>  상수 목록은 전체 참조 **이미지 파일 형식 상수** Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
### <a name="remarks"></a>설명  
 지정한 이름 및 유형을 사용 하 여 이미지를 저장 하려면이 함수를 호출 합니다. 경우는 `guidFileType` 매개 변수를 포함할 파일 이름 확장명에서 이미지 형식을 결정 하는 데 사용 됩니다. 확장명이 없는 제공 하는 경우 이미지 BMP 형식으로 저장 됩니다.  
  
##  <a name="setcolortable"></a>CImage::SetColorTable  
 DIB 섹션의 팔레트에서 항목의 범위에 대 한 빨간색, 녹색, 파란색 (RGB) 색 값을 설정합니다.  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iFirstColor`  
 색 테이블을 설정 하려면 첫 번째 항목의 인덱스입니다.  
  
 `nColors`  
 설정할 색 테이블 항목의 수입니다.  
  
 `prgbColors`  
 배열에 대 한 포인터 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 구조 색을 설정 하려면 테이블 항목입니다.  
  
### <a name="remarks"></a>설명  
 이 방법은 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="setpixel"></a>CImage::SetPixel  
 비트맵에서 지정 된 위치에 있는 픽셀의 색을 설정합니다.  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 설정할 픽셀의 가로 위치입니다.  
  
 *y*  
 설정할 픽셀의 세로 위치입니다.  
  
 `color`  
 픽셀 설정한 색입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 픽셀을 선택 된 클립 영역 외부에 같고 조정 하는 경우 실패 합니다.  
  
##  <a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 픽셀 색에 있는 색을 설정 `iIndex` 색상표에 있습니다.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 설정할 픽셀의 가로 위치입니다.  
  
 *y*  
 설정할 픽셀의 세로 위치입니다.  
  
 `iIndex`  
 색 색상표의 색의 인덱스입니다.  
  
##  <a name="setpixelrgb"></a>CImage::SetPixelRGB  
 로 지정 된 위치에서 설정 하는 픽셀 *x* 및 *y* 가리키는 색에 *r*, *g*, 및 *b*, 빨간색, 녹색, 파란색 (RGB) 이미지입니다.  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 설정할 픽셀의 가로 위치입니다.  
  
 *y*  
 설정할 픽셀의 세로 위치입니다.  
  
 *r*  
 빨간색의 농도 합니다.  
  
 *g*  
 녹색 색의 강도입니다.  
  
 *b*  
 파랑 색의 강도입니다.  
  
### <a name="remarks"></a>설명  
 빨간색, 녹색 및 파란색 매개 변수는 각각 0과 255 사이의 숫자 표시 합니다. 모든 세 개의 매개 변수를 0으로 설정 하면 결합 된 결과 색은 검정입니다. 세 매개 변수 모두를 255로 설정 하면 결합 된 결과 색상은 흰색입니다.  
  
##  <a name="settransparentcolor"></a>CImage::SetTransparentColor  
 투명으로 지정 된 인덱스 위치의 색을 설정합니다.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *iTransparentColor*  
 투명으로 설정 하는 색의 색상표 인덱스입니다. -1 이면 색 없음은 투명으로 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 색의 인덱스는 이전에 투명 하 게 설정 합니다.  
  
##  <a name="stretchblt"></a>CImage::StretchBlt  
 이 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사합니다.  
  
```
BOOL StretchBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 const RECT& rectDest,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 DWORD dwROP = SRCCOPY) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 장치 컨텍스트에 대 한 핸들입니다.  
  
 `xDest`  
 x-좌표 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y-좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 대상 사각형의 논리 단위로 너비입니다.  
  
 `nDestHeight`  
 대상 사각형의 논리 단위에서 높이입니다.  
  
 `dwROP`  
 수행할 래스터 연산을 합니다. 래스터 작업 코드 (현재 선택 된 브러시에 의해 정의 됨) 처럼 대상 만들기 위해 원본, 대상 및 패턴의 비트를 결합 하는 방법에 정의 합니다. 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) 다른 래스터 연산을 코드 목록과 해당 설명을 보려면 Windows sdk에서입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조, 대상을 식별 합니다.  
  
 `xSrc`  
 x-좌표 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y-좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 논리 단위를 소스 사각형의 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위에서 높이입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 원본을 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) Windows sdk에서입니다.  
  
##  <a name="transparentblt"></a>CImage::TransparentBlt  
 이 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사합니다.  
  
```
BOOL TransparentBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 const RECT& rectDest,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 int xDest,
 int yDest,
 int nDestWidth,
 int nDestHeight,
 int xSrc,
 int ySrc,
 int nSrcWidth,
 int nSrcHeight,
 UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
 HDC hDestDC,
 const RECT& rectDest,
 const RECT& rectSrc,
 UINT crTransparent = CLR_INVALID) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hDestDC`  
 대상 장치 컨텍스트에 대 한 핸들입니다.  
  
 `xDest`  
 x-좌표 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y-좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 대상 사각형의 논리 단위로 너비입니다.  
  
 `nDestHeight`  
 대상 사각형의 논리 단위에서 높이입니다.  
  
 *crTransparent*  
 소스 비트맵을 투명 하 게 처리할 색입니다. 기본적으로 **CLR_INVALID**, 현재 이미지의 투명 한 색으로 설정 된 색상을 사용 해야 함을 나타내는입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조, 대상을 식별 합니다.  
  
 `xSrc`  
 x-좌표 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y-좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 논리 단위를 소스 사각형의 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위에서 높이입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 원본을 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 성공 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 `TransparentBlt`4 비트 / 픽셀 및 픽셀 당 8 비트의 소스 비트맵에 지원 됩니다. 사용 하 여 [CImage::AlphaBlend](#alphablend) 에 투명도 사용 하 여 32 비트 / 픽셀 비트맵을 지정 합니다.  
  
  
### <a name="example"></a>예  

```cpp  
// Performs a transparent blit from the source image to the destination 
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage, 
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
  HDC hDstDC = NULL;
  BOOL bResult;

  if(pSrcImage == NULL || pDstImage == NULL)
  {
  // Invalid parameter
  return FALSE;
  }

  // Obtain a DC to the destination image
  hDstDC = pDstImage->GetDC();

  // Perform the blit
  bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

  // Release the destination DC
  pDstImage->ReleaseDC();

  return bResult;
}
```

  
## <a name="see-also"></a>참고 항목  
 [MMXSwarm 샘플](../../visual-cpp-samples.md)   
 [SimpleImage 샘플](../../visual-cpp-samples.md)   
 [장치 독립적 비트맵](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md) [장치 독립적 비트맵](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   









