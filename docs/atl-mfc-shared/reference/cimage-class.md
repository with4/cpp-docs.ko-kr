---
title: "CImage 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CImage
- ATL.CImage
- ATL::CImage
dev_langs:
- C++
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
caps.latest.revision: 20
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f74e5952401d6f9608425681cd91120b648e7b13
ms.lasthandoff: 02/24/2017

---
# <a name="cimage-class"></a>CImage 클래스
`CImage`로드 하 고 이미지를 JPEG, GIF, BMP, 및 PNG 이동식 네트워크 그래픽 () 형식으로 저장 하는 기능 등의 향상 된 비트맵 지원을 제공 합니다.  
  
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
|[CImage::AlphaBlend](#alphablend)|투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.|  
|[CImage::Attach](#attach)|연결 된 `HBITMAP` 에 `CImage` 개체입니다. 비 DIB 섹션 비트맵 또는 DIB 섹션 비트맵과 함께 사용할 수 있습니다.|  
|[CImage::BitBlt](#bitblt)|현재이 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사 합니다.|  
|[CImage::Create](#create)|DIB 섹션 비트맵을 만들고에 이전에 생성 된 연결 `CImage` 개체입니다.|  
|[CImage::CreateEx](#createex)|이전에 생성 된에 연결 합니다 (추가 매개 변수를 가진) DIB 섹션 비트맵을 만들어 `CImage` 개체입니다.|  
|[CImage::Destroy](#destroy)|비트맵을 분리는 `CImage` 개체 하 고 비트맵을 삭제 합니다.|  
|[CImage::Detach](#detach)|비트맵을 분리 한 `CImage` 개체입니다.|  
|[CImage::Draw](#draw)|소스 사각형에서 대상 사각형으로 비트맵을 복사 합니다. **그리기** 또는 확장 하 고, 필요한 경우 대상 사각형의 크기에 맞게 비트맵 압축 하 고, 투명 한 색 및 알파 혼합 처리 합니다.|  
|[CImage::GetBits](#getbits)|비트맵의 실제 픽셀 값에 대 한 포인터를 검색합니다.|  
|[CImage::GetBPP](#getbpp)|픽셀 당 비트 수를 검색합니다.|  
|[CImage::GetColorTable](#getcolortable)|색상표에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색 합니다.|  
|[CImage::GetDC](#getdc)|현재 비트맵을 선택 하는 장치 컨텍스트를 검색 합니다.|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 보려면을 찾습니다.|  
|[CImage::GetHeight](#getheight)|픽셀 단위로 현재 이미지의 높이 검색합니다.|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|사용 가능한 이미지 형식 및 해당 설명을 보려면을 찾습니다.|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|색상표에 있는 항목의 최대 수를 검색합니다.|  
|[CImage::GetPitch](#getpitch)|바이트 단위로 현재 이미지의 피치를 검색합니다.|  
|[CImage::GetPixel](#getpixel)|지정 된 픽셀의 색을 검색 *x* 및 *y*합니다.|  
|[CImage::GetPixelAddress](#getpixeladdress)|각된 픽셀의 주소를 검색합니다.|  
|[CImage::GetTransparentColor](#gettransparentcolor)|색상표에서 투명 한 색의 위치를 검색합니다.|  
|[CImage::GetWidth](#getwidth)|픽셀 단위로 현재 이미지의 너비를 검색합니다.|  
|[CImage::IsDIBSection](#isdibsection)|연결 된 비트맵이 DIB 섹션 인지 확인 합니다.|  
|[CImage::IsIndexed](#isindexed)|비트맵의 색 인덱스 된 색상표에 매핑됨을 나타냅니다.|  
|[CImage::IsNull](#isnull)|소스 비트맵 현재 로드 된 경우를 나타냅니다.|  
|[CImage::IsTransparencySupported](#istransparencysupported)|응용 프로그램이 투명 한 비트맵 지원 여부와 Windows 2000 이상 컴파일된 나타냅니다.|  
|[CImage::Load](#load)|지정된 된 파일에서 이미지를 로드합니다.|  
|[CImage::LoadFromResource](#loadfromresource)|지정된 된 리소스에서 이미지를 로드합니다.|  
|[CImage::MaskBlt](#maskblt)|지정 된 마스크와 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.|  
|[CImage::PlgBlt](#plgblt)|소스 장치 컨텍스트에의 사각형에서 대상 장치 컨텍스트의 사변형으로 비트 블록 전송을 수행합니다.|  
|[CImage::ReleaseDC](#releasedc)|사용 하 여 검색 된 장치 컨텍스트를 해제 [CImage::GetDC](#getdc)합니다.|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI +에서 사용 되는 리소스를 해제 합니다. 전역에서 만든 리소스를 호출 해야 `CImage` 개체입니다.|  
|[CImage::Save](#save)|지정된 된 형식으로 이미지를 저장합니다. **저장** 이미지 옵션을 지정할 수 없습니다.|  
|[CImage::SetColorTable](#setcolortable)|빨간색, 녹색, 파란색 RGB 설정) 색상 DIB 섹션의 색상표에 있는 항목의 범위에는 값입니다.|  
|[CImage::SetPixel](#setpixel)|지정 된 색을 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetPixelIndexed](#setpixelindexed)|색 팔레트의 지정 된 인덱스에 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetPixelRGB](#setpixelrgb)|지정한 빨강, 녹색, 파란색 (RGB) 값으로 지정된 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetTransparentColor](#settransparentcolor)|투명으로 처리 되는 색의 인덱스를 설정 합니다. 색상표에서 색만 투명 하 게 될 수 있습니다.|  
|[CImage::StretchBlt](#stretchblt)|소스 사각형에서 필요한 경우 대상 사각형의 크기에 맞게 비트맵을 늘이거나 대상 사각형으로 비트맵을 복사 합니다.|  
|[CImage::TransparentBlt](#transparentblt)|현재이 장치 컨텍스트를 소스 장치 컨텍스트에에서 투명 한 색을 사용 하 여 비트맵을 복사합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HBITMAP CImage::operator](#operator_hbitmap)|에 연결 된 창 핸들을 반환 된 `CImage` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CImage`비트맵 또는 필요는 없습니다; 두 장치 독립적 비트맵 (DIB) 섹션을 사용 합니다. 사용할 수 있습니다 [만들기](#create) 또는 [CImage::Load](#load) DIB 섹션만 사용 합니다. 비 DIB 섹션 비트맵을 연결할 수는 `CImage` 개체를 사용 하 여 [연결](#attach), 다음을 사용할 수 없다면 다음 `CImage` DIB 섹션 비트맵이 지원 되는 메서드를:  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 연결 된 비트맵 이미지를 DIB 섹션 인지를 확인 하려면 호출 [IsDibSection](#isdibsection)**합니다.**  
  
> [!NOTE]
> **참고** 에서 Visual Studio.NET 2003에서이 클래스 수가 개수를 유지 `CImage` 생성 된 개체입니다. 때마다 횟수가 0이 되 **수가** GDI +에서 사용 하는 리소스를 해제 하기 위해 자동으로 호출 합니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 제대로 소멸 하 고 **수가** 에서 호출 되지 않습니다 `DllMain`합니다.  
  
> [!NOTE]
>  사용 하 여 전역 `CImage` 개체 DLL에 권장 되지 않습니다. 전역 사용 해야 할 경우 `CImage` DLL 호출의에서 개체 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 되는 리소스를 해제 합니다.  
  
 `CImage`새로운 선택할 수 없는 [CDC](../../mfc/reference/cdc-class.md)합니다. `CImage`자체 만듭니다 **HDC** 이미지입니다. 때문에 `HBITMAP` 하나에 선택할 수 **HDC** 한 번에는 `HBITMAP` 연관는 `CImage` 다른 선택할 수 없습니다 **HDC**합니다. 필요한 경우는 `CDC`, 검색에서 **HDC** 에서 `CImage` 되 고 나면 [CDC::FromHandle] (.. /.. /mfc/reference/cdc-class.md#cdc__fromhandle 합니다.  
  
## <a name="example"></a>예제  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 사용 하는 경우 `CImage` MFC 프로젝트를 프로젝트의 멤버 함수를 예상에 대 한 포인터를 확인 한 [CBitmap](../../mfc/reference/cbitmap-class.md) 개체입니다. 사용 하려는 경우 `CImage` 이러한 함수 같은 [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)를 사용 하 여 [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle), 전달 프로그램 `CImage` `HBITMAP`를 사용 하 여 반환 된 `CBitmap*`.  

  
## <a name="example"></a>예제  
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

  
 통해 `CImage`, DIB 섹션의 실제 비트에 액세스할 수 있습니다. 사용할 수는 `CImage` Win32 HBITMAP 또는 DIB 섹션을 이전에 사용한 모든 위치 개체입니다.  
  
> [!NOTE]
>  다음 `CImage` 메서드 사용에 제한이 있습니다.  
  
|메서드|한계|  
|------------|----------------|  
|[PlgBlt](#plgblt)|Windows NT 4.0 에서만 이상으로 작동 합니다. 이상 Windows 95/98에서 실행 되는 응용 프로그램에서 작동 하지 않습니다.|  
|[MaskBlt](#maskblt)|Windows NT 4.0 에서만 이상으로 작동 합니다. 이상 Windows 95/98에서 실행 되는 응용 프로그램에서 작동 하지 않습니다.|  
|[로드](#alphablend)|Windows 2000, Windows 98 및 이후 시스템과 상호 작동 합니다.|  
|[지연 해야](#transparentblt)|Windows 2000, Windows 98 및 이후 시스템과 상호 작동 합니다.|  
|[그리기](#draw)|Windows 2000, Windows 98 및 이후 시스템과 투명도 지원합니다.|  
  
 사용할 수 있습니다 `CImage` MFC 또는 ATL.에서  
  
> [!NOTE]
>  사용 하 여 프로젝트를 만들 때 `CImage`를 정의 해야 `CString` 포함 하기 전에 `atlimage.h`합니다. 프로젝트가 MFC 없이 ATL을 사용 하는 경우 포함 `atlstr.h` 포함 하기 전에 `atlimage.h`합니다. 프로젝트에는 MFC (또는 MFC 지원을 통해 ATL 프로젝트 경우)을 사용 하는 경우 포함 `afxstr.h` 포함 하기 전에 `atlimage.h`합니다.  
>   
>  마찬가지로, 포함 해야 `atlimage.h` 포함 하기 전에 `atlimpl.cpp`합니다. 이 수행 하기 쉽게 포함 `atlimage.h` 에 프로그램 `stdafx.h`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlimage.h  
  
##  <a name="a-namealphablenda--cimagealphablend"></a><a name="alphablend"></a>CImage::AlphaBlend  
 투명 하거나 반투명 픽셀로 있는 비트맵을 표시 합니다.  
  
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
 대상 장치 컨텍스트의 핸들입니다.  
  
 `xDest`  
 X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 *bSrcAlpha*  
 전체 소스 비트맵에 사용할 수는 알파 투명도 값입니다. 기본 0xff (255) 이미지는 불투명 픽셀당 알파 값만을 사용 한다고 가정 합니다.  
  
 `bBlendOp`  
 원본 및 대상 비트맵, 전체 소스 비트맵 및 소스 비트맵에 대 한 형식 정보에 적용 될 글로벌 알파 값에 대 한 알파 혼합 함수입니다. 원본 및 대상 blend 함수는 현재 제한 **AC_SRC_OVER**합니다.  
  
 `pointDest`  
 에 대 한 참조는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형의 높이입니다.  
  
 `xSrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `nSrcWidth`  
 소스 사각형의 논리 단위로 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위로 높이입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 식별 하는 대상입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 소스를 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 알파 혼합 비트맵 픽셀 단위로에서 색 혼합을 지원 합니다.  
  
 때 `bBlendOp` 의 기본값으로 설정 되어 **AC_SRC_OVER**, 소스 비트맵의 원본 픽셀 알파 값을 기반으로 대상 비트맵을 통해 배치 됩니다.  

##  <a name="a-nameattacha--cimageattach"></a><a name="attach"></a>CImage::Attach  
 연결 `hBitmap` 에 `CImage` 개체입니다.  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hBitmap`  
 에 대 한 핸들은 `HBITMAP`합니다.  
  
 *eOrientation*  
 비트맵의 방향을 지정합니다. 다음 중 하나일 수 있습니다.  
  
- **DIBOR_DEFAULT** 방향으로 비트맵의 운영 체제에 의해 결정 됩니다. 그러나이 항상에 없는 것에서 의도 한 결과 모든 운영 체제입니다. 이 대 한 자세한 내용은 다음 기술 자료 문서를 참조 하십시오. ( **Q186586**): PRB: getobject () 항상 반환 양의 높이 대 한 DIB 섹션입니다.  
  
- **DIBOR_BOTTOMUP** 줄 비트맵의 역순으로 되어 있습니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 끝 근처에 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 음수를 반환 하 합니다.  
  
- **DIBOR_TOPDOWN** 비트맵 선은 위에서 아래 순입니다. 이 인해 [CImage::GetBits](#getbits) 비트맵 버퍼의 첫 번째 바이트에 대 한 포인터를 반환 하 고 [CImage::GetPitch](#getpitch) 양수를 반환 하 합니다.  
  
### <a name="remarks"></a>주의  
 비트맵은 비 DIB 섹션 비트맵 또는 DIB 섹션 비트맵 될 수 있습니다. 참조 [IsDIBSection](#isdibsection) DIB에만 사용할 수 있는 메서드의 목록에 대 한 비트맵 섹션입니다.  
  
##  <a name="a-namebitblta--cimagebitblt"></a><a name="bitblt"></a>CImage::BitBlt  
 현재이 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사 합니다.  
  
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
 수행할 래스터 연산을 합니다. 래스터 연산 코드는 소스, 대상 및 패턴의 비트 (현재 선택 된 브러시에 의해 정의 됨)으로 결합 되어 대상 하는 방법을 정확히를 정의 합니다. 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 목록을 다른 래스터 연산 코드와 해당 설명이 나와 있습니다.  
  
 `pointDest`  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 대상 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형의 높이입니다.  
  
 `xSrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 소스 사각형의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `rectDest`  
 A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 대상 사각형을 나타내는 구조입니다.  
  
 `pointSrc`  
 A **지점** 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecimagea--cimagecimage"></a><a name="cimage"></a>CImage::CImage  
 `CImage` 개체를 생성합니다.  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>주의  
 개체를 생성 한 후 호출 [만들기](#create), [부하](#load), [LoadFromResource](#loadfromresource), 또는 [연결](#attach) 비트맵 개체에 연결 합니다.  
  
 **참고** Visual Studio에서이 클래스는 수의 개수를 유지 `CImage` 생성 된 개체입니다. 때마다 횟수가 0이 되 **수가** GDI +에서 사용 하는 리소스를 해제 하기 위해 자동으로 호출 합니다. 이렇게 하면 모든 `CImage` Dll에서 직접 또는 간접적으로 생성 된 개체는 항상 제대로 소멸 하 고 **수가** DllMain에서 호출 되지 않습니다.  
  
 사용 하 여 전역 `CImage` 개체 DLL에 권장 되지 않습니다. 전역 사용 해야 할 경우 `CImage` DLL 호출의에서 개체 [CImage::ReleaseGDIPlus](#releasegdiplus) 를 명시적으로 GDI +에서 사용 되는 리소스를 해제 합니다.  
  
##  <a name="a-namecreatea--cimagecreate"></a><a name="create"></a>CImage::Create  
 만듭니다는 `CImage` 비트맵에 이전에 생성 된 연결 및 `CImage` 개체입니다.  
  
```
BOOL Create(
 int nWidth,
 int nHeight,
 int nBPP,
 DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 너비는 `CImage` 픽셀에서 비트맵입니다.  
  
 `nHeight`  
 높이 `CImage` 픽셀에서 비트맵입니다. 경우 `nHeight` 비트맵이 상향식 DIB 및 원점은 왼쪽된 아래 모서리에는 양수입니다. 경우 `nHeight` 이 음수 이면 비트맵 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
 `nBPP`  
 비트맵의 픽셀 당 비트 숫자입니다. 일반적으로 4, 8, 16, 24 또는 32입니다. 흑백 비트맵 또는 마스크에 대 한 1을 수 있습니다.  
  
 `dwFlags`  
 비트맵 개체는 알파 채널이 있는지 여부를 지정 합니다. 0 개 이상의 다음 값의 조합일 수 있습니다.  
  
- **createAlphaChannel** 경우에 사용할 수 `nBPP` 32 및 `eCompression` 는 **BI_RGB**합니다. 를 지정 하는 경우에 생성된 된 이미지의 각 픽셀 (알파벳이 아닌 32 비트 이미지에 사용 되지 않는)의 네 번째 바이트에 저장 된 각 픽셀에 대 한 알파 (투명도) 값. 호출할 때이 알파 채널이 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.  
  
> [!NOTE]
>  에 대 한 호출에서 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 알파 자동으로 대상으로 혼합 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="a-namecreateexa--cimagecreateex"></a><a name="createex"></a>CImage::CreateEx  
 만듭니다는 `CImage` 비트맵에 이전에 생성 된 연결 및 `CImage` 개체입니다.  
  
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
 너비는 `CImage` 픽셀에서 비트맵입니다.  
  
 `nHeight`  
 높이 `CImage` 픽셀에서 비트맵입니다. 경우 `nHeight` 비트맵이 상향식 DIB 및 원점은 왼쪽된 아래 모서리에는 양수입니다. 경우 `nHeight` 이 음수 이면 비트맵 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
 `nBPP`  
 비트맵의 픽셀 당 비트 숫자입니다. 일반적으로 4, 8, 16, 24 또는 32입니다. 흑백 비트맵 또는 마스크에 대 한 1을 수 있습니다.  
  
 `eCompression`  
 (위에서 아래로 Dib를 압축할 수 없습니다.)는 압축 된 상향식 비트맵에 대 한 압축 유형을 지정 합니다. 다음 값 중 하나입니다.  
  
- **BI_RGB** 형식은 압축 되지 않습니다. 호출할 때이 값을 지정 `CImage::CreateEx` 호출과 같습니다 `CImage::Create`합니다.  
  
- **BI_BITFIELDS** 형식은 압축 된 고 색상표는 세 개의 이루어져 `DWORD` 빨간색으로 지정 하는 색 마스크 녹색, 각각 및 파랑 구성 요소, 각 픽셀의 합니다. 16 및 32 bpp 비트맵와 함께 사용할 경우에 유효 합니다.  
  
 *pdwBitfields*  
 경우에 사용 `eCompression` 로 설정 된 **BI_BITFIELDS**, 그렇지 않으면 이어야 합니다 **NULL**합니다. 세 개인 배열에 대 한 포인터 `DWORD` 빨강, 비트를 각 픽셀의 사용은 지정 하는 비트 마스크 녹색으로 표시 되는 색의 구성 요소는 각각 및 파랑입니다. 비트 필드에 대 한 제한 사항에 대 한 자세한 내용은 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `dwFlags`  
 비트맵 개체는 알파 채널이 있는지 여부를 지정 합니다. 0 개 이상의 다음 값의 조합일 수 있습니다.  
  
- **createAlphaChannel** 경우에 사용할 수 `nBPP` 32 및 `eCompression` 는 **BI_RGB**합니다. 를 지정 하는 경우에 생성된 된 이미지의 각 픽셀 (알파벳이 아닌 32 비트 이미지에 사용 되지 않는)의 네 번째 바이트에 저장 된 각 픽셀에 대 한 알파 (투명도) 값. 호출할 때이 알파 채널이 자동으로 사용 됩니다 [CImage::AlphaBlend](#alphablend)합니다.  
  
    > [!NOTE]
    >  에 대 한 호출에서 [CImage::Draw](#draw), 알파 채널을 사용 하 여 이미지는 알파 자동으로 대상으로 혼합 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 성공 하는 경우. 그렇지 않으면 **FALSE**합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 16 비트를 사용 하 여 각 픽셀을 인코딩하는 데 100 x 100 픽셀 비트맵을 만듭니다. 지정된 된 16 비트 픽셀에 0-3 비트 빨강 구성 요소, 4-7 비트 인코딩 녹색, 인코딩한 8-11 비트 인코딩 파란색입니다. 나머지 4 비트가 사용 되지 않습니다.  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="a-namedestroya--cimagedestroy"></a><a name="destroy"></a>CImage::Destroy  
 비트맵을 분리는 `CImage` 개체 하 고 비트맵을 삭제 합니다.  
  
```
void Destroy() throw();
```  
  
##  <a name="a-namedetacha--cimagedetach"></a><a name="detach"></a>CImage::Detach  
 비트맵을 분리 한 `CImage` 개체입니다.  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>반환 값  
 분리 비트맵에 대 한 핸들 또는 **NULL** 없는 비트맵 연결 되어 있습니다.  
  
##  <a name="a-namedrawa--cimagedraw"></a><a name="draw"></a>CImage::Draw  
 현재 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사 합니다.  
  
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
 대상 장치 컨텍스트의 핸들입니다.  
  
 `xDest`  
 X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형의 높이입니다.  
  
 `xSrc`  
 X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y 좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 소스 사각형의 논리 단위로 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위로 높이입니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 식별 하는 대상입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 소스를 식별 합니다.  
  
 `pointDest`  
 에 대 한 참조는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 **그리기** 와 동일한 작업을 수행 [StretchBlt](#stretchblt)이미지는 투명 한 색 또는 알파 채널 포함 되어 있지 않으면. 이 경우 **그리기** 으로 동일한 작업을 수행 [지연 해야](#transparentblt) 또는 [해 서 AlphaBlend](#alphablend) 필요에 따라 합니다.  
  
 버전에 대 한 **그리기** 소스 사각형을 지정 하지 않는, 전체 원본 이미지의 기본값입니다. 버전에 대 한 **그리기** 대상 사각형에 대 한 크기를 지정 하지 않는, 기본 및 확장 하지 않는 원본 이미지의 크기는 또는 발생을 축소 합니다.  
  
##  <a name="a-namegetbitsa--cimagegetbits"></a><a name="getbits"></a>CImage::GetBits  
 비트맵의 각된 픽셀의 실제 비트 값에 대 한 포인터를 검색합니다.  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>반환 값  
 비트맵 버퍼에 대 한 포인터입니다. 아래에서 위로 DIB 비트맵을 사용 하는 경우 포인터가 가리키는 버퍼의 끝을 부분입니다. 하향식 DIB 비트맵을 사용 하는 경우 버퍼의 첫 번째 바이트를 가리키는 포인터입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 값과 함께이 포인터를 사용 하 여 [GetPitch](#getpitch)를 찾아서는 이미지의 개별 픽셀을 변경할 수 있습니다.  
  
> [!NOTE]
>  이 방법은 지원만 DIB 섹션 비트맵입니다. 따라서의 픽셀에 액세스 한 `CImage` DIB 섹션의 픽셀을 동일한 동일한 방식으로 개체입니다. 반환 된 포인터의 위치 (0, 0)에 있는 픽셀을 가리킵니다.  
  
##  <a name="a-namegetbppa--cimagegetbpp"></a><a name="getbpp"></a>CImage::GetBPP  
 픽셀 당 비트 값을 검색합니다.  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 당 비트 수입니다.  
  
### <a name="remarks"></a>주의  
 이 값의 각 픽셀을 정의 하는 비트 수 및 비트맵의 색의 최대 수를 결정 합니다.  
  
 픽셀 당 비트 수는 일반적으로 1, 4, 8, 16, 24 또는 32입니다. 참조는 **biBitCount** 소속 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 이 값에 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namegetcolortablea--cimagegetcolortable"></a><a name="getcolortable"></a>CImage::GetColorTable  
 DIB 섹션의 팔레트에 있는 항목의 범위에서 빨간색, 녹색, 파란색 (RGB) 색 값을 검색 합니다.  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `iFirstColor`  
 색 테이블 인덱스를 검색 하는 첫 번째 항목입니다.  
  
 `nColors`  
 검색할 색 테이블 항목의 수입니다.  
  
 `prgbColors`  
 배열에 대 한 포인터 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 색을 검색 하는 구조 테이블 항목입니다.  
  
##  <a name="a-namegetdca--cimagegetdc"></a><a name="getdc"></a>CImage::GetDC  
 현재 보유 한 이미지를 선택 하는 장치 컨텍스트를 검색 합니다.  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 장치 컨텍스트에 대한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 각 호출 `GetDC`에 대 한 후속 호출을 해야 [ReleaseDC](#releasedc)합니다.  
  
##  <a name="a-namegetexporterfilterstringa--cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>CImage::GetExporterFilterString  
 이미지 저장에 대 한 이미지 형식을 사용할 수 있는 찾습니다.  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>매개 변수  
 *strExporters*  
 에 대 한 참조는 **CSimpleString** 개체입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.  
  
 `aguidFileTypes`  
 문자열에는 파일 형식 중 하나에 해당 하는 각 요소와 배열 Guid입니다. 예제에서 `pszAllFilesDescription` 아래 `aguidFileTypes`[0]은 `GUID_NULL` 나머지 배열 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식입니다.  
  
> [!NOTE]
>  전체 목록은 상수를 참조 하십시오. **이미지 파일 형식 상수** 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `pszAllFilesDescription`  
 이 매개 변수가 없으면 **NULL**, 필터 문자열 목록 맨 앞에 추가 필터 하나를 갖습니다. 이 필터의 현재 값을 갖습니다 `pszAllFilesDescription` 해당 설명에 대 한 고 목록에서 모든 다른 내보내기에서 지 원하는 모든 확장명의 파일을 허용 합니다.  
  
 예:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그는.  
  
- **excludeGIF** = 0x01 제외 GIF 파일입니다.  
  
- **excludeBMP** = 0x02 제외 BMP (Windows 비트맵) 파일입니다.  
  
- **excludeEMF** = 0x04 제외 EMF (확장 메타 파일) 파일입니다.  
  
- **excludeWMF** = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.  
  
- **excludeJPEG** = 0x10 제외 JPEG 파일입니다.  
  
- **excludePNG** = 0x20 제외 하는 PNG 파일입니다.  
  
- **excludeTIFF** = 0x40 제외 TIFF 파일입니다.  
  
- **excludeIcon** = 0x80 제외 ICO (Windows 아이콘) 파일입니다.  
  
- **excludeOther** = 0x80000000 위에 나열 되지 않은 파일 형식을 제외 합니다.  
  
- **excludeDefaultLoad** = 부하, 형식이 기본적으로 포함 된 모든 파일에 대 한 0  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF** 저장에 대 한 이러한 파일은 기본적으로 제외 일반적으로 특별 한 요구 사항이 있기 때문에 있습니다.  
  
 `chSeparator`  
 이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
### <a name="remarks"></a>주의  
 MFC 프로그램에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 다른 이름으로 저장 대화 상자에서 사용 가능한 이미지의 파일 확장명을 노출 하는 개체 형식입니다.  
  
 매개 변수 *strExporter* 형식은 같습니다.  
  
 description0 파일 | \*.ext0 | filedescription1 | \*.ext1 |... 파일 설명 *n*|\*합니다. ext *n*||  
  
 여기서 ' |'으로 지정 된 구분 기호 문자 `chSeparator`합니다. 예:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 기본 구분 기호를 사용 하 여 ' |' MFC에이 문자열을 전달 하면 `CFileDialog` 개체입니다. 일반적인 파일 저장 대화 상자에이 문자열을 전달 하는 경우에 null 구분 기호 '\0'를 사용 합니다.  
  
##  <a name="a-namegetheighta--cimagegetheight"></a><a name="getheight"></a>CImage::GetHeight  
 이미지의 픽셀에서 높이 검색합니다.  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이미지의 픽셀 높이입니다.  
  
##  <a name="a-namegetimporterfilterstringa--cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>CImage::GetImporterFilterString  
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
 에 대 한 참조는 **CSimpleString** 개체입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.  
  
 `aguidFileTypes`  
 문자열에는 파일 형식 중 하나에 해당 하는 각 요소와 배열 Guid입니다. 예제에서 `pszAllFilesDescription` 아래 `aguidFileTypes`[0]은 `GUID_NULL` 와 나머지 배열의 값은 현재 운영 체제에서 지 원하는 이미지 파일 형식입니다.  
  
> [!NOTE]
>  전체 목록은 상수를 참조 하십시오. **이미지 파일 형식 상수** 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `pszAllFilesDescription`  
 이 매개 변수가 없으면 **NULL**, 필터 문자열 목록 맨 앞에 추가 필터 하나를 갖습니다. 이 필터의 현재 값을 갖습니다 `pszAllFilesDescription` 해당 설명에 대 한 고 목록에서 모든 다른 내보내기에서 지 원하는 모든 확장명의 파일을 허용 합니다.  
  
 예:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 목록에서 제외할 파일 형식을 지정 하는 비트 플래그 집합입니다. 사용할 수 있는 플래그는.  
  
- **excludeGIF** = 0x01 제외 GIF 파일입니다.  
  
- **excludeBMP** = 0x02 제외 BMP (Windows 비트맵) 파일입니다.  
  
- **excludeEMF** = 0x04 제외 EMF (확장 메타 파일) 파일입니다.  
  
- **excludeWMF** = 0x08 제외 WMF (Windows 메타 파일) 파일입니다.  
  
- **excludeJPEG** = 0x10 제외 JPEG 파일입니다.  
  
- **excludePNG** = 0x20 제외 하는 PNG 파일입니다.  
  
- **excludeTIFF** = 0x40 제외 TIFF 파일입니다.  
  
- **excludeIcon** = 0x80 제외 ICO (Windows 아이콘) 파일입니다.  
  
- **excludeOther** = 0x80000000 위에 나열 되지 않은 파일 형식을 제외 합니다.  
  
- **excludeDefaultLoad** = 부하, 형식이 기본적으로 포함 된 모든 파일에 대 한 0  
  
- **excludeDefaultSave** = **excludeIcon | excludeEMF | excludeWMF** 저장에 대 한 이러한 파일은 기본적으로 제외 일반적으로 특별 한 요구 사항이 있기 때문에 있습니다.  
  
 `chSeparator`  
 이미지 형식 간에 사용 되는 구분 기호입니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>주의  
 MFC 프로그램에 결과 형식 문자열을 전달할 수 있습니다 [CFileDialog](../../mfc/reference/cfiledialog-class.md) 사용 가능한 이미지의 파일 확장명을 노출 하는 개체 형식에 **파일 열기** 대화 상자입니다.  
  
 매개 변수 *strImporter* 형식은 같습니다.  
  
 description0 파일 | \*.ext0 | filedescription1 | \*.ext1 |... 파일 설명 *n*|\*합니다. ext *n*||  
  
 여기서 ' |'으로 지정 된 구분 기호 문자 `chSeparator`합니다. 예:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 기본 구분 기호를 사용 하 여 ' |' MFC에이 문자열을 전달 하면 `CFileDialog` 개체입니다. 공통에이 문자열을 전달 하는 경우에 null 구분 기호 '\0'를 사용 하 여 **파일 열기** 대화 상자입니다.  
  
##  <a name="a-namegetmaxcolortableentriesa--cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>CImage::GetMaxColorTableEntries  
 색상표에 있는 항목의 최대 수를 검색합니다.  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 색상표에 있는 항목의 수입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="a-namegetpitcha--cimagegetpitch"></a><a name="getpitch"></a>CImage::GetPitch  
 이미지의 피치를 검색합니다.  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이미지의 피치 합니다. 반환 값이 음수 이면 비트맵 상향식 DIB 이며 원점은 왼쪽된 아래 모서리. 반환 값이 양수 이면 비트맵 하향식 DIB 이며 원점은 왼쪽된 위 모퉁이입니다.  
  
### <a name="remarks"></a>주의  
 피치 (바이트) 한 비트맵 줄의 시작 부분을 나타내는 두 개의 메모리 주소와 다음 비트맵 줄의 시작 부분 사이의 거리입니다. 피치 바이트 단위로 측정 되는 이미지의 피치를 통해 픽셀 형식을 확인할 수 있습니다. 피치는 비트맵에 대 한 예약 되는 추가 메모리를 포함할 수도 있습니다.  
  
 사용 하 여 `GetPitch` 와 [GetBits](#getbits) 이미지의 개별 픽셀을 찾으려고 합니다.  
  
> [!NOTE]
>  이 메서드는 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="a-namegetpixela--cimagegetpixel"></a><a name="getpixel"></a>CImage::GetPixel  
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
 빨간색, 녹색, 파란색 (RGB) 픽셀의 값입니다. 반환 값은 현재 클립 영역 외부의 픽셀 이면 **CLR_INVALID**합니다.  
  
##  <a name="a-namegetpixeladdressa--cimagegetpixeladdress"></a><a name="getpixeladdress"></a>CImage::GetPixelAddress  
 정확한 픽셀의 주소를 검색합니다.  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 픽셀의 x 좌표입니다.  
  
 *y*  
 픽셀의 y 좌표입니다.  
  
### <a name="remarks"></a>주의  
 주소는 픽셀의 좌표, 비트맵 및 픽셀 당 비트의 피치에 따라 결정 됩니다.  
  
 픽셀 당 8 비트 미만이 있는 형식의 경우이 메서드는 픽셀을 포함 하는 바이트의 주소를 반환 합니다. 예를 들어 이미지 형식, 픽셀당 4 비트 `GetPixelAddress` 반환 된 바이트가 고 첫 번째 픽셀의 주소를 2 바이트 픽셀에 대 한 계산 해야 합니다.  
  
> [!NOTE]
>  이 메서드는 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="a-namegettransparentcolora--cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>CImage::GetTransparentColor  
 색상표에서 투명 한 색의 인덱싱된 위치를 검색합니다.  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 투명 한 색의 인덱스입니다.  
  
##  <a name="a-namegetwidtha--cimagegetwidth"></a><a name="getwidth"></a>CImage::GetWidth  
 이미지의 픽셀에서 너비를 검색합니다.  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 비트맵의 너비입니다.  
  
##  <a name="a-nameisdibsectiona--cimageisdibsection"></a><a name="isdibsection"></a>CImage::IsDIBSection  
 연결 된 비트맵이 DIB 섹션 인지 확인 합니다.  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 경우 연결 된 비트맵이 DIB 섹션입니다. 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 비트맵이 DIB 섹션에서 다음을 사용할 수 없습니다 `CImage` 메서드 DIB 섹션 비트맵만을 지원 합니다.  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="a-nameisindexeda--cimageisindexed"></a><a name="isindexed"></a>CImage::IsIndexed  
 비트맵의 픽셀 색 팔레트에 매핑되는 있는지 여부를 결정 합니다.  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 **true 이면** 인덱스이 고 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 **true** 비트맵은 8 비트 하는 경우에 (256 색)이 있습니다.  
  
> [!NOTE]
>  이 메서드는 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="a-nameisnulla--cimageisnull"></a><a name="isnull"></a>CImage::IsNull  
 비트맵 현재 로드 된 경우를 결정 합니다.  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>주의  
 이 메서드가 반환 **True** 비트맵 없는 경우 현재 로드 하 고, 그렇지 않으면 **False**합니다.  
  
##  <a name="a-nameistransparencysupporteda--cimageistransparencysupported"></a><a name="istransparencysupported"></a>CImage::IsTransparencySupported  
 응용 프로그램이 투명 한 비트맵 지원 여부와 Windows 2000 이상 컴파일된 나타냅니다.  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 속성을&0;이 아닌 경우 현재 플랫폼에서 투명도 지원 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 반환 값은&0;이 아니면 고 투명도 사용할 수에 대 한 호출 [해 서 AlphaBlend](#alphablend), [지연 해야](#transparentblt), 또는 [그리기](#draw) 투명 한 색을 처리 합니다.  
  
 운영 체제와 함께 사용할 Windows 2000 또는 Windows 98 하기 전에 응용 프로그램을 컴파일된 경우이 메서드는 0, 최신 운영 체제에도 항상 반환 합니다.  
  

##  <a name="a-nameloada--cimageload"></a><a name="load"></a>CImage::Load  
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
  
### <a name="remarks"></a>주의  
 지정 된 이미지를 로드 *pszFileName* 또는 `pStream`합니다.  
  
 올바른 이미지 형식은 BMP, GIF, JPEG, PNG 및 TIFF 합니다.  
  
##  <a name="a-nameloadfromresourcea--cimageloadfromresource"></a><a name="loadfromresource"></a>CImage::LoadFromResource  
 이미지를 로드 한 `BITMAP` 리소스입니다.  
  
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
 로드할 이미지를 포함 하는 모듈의 인스턴스 핸들입니다.  
  
 `pszResourceName`  
 로드 하려는 이미지를 포함 하는 리소스의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nIDResource`  
 로드 된 리소스의 ID입니다.  
  
### <a name="remarks"></a>주의  
 리소스 형식 이어야 합니다 `BITMAP`합니다.  
  
##  <a name="a-namemaskblta--cimagemaskblt"></a><a name="maskblt"></a>CImage::MaskBlt  
 지정 된 마스크와 래스터 연산을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.  
  
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
 해당 실행 파일 리소스를 포함 하는 모듈에 대 한 핸들입니다.  
  
 `xDest`  
 X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형 및 소스 비트맵의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형 및 소스 비트맵의 높이입니다.  
  
 `xSrc`  
 소스 비트맵의 왼쪽된 위 모퉁이의 논리적 x 좌표입니다.  
  
 `ySrc`  
 소스 비트맵의 왼쪽된 위 모퉁이의 논리적 y 좌표입니다.  
  
 `hbmMask`  
 소스 장치 컨텍스트에서 비트맵을 색 비트맵 함께 단색 마스크가 비트맵 핸들입니다.  
  
 `xMask`  
 에 지정 된 마스크 비트맵에 대 한 가로 픽셀 오프셋은 `hbmMask` 매개 변수입니다.  
  
 `yMask`  
 에 지정 된 마스크 비트맵에 대 한 픽셀 수직 오프셋은 `hbmMask` 매개 변수입니다.  
  
 `dwROP`  
 원본 및 대상 데이터의 조합을 제어 하는 메서드에서 사용 하는 삼항 래스터 연산 코드를 모두 전경색과 배경색을 지정 합니다. 배경 래스터 연산 코드는이 값;의 상위 단어로의 상위 바이트에 저장 됩니다. 전경 래스터 연산 코드는이 값;의 상위 단어에 대해 하위 바이트에 저장 됩니다. 이 값의 하위 단어로 무시 되 고&0; 이어야 합니다. 전경색과 배경색이 메서드의 컨텍스트에 설명은 `MaskBlt` 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 일반적인 래스터 연산 코드 목록은 참조 하십시오. `BitBlt` 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `rectDest`  
 에 대 한 참조는 `RECT` 구조를 식별 하는 대상입니다.  
  
 `pointSrc`  
 A `POINT` 소스 사각형의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `pointMask`  
 A **지점** 마스크 비트맵의 왼쪽된 위 모퉁이 나타내는 구조입니다.  
  
 `pointDest`  
 에 대 한 참조는 **지점** 논리 단위에 있는 대상 사각형의 왼쪽된 위 모퉁이 식별 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 Windows NT 4.0 이상에 해당 버전에 적용 됩니다.  
  
##  <a name="a-nameoperatorhbitmapa--cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>HBITMAP CImage::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CImage` 개체입니다. 이 연산자는 직접 사용을 지원 하려면 캐스팅 연산자는 `HBITMAP` 개체입니다.  
  
##  <a name="a-nameplgblta--cimageplgblt"></a><a name="plgblt"></a>CImage::PlgBlt  
 소스 장치 컨텍스트에의 사각형에서 대상 장치 컨텍스트의 사변형으로 비트 블록 전송을 수행합니다.  
  
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
 대상 장치 컨텍스트의 핸들입니다.  
  
 *pPoints*  
 대상 평행 사변형의 세 모퉁이 식별 하는 논리적 공간에&3; 개의 점 배열에 대 한 포인터입니다. 소스 사각형의 왼쪽된 위 모퉁이이 배열, 오른쪽 위 모서리를이 배열에 있는 두 번째 지점 및 세 번째 데이터 요소 왼쪽된 아래 모서리에서 첫 번째 요소와 매핑됩니다. 소스 사각형의 오른쪽 아래 모퉁이 평행 사변형에 암시적 네 번째 요소와 매핑됩니다.  
  
 `hbmMask`  
 소스 사각형의 색을 마스크 하는 데 사용 되는 선택적 흑백 비트맵에 대 한 핸들입니다.  
  
 `xSrc`  
 X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y 좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 소스 사각형의 논리 단위로 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위로 높이입니다.  
  
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
  
### <a name="remarks"></a>주의  
 경우 `hbmMask` 유효한 단색 비트맵을 식별 **PlgBit** 이 비트맵을 사용 하 여 소스 사각형의 색 데이터 비트 마스크입니다.  
  
 이 메서드는 Windows NT 4.0 이상에 해당 버전에 적용 됩니다. 참조 [PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 대 한 더 자세한 정보.  
  
##  <a name="a-namereleasedca--cimagereleasedc"></a><a name="releasedc"></a>CImage::ReleaseDC  
 장치 컨텍스트를 해제 합니다.  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>주의  
 호출 해야 하므로 하나의 비트맵을 선택할 수 장치 컨텍스트로 한 번에 `ReleaseDC` 에 대 한 각 호출 [GetDC](#getdc)합니다.  
  
##  <a name="a-namereleasegdiplusa--cimagereleasegdiplus"></a><a name="releasegdiplus"></a>CImage::ReleaseGDIPlus  
 GDI +에서 사용 되는 리소스를 해제 합니다.  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>주의  
 전역에 의해 할당 되는 무료 리소스에이 메서드를 호출 해야 `CImage` 개체입니다. 참조 [CImage::CImage](#cimage)합니다.  
  
##  <a name="a-namesavea--cimagesave"></a><a name="save"></a>CImage::Save  
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
 이미지를 저장 하려면 파일 형식입니다. 다음 중 하나일 수 있습니다.  
  
- **ImageFormatBMP** 압축 푼된 비트맵 이미지입니다.  
  
- **ImageFormatPNG** 압축 된 이미지는 PNG 이동식 네트워크 그래픽 ().  
  
- **ImageFormatJPEG** A JPEG 압축 된 이미지입니다.  
  
- **ImageFormatGIF** A GIF 압축 된 이미지입니다.  
  
> [!NOTE]
>  전체 목록은 상수를 참조 하십시오. **이미지 파일 형식 상수** 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
### <a name="remarks"></a>주의  
 지정한 이름 및 형식을 사용 하 여 이미지를 저장 하려면이 함수를 호출 합니다. 하는 경우는 `guidFileType` 매개 변수를 포함할 파일 이름 확장명에서 이미지 형식을 결정 하는 데 사용 됩니다. 확장명이 없는 아무 것도 제공 하는 경우 이미지 BMP 형식으로 저장 됩니다.  
  
##  <a name="a-namesetcolortablea--cimagesetcolortable"></a><a name="setcolortable"></a>CImage::SetColorTable  
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
 설정 하려면 색 테이블 항목의 수입니다.  
  
 `prgbColors`  
 배열에 대 한 포인터 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938) 색을 설정 하는 구조 테이블 항목입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 DIB 섹션 비트맵만 지원합니다.  
  
##  <a name="a-namesetpixela--cimagesetpixel"></a><a name="setpixel"></a>CImage::SetPixel  
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
 픽셀을 설정 하는 색입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 픽셀을 선택 된 클립 영역 외부에서 실시간 조정 하는 경우 실패 합니다.  
  
##  <a name="a-namesetpixelindexeda--cimagesetpixelindexed"></a><a name="setpixelindexed"></a>CImage::SetPixelIndexed  
 픽셀 색에 있는 색을 설정 `iIndex` 색 팔레트에 있습니다.  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 설정할 픽셀의 가로 위치입니다.  
  
 *y*  
 설정할 픽셀의 세로 위치입니다.  
  
 `iIndex`  
 색상표에서 색의 인덱스입니다.  
  
##  <a name="a-namesetpixelrgba--cimagesetpixelrgb"></a><a name="setpixelrgb"></a>CImage::SetPixelRGB  
 로 지정 된 위치에서 설정 하는 픽셀 *x* 및 *y* 로 표시 된 색에 *r*, *g*, 및 *b*, 빨간색, 녹색, 파란색 (RGB) 이미지입니다.  
  
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
 빨강의 강도 따라 합니다.  
  
 *g*  
 녹색의 강도 따라 합니다.  
  
 *b*  
 파란색의 강도 따라 합니다.  
  
### <a name="remarks"></a>주의  
 빨간색, 녹색 및 파란색 매개 변수는 각각 0에서 255 사이의 숫자 표시. 모든 세 개의 매개 변수를&0;으로 설정 하면 결합 된 결과 색은 검정입니다. 세 매개 변수 모두를 255로 설정 하면 결합 된 결과 색은 흰색입니다.  
  
##  <a name="a-namesettransparentcolora--cimagesettransparentcolor"></a><a name="settransparentcolor"></a>CImage::SetTransparentColor  
 투명으로 지정된 된 인덱스 위치에 색을 설정합니다.  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *iTransparentColor*  
 색을 투명 하 게 설정 하려면의 색상표 인덱스입니다. 경우-1을 색이 없으면 설정은 투명 하 게 합니다.  
  
### <a name="return-value"></a>반환 값  
 색의 인덱스는 이전에 투명 하 게 설정 합니다.  
  
##  <a name="a-namestretchblta--cimagestretchblt"></a><a name="stretchblt"></a>CImage::StretchBlt  
 현재이 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사 합니다.  
  
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
 대상 장치 컨텍스트의 핸들입니다.  
  
 `xDest`  
 X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형의 높이입니다.  
  
 `dwROP`  
 수행할 래스터 연산을 합니다. 래스터 연산 코드는 소스, 대상 및 패턴의 비트 (현재 선택 된 브러시에 의해 정의 됨)으로 결합 되어 대상 하는 방법을 정확히를 정의 합니다. 참조 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 목록을 다른 래스터 연산 코드와 해당 설명이 나와 있습니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 식별 하는 대상입니다.  
  
 `xSrc`  
 X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y 좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 소스 사각형의 논리 단위로 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위로 높이입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 소스를 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nametransparentblta--cimagetransparentblt"></a><a name="transparentblt"></a>CImage::TransparentBlt  
 현재이 장치 컨텍스트를 소스 장치 컨텍스트에에서 비트맵을 복사 합니다.  
  
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
 대상 장치 컨텍스트의 핸들입니다.  
  
 `xDest`  
 X 좌표를 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `yDest`  
 Y 좌표, 대상 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nDestWidth`  
 논리 단위는 대상 사각형의 너비입니다.  
  
 `nDestHeight`  
 논리 단위는 대상 사각형의 높이입니다.  
  
 *crTransparent*  
 소스 비트맵을 투명 하 게 처리할 색입니다. 기본적으로 **CLR_INVALID**, 현재 이미지의 투명 한 색으로 설정 된 색상을 사용 해야 함을 나타내는 합니다.  
  
 `rectDest`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 식별 하는 대상입니다.  
  
 `xSrc`  
 X 좌표를 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `ySrc`  
 Y 좌표, 소스 사각형의 왼쪽된 위 모퉁이의 논리 단위입니다.  
  
 `nSrcWidth`  
 소스 사각형의 논리 단위로 너비입니다.  
  
 `nSrcHeight`  
 소스 사각형의 논리 단위로 높이입니다.  
  
 `rectSrc`  
 에 대 한 참조는 `RECT` 구조를 소스를 식별 합니다.  
  
### <a name="return-value"></a>반환 값  
 **TRUE** 성공 하 고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 `TransparentBlt`소스 비트맵의 픽셀 당 및 픽셀 당 8 비트 4 개 비트에 지원 됩니다. 사용 하 여 [CImage::AlphaBlend](#alphablend) 투명도 있는 32 비트 / 픽셀 비트맵을 지정 합니다.  
  
  
### <a name="example"></a>예제  

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
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)
 [장치 독립적 비트맵](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   










