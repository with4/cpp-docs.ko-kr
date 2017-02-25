---
title: "CImage Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CImage"
  - "ATL.CImage"
  - "ATL::CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".gif 파일, ATL and MFC support"
  - "비트맵[C++], ATL and MFC support for"
  - "CImage class"
  - "gif 파일, ATL and MFC support"
  - "이미지[C++], ATL and MFC support for"
  - "jpeg 파일"
  - "PNG 파일, ATL and MFC support"
  - "transparent color"
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CImage Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CImage`로드 하 고 이미지를 JPEG, GIF, BMP, PNG \(이동식 네트워크 그래픽\) 형식으로 저장 하는 기능 등 향상 된 비트맵 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CImage  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CImage::CImage](../Topic/CImage::CImage.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md)|투명 또는 반투명 픽셀 비트맵을 표시 합니다.|  
|[CImage::Attach](../Topic/CImage::Attach.md)|첨부는 `HBITMAP` 에 `CImage` 개체입니다.  비 DIB 섹션 비트맵 또는 DIB 섹션 비트맵을 사용할 수 있습니다.|  
|[CImage::BitBlt](../Topic/CImage::BitBlt.md)|비트맵 소스 장치 컨텍스트에서이 현재 장치 컨텍스트를 복사합니다.|  
|[CImage::Create](../Topic/CImage::Create.md)|DIB 섹션 비트맵을 만들고이를 이전에 생성 된 연결 `CImage` 개체입니다.|  
|[CImage::CreateEx](../Topic/CImage::CreateEx.md)|DIB 섹션 비트맵 \(추가 매개 변수\)를 만들고 이전에 생성 된 첨부 `CImage` 개체입니다.|  
|[CImage::Destroy](../Topic/CImage::Destroy.md)|비트맵에서 분리 된 `CImage` 개체와 비트맵을 소멸 시킵니다.|  
|[CImage::Detach](../Topic/CImage::Detach.md)|비트맵에서 분리 된 `CImage` 개체입니다.|  
|[CImage::Draw](../Topic/CImage::Draw.md)|비트맵 소스 사각형 대상 사각형에 복사합니다.  **그릴** 확장 또는 필요한 경우 대상 사각형의 크기에 맞게 비트맵 압축 및 알파 혼합 색을 투명 하 게 처리 합니다.|  
|[CImage::GetBits](../Topic/CImage::GetBits.md)|비트맵의 실제 픽셀 값에 대 한 포인터를 검색합니다.|  
|[CImage::GetBPP](../Topic/CImage::GetBPP.md)|픽셀 당 비트 수를 검색합니다.|  
|[CImage::GetColorTable](../Topic/CImage::GetColorTable.md)|색상표에서 항목의 범위에서 빨강, 녹색, 파랑 \(RGB\) 색 값을 검색합니다.|  
|[CImage::GetDC](../Topic/CImage::GetDC.md)|현재 비트맵으로 선택 된 장치 컨텍스트를 검색 합니다.|  
|[CImage::GetExporterFilterString](../Topic/CImage::GetExporterFilterString.md)|사용할 수 있는 이미지 형식 및 그에 대 한 찾습니다.|  
|[CImage::GetHeight](../Topic/CImage::GetHeight.md)|현재 이미지의 픽셀 높이 검색합니다.|  
|[CImage::GetImporterFilterString](../Topic/CImage::GetImporterFilterString.md)|사용할 수 있는 이미지 형식 및 그에 대 한 찾습니다.|  
|[CImage::GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)|색상표에서 항목의 최대 수를 검색합니다.|  
|[CImage::GetPitch](../Topic/CImage::GetPitch.md)|바이트 단위의 현재 이미지의 피치를 검색합니다.|  
|[CImage::GetPixel](../Topic/CImage::GetPixel.md)|지정 된 픽셀의 색을 검색  *x* 및  *y*.|  
|[CImage::GetPixelAddress](../Topic/CImage::GetPixelAddress.md)|주어진된 픽셀의 주소를 검색합니다.|  
|[CImage::GetTransparentColor](../Topic/CImage::GetTransparentColor.md)|색상표에서 투명 한 색의 위치를 검색합니다.|  
|[CImage::GetWidth](../Topic/CImage::GetWidth.md)|현재 이미지의 픽셀 너비를 검색합니다.|  
|[CImage::IsDIBSection](../Topic/CImage::IsDIBSection.md)|연결 된 비트맵 DIB 구역 인지 여부를 확인 합니다.|  
|[CImage::IsIndexed](../Topic/CImage::IsIndexed.md)|비트맵의 색 인덱스 된 색상표에 매핑되지 않은 상태임을 나타냅니다.|  
|[CImage::IsNull](../Topic/CImage::IsNull.md)|소스 비트맵을 현재 로드 되어 있는지를 나타냅니다.|  
|[CImage::IsTransparencySupported](../Topic/CImage::IsTransparencySupported.md)|응용 프로그램을 투명 한 비트맵을 지원 하 고 Windows 2000 또는 나중에 컴파일된 여부를 나타냅니다.|  
|[CImage::Load](../Topic/CImage::Load.md)|지정 된 파일에서 이미지를 로드합니다.|  
|[CImage::LoadFromResource](../Topic/CImage::LoadFromResource.md)|지정 된 리소스에서 이미지를 로드합니다.|  
|[CImage::MaskBlt](../Topic/CImage::MaskBlt.md)|지정 된 마스크와 래스터 작업을 사용 하 여 원본 및 대상 비트맵에 대 한 색 데이터를 결합 합니다.|  
|[CImage::PlgBlt](../Topic/CImage::PlgBlt.md)|비트 블록 전송에서 사각형 원본 장치 컨텍스트에서 대상 장치 컨텍스트의 평행 사변형으로 수행합니다.|  
|[CImage::ReleaseDC](../Topic/CImage::ReleaseDC.md)|검색 된 장치 컨텍스트를 해제  [CImage::GetDC](../Topic/CImage::GetDC.md).|  
|[CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)|GDI\+를 사용 하는 리소스를 해제 합니다.  사용 가능한 리소스를 전역으로 만든 호출 해야 `CImage` 개체입니다.|  
|[CImage::Save](../Topic/CImage::Save.md)|지정 된 형식으로 이미지를 저장합니다.  **저장** 이미지 옵션을 지정할 수 없습니다.|  
|[CImage::SetColorTable](../Topic/CImage::SetColorTable.md)|빨강, 녹색, 파란색 RGB 설정\) 색 색상표 DIB 구역의 항목 범위의 값입니다.|  
|[CImage::SetPixel](../Topic/CImage::SetPixel.md)|지정 된 좌표에 지정 된 색상의 픽셀을 설정합니다.|  
|[CImage::SetPixelIndexed](../Topic/CImage::SetPixelIndexed.md)|색상 팔레트의 지정 된 인덱스에 지정 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetPixelRGB](../Topic/CImage::SetPixelRGB.md)|지정 된 빨강, 녹색, 파랑 \(RGB\) 값으로 지정 된 좌표에 있는 픽셀을 설정합니다.|  
|[CImage::SetTransparentColor](../Topic/CImage::SetTransparentColor.md)|투명으로 처리 하는 색의 인덱스를 설정 합니다.  팔레트에서는 하나의 색 투명 하 게 될 수 있습니다.|  
|[CImage::StretchBlt](../Topic/CImage::StretchBlt.md)|비트맵 소스 사각형 또는 필요한 경우 대상 사각형의 크기에 맞게 비트맵 압축 대상 사각형에 복사 합니다.|  
|[CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md)|비트맵에서 투명 한 색 원본 장치 컨텍스트에서이 현재 장치 컨텍스트를 복사합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CImage::operator HBITMAP](../Topic/CImage::operator%20HBITMAP.md)|연결에 대 한 Windows 핸들을 반환의 `CImage` 개체입니다.|  
  
## 설명  
 `CImage`비트맵 장치 독립적 비트맵 \(DIB\) 섹션 중 하나 인지 됩니다. 그러나 사용할 수 있는  [만들기](../Topic/CImage::Create.md) 또는  [CImage::Load](../Topic/CImage::Load.md) 만 DIB 섹션.  비 DIB 섹션 비트맵에 첨부할 수 있습니다는 `CImage` 개체를 사용 하 여  [첨부](../Topic/CImage::Attach.md), 하지만 다음 수 `CImage` DIB 섹션 비트맵을 지 원하는 방법:  
  
-   [GetBits](../Topic/CImage::GetBits.md)  
  
-   [GetColorTable](../Topic/CImage::GetColorTable.md)  
  
-   [GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)  
  
-   [GetPitch](../Topic/CImage::GetPitch.md)  
  
-   [GetPixelAddress](../Topic/CImage::GetPixelAddress.md)  
  
-   [IsIndexed](../Topic/CImage::IsIndexed.md)  
  
-   [SetColorTable](../Topic/CImage::SetColorTable.md)  
  
 연결 된 비트맵을 DIB 구역 인지 여부를 확인 하려면 호출  [IsDibSection](../Topic/CImage::IsDIBSection.md)**.**  
  
> [!NOTE]
>  **참고**  에서 Visual Studio.net 2003이이 클래스의 개수를 유지 `CImage` 개체를 생성 합니다.  때마다 횟수가 되는 함수를 0으로  [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) GDI\+를 사용 하는 리소스를 해제 하려면 자동으로 호출 됩니다.  하나 이렇게 `CImage` 직접 또는 간접적으로 Dll에서 만든 개체 제대로 소멸 되어 항상 고  **GdiplusShutdown** 를 호출할 때 `DllMain`.  
  
> [!NOTE]
>  전역을 사용 하 여 `CImage` 개체 DLL에서 권장 되지 않습니다.  전역을 사용 하는 경우 `CImage` 개체 DLL 호출에서에서  [CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md) GDI\+를 사용 하는 리소스를 명시적으로 해제 합니다.  
  
 `CImage`새에 선택할 수 없습니다  [CDC](../../mfc/reference/cdc-class.md).  `CImage`자체 생성  **HDC** 이미지.  때문에 `HBITMAP` 만 하나로 선택할 수 있습니다  **HDC** 번의 `HBITMAP` 연관의 `CImage` 다른 형식으로 선택할 수 없습니다  **HDC**.  필요한 경우는 `CDC`, 검색은  **HDC** 에서 `CImage` 를 제공 하 고  [CDC::FromHandle](../Topic/CDC::FromHandle.md).  
  
## 예제  
 [!code-cpp[NVC_ATLMFC_Utilities#70](../../atl-mfc-shared/codesnippet/CPP/cimage-class_1.cpp)]  
  
 사용 하는 경우 `CImage` 는 MFC 프로젝트에서 프로젝트 멤버 함수에 대 한 포인터를 예상 참고는  [CBitmap](../../mfc/reference/cbitmap-class.md) 개체.  사용 하려는 경우 `CImage` 이러한 함수 처럼  [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md), 사용  [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md), 전달에 `CImage``HBITMAP`, 반환 되는 사용 `CBitmap*`.  
  
## 예제  
 [!code-cpp[NVC_ATLMFC_Utilities#71](../../atl-mfc-shared/codesnippet/CPP/cimage-class_2.cpp)]  
  
 \- `CImage`, 실제 비트 DIB 섹션의 액세스 권한이.  사용할 수 있는 `CImage` 아무 곳 이나 Win32 이러한 방식으로 또는 DIB 섹션 이전에 사용한 개체.  
  
> [!NOTE]
>  다음 `CImage` 메서드 사용에 한계도 있습니다.  
  
|메서드|제한|  
|---------|--------|  
|[PlgBlt](../Topic/CImage::PlgBlt.md)|만 Windows NT 4.0 또는 나중에 사용할 수 있습니다.  Windows 95\/98 이상에서 실행 되는 응용 프로그램에는 작동 하지 않습니다.|  
|[MaskBlt](../Topic/CImage::MaskBlt.md)|만 Windows NT 4.0 또는 나중에 사용할 수 있습니다.  Windows 95\/98 이상에서 실행 되는 응용 프로그램에는 작동 하지 않습니다.|  
|[AlphaBlend](../Topic/CImage::AlphaBlend.md)|Windows 2000, Windows 98 및 이후 시스템에서 작동 합니다.|  
|[지연 해야](../Topic/CImage::TransparentBlt.md)|Windows 2000, Windows 98 및 이후 시스템에서 작동 합니다.|  
|[그리기](../Topic/CImage::Draw.md)|Windows 2000, Windows 98 및 이후 시스템 투명도 지원합니다.|  
  
 참조  [CImage 제한 이전 운영 체제와](../../mfc/cimage-limitations-with-earlier-operating-systems.md) 에 제한에 대 한 이러한 메서드에 대 한 자세한.  
  
 사용할 수 있는 `CImage` 는 MFC 나 ATL에서  
  
> [!NOTE]
>  사용 하 여 프로젝트를 만들 때 `CImage`를 정의 해야 `CString` 를 포함 하기 전에 `atlimage.h`.  MFC 없이 ATL 프로젝트를 사용 하는 경우 포함 `atlstr.h` 를 포함 하기 전에 `atlimage.h`.  프로젝트에 MFC \(또는 MFC 지원을 ATL 프로젝트 인지\) 사용 하는 경우 포함 `afxstr.h` 를 포함 하기 전에 `atlimage.h`.  
>   
>  마찬가지로 포함 해야 `atlimage.h` 를 포함 하기 전에 `atlimpl.cpp`.  이 작업을 쉽게 수행 하려면 포함 `atlimage.h` 에 `stdafx.h`.  
  
## 요구 사항  
 **헤더:**  atlimage.h  
  
## 참고 항목  
 [MMXSwarm 샘플](../../top/visual-cpp-samples.md)   
 [SimpleImage 샘플](../../top/visual-cpp-samples.md)   
 [Device\-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)