---
title: "AFX_GLOBAL_DATA 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AFX_GLOBAL_DATA
dev_langs: C++
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 54ca5ac28d4f5fb044b78ad7b846cd20d73e2c22
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA 구조체
`AFX_GLOBAL_DATA` 구조는 프레임워크를 관리하거나 응용 프로그램의 모양과 동작을 사용자 지정하는 데 사용되는 필드 및 메서드를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct AFX_GLOBAL_DATA  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|`AFX_GLOBAL_DATA` 구조를 생성합니다.|  
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: cleanup](#cleanup)|브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.|  
|[Afx_global_data:: drawparentbackground](#drawparentbackground)|지정된 영역에 컨트롤 부모의 배경을 그립니다.|  
|[Afx_global_data:: drawtextonglass](#drawtextonglass)|지정된 테마의 비주얼 스타일로 지정된 텍스트를 그립니다.|  
|[Afx_global_data:: excludetag](#excludetag)|지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.|  
|[Afx_global_data:: getcolor](#getcolor)|지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|글로벌 데이터에 저장된 `ID2D1Factory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[Afx_global_data:: gethandcursor](#gethandcursor)|식별자가 `IDC_HAND`인 손 모양의 미리 정의된 커서를 검색합니다.|  
|[Afx_global_data:: getitaskbarlist](#getitaskbarlist)|ITaskBarList 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|  
|[Afx_global_data:: getitaskbarlist3](#getitaskbarlist3)|ITaskBarList3 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|  
|[Afx_global_data:: getnonclientmetrics](#getnonclientmetrics)|최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.|  
|[Afx_global_data:: getshellautohidebars](#getshellautohidebars)|셸 자동 숨기기 막대의 위치를 결정합니다.|  
|[Afx_global_data:: gettextheight](#gettextheight)|현재 글꼴에서 텍스트 문자의 높이를 검색합니다.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|글로벌 데이터에 저장된 `IWICImagingFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|글로벌 데이터에 저장된 `IDWriteFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D`, `DirectWrite`및 `WIC` 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|  
|[Afx_global_data:: is32biticons](#is32biticons)|미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D` 의 초기화 여부를 확인합니다.|  
|[Afx_global_data:: isdwmcompositionenabled](#isdwmcompositionenabled)|Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) 메서드를 호출하는 간단한 방법을 제공합니다.|  
|[Afx_global_data:: ishighcontrastmode](#ishighcontrastmode)|이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.|  
|[Afx_global_data:: onsettingchange](#onsettingchange)|데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.|  
|[Afx_global_data:: registerwindowclass](#registerwindowclass)|지정된 MFC 창 클래스를 등록합니다.|  
|[Afx_global_data:: releasetaskbarrefs](#releasetaskbarrefs)|GetITaskbarList 및 GetITaskbarList3 메서드를 통해 얻은 인터페이스를 해제합니다.|  
|[Afx_global_data:: resume](#resume)|Windows [테마 및 비주얼 스타일](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)을 지원하는 메서드에 액세스하는 내부 함수 포인터를 다시 초기화합니다.|  
|[Afx_global_data:: setlayeredattrib](#setlayeredattrib)|Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) 메서드를 호출하는 간단한 방법을 제공합니다.|  
|[Afx_global_data:: setmenufont](#setmenufont)|지정된 논리 글꼴을 만듭니다.|  
|[Afx_global_data:: shellcreateitemfromparsingname](#shellcreateitemfromparsingname)|구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.|  
|[Afx_global_data:: updatefonts](#updatefonts)|프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.|  
|[Afx_global_data:: updatesyscolors](#updatesyscolors)|프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: enableaccessibilitysupport](#enableaccessibilitysupport)|Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다. Active Accessibility는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 방법을 제공합니다.|  
|[Afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport)|Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: iswindowslayersupportavailable](#iswindowslayersupportavailable)|운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: bisosalphablendingsupport](#bisosalphablendingsupport)|현재 운영 체제가 알파 혼합을 지원하는지 여부를 나타냅니다.|  
|[Afx_global_data:: biswindows7](#biswindows7)|응용 프로그램이 Windows 7 운영 체제 이상에서 실행되고 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: clractivecaptiongradient](#clractivecaptiongradient)|활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[Afx_global_data:: clrinactivecaptiongradient](#clrinactivecaptiongradient)|비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[Afx_global_data:: m_busebuiltin32biticons](#m_busebuiltin32biticons)|프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.|  
|[Afx_global_data:: m_busesystemfont](#m_busesystemfont)|시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.|  
|[Afx_global_data:: m_hcurhand](#m_hcurhand)|손 모양 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hcurstretch](#m_hcurstretch)|가로 늘이기 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hcurstretchvert](#m_hcurstretchvert)|세로 늘이기 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hicontool](#m_hicontool)|도구 아이콘에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_nautohidetoolbarmargin](#m_nautohidetoolbarmargin)|맨 왼쪽 자동 숨기기 도구 모음에서 도킹 모음의 왼쪽까지의 오프셋을 지정합니다.|  
|[Afx_global_data:: m_nautohidetoolbarspacing](#m_nautohidetoolbarspacing)|자동 숨기기 도구 모음 사이의 간격을 지정합니다.|  
|[Afx_global_data:: m_ndragframethicknessdock](#m_ndragframethicknessdock)|도킹된 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|  
|[Afx_global_data:: m_ndragframethicknessfloat](#m_ndragframethicknessfloat)|부동 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA` 구조에서 대부분의 데이터는 응용 프로그램 시작 시 초기화됩니다.  
  
### <a name="inheritance-hierarchy"></a>상속 계층  
 `AFX_GLOBAL_DATA`   
  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxglobals.h  
  
### <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="bisosalphablendingsupport"></a>Afx_global_data:: bisosalphablendingsupport
운영 체제 알파 혼합을 지원 하는지 여부를 나타냅니다.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE`알파 혼합은 지원; 나타냅니다. 그렇지 않으면 `FALSE`합니다.  
  

## <a name="cleanup"></a>Afx_global_data:: cleanup
브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.  
  
  
```  
void CleanUp();
```  
## <a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
### <a name="parameters"></a>매개 변수   
 `angle`  
 시계 방향으로 회전 각도도 합니다.  
  
 `center`  
 회전할에 대 한 점입니다.  
  
 `matrix`  
 이 메서드가 반환 될 때 새 회전 변환을 포함 되어 있습니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 성공 하면 s_ok이 고 또는 오류 값을 반환 합니다.  
  
## <a name="drawparentbackground"></a>Afx_global_data:: drawparentbackground
지정된 영역에 컨트롤 부모의 배경을 그립니다.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `pWnd`  
 컨트롤의 창에 대한 포인터입니다.  
  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `lpRect`  
 그리는 영역 경계가 되는 사각형에 대한 포인터입니다. 기본값은 `NULL`입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
## <a name="drawtextonglass"></a>Afx_global_data:: drawtextonglass
지정된 테마의 비주얼 스타일로 지정된 텍스트를 그립니다.  
  
  
```  
BOOL DrawTextOnGlass(
    HTHEME hTheme,   
    CDC* pDC,   
    int iPartId,   
    int iStateId,   
    CString strText,   
    CRect rect,   
    DWORD dwFlags,   
    int nGlowSize = 0,   
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `hTheme`  
 창의 테마 데이터에 대한 핸드 또는 `NULL`입니다. 이 매개 변수가 `NULL` 이 아니고 테마가 지원되는 경우 프레임워크는 지정된 테마를 사용하여 텍스트를 그립니다. 그렇지 않으면 테마를 사용하여 텍스트를 그리지 않습니다.  
  
 [를 만들려면](http://msdn.microsoft.com/library/windows/desktop/bb759821) OpenThemeData `HTHEME`메서드를 사용합니다.  
  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `iPartId`  
 원하는 텍스트 모양이 있는 컨트롤 파트입니다. 자세한 내용은 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)에 설명된 표의 파트 열을 참조하세요. 이 값이 0이면 텍스트가 기본 글꼴로 그려지거나 장치 컨텍스트로 선택된 글꼴로 그려집니다.  
  
 [in] `iStateId`  
 원하는 텍스트 모양이 있는 컨트롤 상태입니다. 자세한 내용은 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)에 설명된 표의 상태 열을 참조하세요.  
  
 [in] `strText`  
 그릴 텍스트입니다.  
  
 [in] `rect`  
 지정된 텍스트가 그려지는 영역의 경계입니다.  
  
 [in] `dwFlags`  
 지정된 텍스트가 그려지는 방식을 지정하는 플래그의 비트 조합(OR)입니다.  
  
 경우는 `hTheme` 매개 변수는 `NULL` 테마 되지 지원 하 여 사용 하는 경우 또는 `nFormat` 의 매개 변수는 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) 메서드 유효한 플래그를 설명 합니다. 테마가 지원되는 경우에는 `dwFlags` DrawThemeTextEx [메서드의](http://msdn.microsoft.com/library/windows/desktop/bb773317) 매개 변수가 유효한 플래그를 설명합니다.  
  
 [in] `nGlowSize`  
 지정된 텍스트를 그리기 전에 배경에 그려지는 글로우 효과의 크기입니다. 기본값은 0입니다.  
  
 [in] `clrText`  
 지정된 텍스트가 그려지는 색입니다. 기본값은 기본 색입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`테마는 지정 된 텍스트를 그리는 데 사용 되는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 테마는 응용 프로그램의 비주얼 스타일을 정의합니다. `hTheme` 매개 변수가 `NULL`인 경우, [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) 메서드가 지원되지 않는 경우 또는 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션을 사용할 수 없는 경우에는 텍스트를 그리는 데 테마가 사용되지 않습니다.  
  
### <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="enableaccessibilitysupport"></a>Afx_global_data:: enableaccessibilitysupport
Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `bEnable`  
 내게 필요한 옵션 지원을 활성화하려면 `TRUE`로 설정하고 비활성화하려면 `FALSE`로 설정합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>설명  
 Active Accessibility는 프로그램의 방식을 향상시키는 COM 기반의 기술이고 Windows 운영 체제는 보조 기술 제품과 함께 작동합니다. 이는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 메서드를 제공합니다. 그러나 이제부터 Microsoft UI 자동화라고 하는 새로운 내게 필요한 옵션 모델을 사용할 수 있습니다. 두 기술을 비교를 참조 하십시오. [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)합니다.  
  
 사용 하 여는 [afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport) 메서드를 Microsoft Active Accessibility를 지원 설정 되어 있는지 확인 합니다.  
  
 
### <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)   
 [Afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport)

## <a name="excludetag"></a>Afx_global_data:: excludetag
지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `strBuffer`  
 텍스트 버퍼입니다.  
  
 [in] `lpszTag`  
 한 쌍의 태그 및 닫는 XML 태그의 이름입니다.  
  
 [out] `strTag`  
 이 메서드가 반환 될 때는 `strTag` 사이 있는 여는 태그와 닫는 XML 태그에서 명명 된 텍스트를 포함 하는 매개 변수는 `lpszTag` 매개 변수입니다. 결과에서 선행 또는 후행 공백이 잘립니다.  
  
 [in] `bIsCharsList`  
 `TRUE`이스케이프 문자에 대 한 기호를 변환 하는 `strTag` 실제 이스케이프 문자로; 매개 변수 `FALSE` 는 변환을 수행할 수 없습니다. 기본값은 `FALSE`합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>설명  
 XML 태그 쌍 태그 및 닫는 태그를 시작 및 실행 하는 지정 된 버퍼에서 텍스트의 끝을 나타내는 이름이 구성 됩니다. `strBuffer` 는 버퍼를 지정 하는 매개 변수 및 `lpszTag` 매개 변수 XML 태그의 이름을 지정 합니다.  
  
 다음 표에 지정 된 버퍼에서 이스케이프 문자 집합을 인코딩할 기호를 사용 합니다. 지정 `TRUE` 에 대 한는 `bIsCharsList` 의 기호를 변환 하는 매개 변수는 `strTag` 실제 이스케이프 문자에 대 한 매개 변수입니다. 다음 표에서 사용 하 여는 [_T()](../../c-runtime-library/data-type-mappings.md) 기호를 지정 하 고 문자열을 이스케이프 하는 매크로입니다.  
  
|기호|이스케이프 문자|  
|------------|----------------------|  
|_T ("\\\t")|_T("\t")|  
|_T ("\\\n")|_T("\n")|  
|_T ("\\\r")|_T("\r")|  
|_T ("\\\b")|_T("\b")|  
|_T("LT")|_T ("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="getcolor"></a>Afx_global_data:: getcolor
지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `nColor`  
 색을 검색 하는 사용자 인터페이스 요소를 지정 하는 값입니다. 유효한 값의 목록에 대 한 참조는 `nIndex` 의 매개 변수는 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) 메서드.  
  
### <a name="return-value"></a>반환 값  
 지정 된 사용자 인터페이스 요소의 RGB 색상 값입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="remarks"></a>설명  
 경우는 `nColor` 매개 변수가 범위를 벗어나면 반환 값은 0입니다. 0이 유효한 RGB 값 이기도 하기 때문에 시스템 색이 현재 운영 체제에서 지원 되는지 여부를 확인 하려면이 메서드를 사용할 수 없습니다. 대신를 사용 하 여는 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) 반환 하는 메서드 `NULL` 색이 지원 되지 않는 경우.  
  
### <a name="see-also"></a>참고 항목  

 [GetSysColor 함수](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA::GetDirect2dFactory
 글로벌 데이터에 저장 된 ID2D1Factory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리 생성에 성공 하면 또는 생성 하지 못한 경우 NULL 경우 ID2D1Factory 인터페이스 또는 현재 운영 체제에 대 한 포인터 D2D 지원이 필요는 없습니다.  
  
## <a name="gethandcursor"></a>Afx_global_data:: gethandcursor
식별자가 `IDC_HAND`인 손 모양의 미리 정의된 커서를 검색합니다.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
### <a name="return-value"></a>반환 값  
 손 모양 커서의 핸들입니다.  

## <a name="getnonclientmetrics"></a>Afx_global_data:: getnonclientmetrics
최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
### <a name="parameters"></a>매개 변수   
 [in, out] `info`  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) 최소화 되지 않은 창의 비클라이언트 영역와 관련 된 확장 가능한 메트릭을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
 
  
### <a name="see-also"></a>참고 항목   
 [NONCLIENTMETRICS 구조](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a>Afx_global_data:: gettextheight
 현재 글꼴에서 텍스트 문자의 높이를 검색합니다.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `bHorz`  
 `TRUE`텍스트를 가로로; 실행 될 때 문자의 높이 검색 하려면 `FALSE` 텍스트 실행을 세로로 하는 경우 문자의 높이 검색 하도록 합니다. 기본값은 `TRUE`입니다.  
  
### <a name="return-value"></a>반환 값  
 해당 디센더를 해당 어센더에서 측정 된 현재 글꼴의 높이입니다.  
  
## <a name="getwicfactory"></a>AFX_GLOBAL_DATA::GetWICFactory
글로벌 데이터에 저장 된 IWICImagingFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리 생성에 성공 하면 또는 생성 하지 못한 경우 NULL 경우 IWICImagingFactory 인터페이스 또는 현재 운영 체제에 대 한 포인터 WIC 지원이 필요는 없습니다.  
  
## <a name="getwritefactory"></a>AFX_GLOBAL_DATA::GetWriteFactory
글로벌 데이터에 저장 된 IDWriteFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리 생성에 성공 하면 또는 생성 하지 못한 경우 NULL 경우 IDWriteFactory 인터페이스 또는 현재 운영 체제에 대 한 포인터 DirectWrite 지원이 필요는 없습니다.  
 
## <a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D
D2D, DirectWrite, 및 WIC 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>매개 변수   
 `d2dFactoryType`  
 D2d 및 생성 하는 리소스의 스레딩 모델입니다.  
  
 `writeFactoryType`  
 쓰기 팩터리 개체를 공유 또는 격리 됩니다 있는지 여부를 지정 하는 값  
  
### <a name="return-value"></a>반환 값  
 TRUE를 반환 하는 팩터리 했는데 intilalizrd, FALSE-그렇지 않은 경우  
  
## <a name="is32biticons"></a>Afx_global_data:: is32biticons
미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`32 비트를 미리 정의 된 아이콘 사용할 수 있습니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 `TRUE` 프레임 워크 지원 아이콘을 기본 제공 하는 32 비트, 및 16 비트 / 픽셀 이상의 운영 체제에서 지원 되는 경우 않으며 고대비에 이미지가 표시 되지 않는 경우.  
  
## <a name="isaccessibilitysupport"></a>Afx_global_data:: isaccessibilitysupport
Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.  
  
  
```  
BOOL IsAccessibilitySupport() const; 
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`내게 필요한 옵션 지원을 활성화 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Active Accessibility 했던 액세스할 수 있는 응용 프로그램을 만들기 위한 이전 솔루션입니다. Microsoft UI 자동화 보조 기술 제품의 요구를 해결 하기 위한 용도가 및 자동 테스트 도구는 Microsoft Windows에 대 한 새로운 접근성 모델로 합니다.   
  
 사용 하 여는 [afx_global_data:: enableaccessibilitysupport](#enableaccessibilitysupport) 메서드를 사용 하도록 설정 하거나 Active Accessibility를 지원 하지 않도록 설정 합니다.  
  

### <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2DInitialized
 D2D 초기화 되었는지 여부를 결정 합니다.  
  
  
```  
BOOL IsD2DInitialized() const; 
```  
  
### <a name="return-value"></a>반환 값  
 D2D 초기화 되었습니다. 그렇지 않으면 FALSE입니다.  
  
## <a name="isdwmcompositionenabled"></a>Afx_global_data:: isdwmcompositionenabled
Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션을 사용 하도록 설정 되지 않았으면, `FALSE`합니다.  
  
### <a name="see-also"></a>참고 항목    
 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="ishighcontrastmode"></a>Afx_global_data:: ishighcontrastmode
 이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.    
```  
BOOL IsHighContrastMode() const; 
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이미지 검정색 또는 흰색 고대비 모드에 현재 표시 되어 있으면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 검은색 고대비 모드에서 생성할 빛 가장자리 흰색 되며 백그라운드 검은색입니다. 흰색 고대비 모드에서 생성할 빛 가장자리는 검은색 및 배경은 흰색입니다.  
  
## <a name="iswindowslayersupportavailable"></a>Afx_global_data:: iswindowslayersupportavailable
운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const; 
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`계층된 창을 지원 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 계층된 창을 지 원하는 경우 *스마트 도킹* 표식 계층된 창을 사용 합니다.  
  
## <a name="m_busebuiltin32biticons"></a>Afx_global_data:: m_busebuiltin32biticons
프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE`프레임 워크; 32 비트 색 아이콘을 사용 하도록 지정 `FALSE` 더 낮은 해상도 아이콘을 지정 합니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자에는이 멤버를 초기화 합니다. `TRUE`합니다.  
  
 이 멤버는 응용 프로그램 시작 시 설정 되어야 합니다.  
  
## <a name="m_busesystemfont"></a>Afx_global_data:: m_busesystemfont
시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE`시스템 글꼴;을 사용 하도록 지정 그렇지 않으면 `FALSE`합니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자에는이 멤버를 초기화 합니다. `FALSE`합니다.  
  
 사용 하는 유일한 방법은 글꼴을 결정 하기 위해 프레임 워크에 대 한 않습니다이 멤버를 테스트 합니다. `AFX_GLOBAL_DATA::UpdateFonts` 메서드는 또한 기본 및 대체 글꼴을 메뉴, 도구 모음 및 리본에 적용할 수는 어떤 비주얼 스타일을 결정을 테스트 합니다.  
  
## <a name="m_hcurhand"></a>Afx_global_data:: m_hcurhand
손 모양 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="m_hcurstretch"></a>Afx_global_data:: m_hcurstretch
가로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="m_hcurstretchvert"></a>Afx_global_data:: m_hcurstretchvert
세로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="m_hicontool"></a>Afx_global_data:: m_hicontool
도구 아이콘에 대한 핸들을 저장합니다.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="m_nautohidetoolbarmargin"></a>Afx_global_data:: m_nautohidetoolbarmargin
도킹 창의 왼쪽 맨 왼쪽 autohide 도구 모음에서 오프셋을 지정합니다.  
  
  
```  
int  m_nAutoHideToolBarMargin;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀에이 멤버를 초기화 합니다.  
  
## <a name="m_nautohidetoolbarspacing"></a>Afx_global_data:: m_nautohidetoolbarspacing
자동 숨기기 도구 모음 사이의 간격을 지정합니다.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 14 픽셀이 멤버를 초기화 합니다.  
  
## <a name="m_ndragframethicknessdock"></a>Afx_global_data:: m_ndragframethicknessdock

도킹 된 상태를 표시 하는 데 사용 된 끌어서 프레임의 두께 지정 합니다.  
  
  
```  
int  m_nDragFrameThicknessDock;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자를 3 픽셀로이 멤버를 초기화 합니다.  
  
## <a name="m_ndragframethicknessfloat"></a>Afx_global_data:: m_ndragframethicknessfloat
부동 상태를 표시 하는 데 사용 된 끌어서 프레임의 두께 지정 합니다.  
  
  
```  
int  m_nDragFrameThicknessFloat;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀에이 멤버를 초기화 합니다.  
  
## <a name="onsettingchange"></a>Afx_global_data:: onsettingchange
데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.  
  
  
```  
void OnSettingChange();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자의 데스크톱의 특정 한 특성의 상태에 프레임 워크 변수를 설정합니다. 이 메서드는 작업 자동 숨기기 기능 표시줄, 메뉴 페이드 메뉴 애니메이션의 현재 상태를 검색 합니다.  
  
## <a name="registerwindowclass"></a>Afx_global_data:: registerwindowclass
지정된 MFC 창 클래스를 등록합니다.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `lpszClassNamePrefix`  
 등록 하는 창 클래스의 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 등록 된 클래스의 정규화 된 이름 그렇지 않은 경우는 [리소스 예외](http://msdn.microsoft.com/library/ddd99292-819b-4fa4-8371-b1954ed5856d)합니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 콜론으로 구분 된 목록입니다는 `lpszClassNamePrefix` 매개 변수 문자열 및 현재 핸들의 16 진수 텍스트로 표시 됩니다. 응용 프로그램 인스턴스; 응용 프로그램 커서 식별자가 IDC_ARROW; 화살표 커서를 및 배경 브러시입니다. MFC 창 클래스 등록 하는 방법에 대 한 자세한 내용은 참조 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)합니다.  
  
### <a name="see-also"></a>참고 항목    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a>Afx_global_data:: resume
 Windows 테마 및 비주얼 스타일을 지 원하는 메서드에 액세스 하는 내부 함수 포인터를 다시 초기화 합니다. 
  
  
```  
BOOL Resume();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다. 디버그 모드에서이 메서드는이 메서드는 성공 하는 경우 어설션 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 프레임 워크 받을 때 호출 됩니다는 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) 메시지입니다.  
  
## <a name="setlayeredattrib"></a>Afx_global_data:: setlayeredattrib
Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `hwnd`  
 계층화된 창을 처리합니다.  
  
 [in] `crKey`  
 투명 색상 키입니다는 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) 계층화 된 창을 구성 하려면 사용 합니다.  
  
 [in] `bAlpha`  
 계층화된 창의 불투명도를 기술하는 데 사용되는 알파 값입니다.  
  
 [in] `dwFlags`  
 사용할 메서드 매개 변수를 지정하는 플래그의 비트 조합(OR)입니다. `crKey` 매개 변수를 투명 색상으로 사용하려면 LWA_COLORKEY를 지정합니다. `bAlpha` 매개 변수를 사용해서 계층화된 창의 불투명도를 결정하려면 LWA_ALPHA를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.   
 
### <a name="see-also"></a>참고 항목   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="setmenufont"></a>Afx_global_data:: setmenufont
지정된 논리 글꼴을 만듭니다.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] `lpLogFont`  
 글꼴의 특성을 포함 하는 구조에 대 한 포인터입니다.  
  
 [in] `bHorz`  
 `TRUE`텍스트 가로; 실행 되도록 지정 하려면 `FALSE` 텍스트 세로 방향으로 실행 되도록 지정 하려면.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`이 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다. 디버그 모드에서이 메서드는이 메서드는 성공 하는 경우 어설션 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 가로 일반 글꼴는 밑줄이 그어진된 글꼴 만들고 굵은 글꼴을 사용 되는 기본 메뉴 항목 합니다. 이 메서드는 필요에 따라 정기적인 세로 방향 글꼴을 만듭니다. 논리 글꼴에 대 한 자세한 내용은 참조 [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect)합니다.  
  
## <a name="updatefonts"></a>Afx_global_data:: updatefonts
프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.  
  
  
```  
void UpdateFonts();
```  
  
### <a name="remarks"></a>설명  
 논리 글꼴에 대 한 자세한 내용은 참조 하십시오. `CFont::CreateFontIndirect`합니다.  
  
## <a name="updatesyscolors"></a>Afx_global_data:: updatesyscolors
프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="biswindows7"></a>Afx_global_data:: biswindows7
응용 프로그램에서 Windows 7 이상이 실행 되는지를 나타냅니다.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="clractivecaptiongradient"></a>Afx_global_data:: clractivecaptiongradient
활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="clrinactivecaptiongradient"></a>Afx_global_data:: clrinactivecaptiongradient
비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="getitaskbarlist"></a>Afx_global_data:: getitaskbarlist
만들고의 글로벌 데이터 저장에 대 한 포인터는 `ITaskBarList` 인터페이스입니다.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `ITaskbarList` 목록 개체 막대 작업 만들기 성공 하면 인터페이스 `NULL` 만들기가 실패 하거나 현재 운영 체제가 Windows 7 보다 작은 경우.  
  
## <a name="getitaskbarlist3"></a>Afx_global_data:: getitaskbarlist3
만들고의 글로벌 데이터 저장에 대 한 포인터는 `ITaskBarList3` 인터페이스입니다.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `ITaskbarList3` 목록 개체 막대 작업 만들기 성공 하면 인터페이스 `NULL` 만들기가 실패 하거나 현재 운영 체제가 Windows 7 보다 작은 경우.  
  
## <a name="getshellautohidebars"></a>Afx_global_data:: getshellautohidebars
셸 자동 숨기기 막대의 위치를 결정합니다.  
  
  
```  
int GetShellAutohideBars();
```  
  
### <a name="return-value"></a>반환 값  
 자동의 위치를 지정 하는 인코딩된 플래그와 함께 정수 값 모음을 숨깁니다. 다음 값을 결합할 수 있습니다: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT 합니다.  
  
## <a name="releasetaskbarrefs"></a>Afx_global_data:: releasetaskbarrefs
인터페이스를 통해 가져온 해제는 `GetITaskbarList` 및 `GetITaskbarList3` 메서드.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="shellcreateitemfromparsingname"></a>Afx_global_data:: shellcreateitemfromparsingname
구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
### <a name="parameters"></a>매개 변수   
 `pszPath`  
 [in] 표시 이름에 대 한 포인터입니다.  
  
 `pbc`  
 구문 분석 작업을 제어 하는 바인딩 컨텍스트에 대 한 포인터입니다.  
  
 `riid`  
 인터페이스 ID에 대 한 참조  
  
 `ppv`  
 [out] 이 함수를 반환 하는 경우에 요청 된 인터페이스 포인터를 포함 `riid`합니다. 일반적으로 `IShellItem` 또는 `IShellItem2`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 반환 그렇지 않으면 오류 값입니다.  

