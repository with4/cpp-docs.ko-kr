---
title: AFX_GLOBAL_DATA 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFX_GLOBAL_DATA
dev_langs:
- C++
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4885cf6e5ddbff939e3f8e6401bd23661f13e275
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337410"
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
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|ITaskBarList3 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|  
|[Afx_global_data:: getnonclientmetrics](#getnonclientmetrics)|최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.|  
|[Afx_global_data:: getshellautohidebars](#getshellautohidebars)|셸 자동 숨기기 막대의 위치를 결정합니다.|  
|[Afx_global_data:: gettextheight](#gettextheight)|현재 글꼴에서 텍스트 문자의 높이를 검색합니다.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|글로벌 데이터에 저장된 `IWICImagingFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|글로벌 데이터에 저장된 `IDWriteFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D`, `DirectWrite`및 `WIC` 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|  
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.|  
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
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: enableaccessibilitysupport](#enableaccessibilitysupport)|Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다. Active Accessibility는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 방법을 제공합니다.|  
|[Afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport)|Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: iswindowslayersupportavailable](#iswindowslayersupportavailable)|운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[Afx_global_data:: bisosalphablendingsupport](#bisosalphablendingsupport)|현재 운영 체제가 알파 혼합을 지원하는지 여부를 나타냅니다.|  
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|응용 프로그램이 Windows 7 운영 체제 이상에서 실행되고 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: clractivecaptiongradient](#clractivecaptiongradient)|활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[Afx_global_data:: clrinactivecaptiongradient](#clrinactivecaptiongradient)|비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.|  
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


## <a name="bisosalphablendingsupport"></a> Afx_global_data:: bisosalphablendingsupport
운영 체제가 알파 혼합을 지원 하는지 여부를 나타냅니다.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
### <a name="remarks"></a>설명  
 TRUE 이면 알파 혼합 지원 됩니다. 그렇지 않으면 FALSE입니다.  
  

## <a name="cleanup"></a> Afx_global_data:: cleanup
브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.  
  
  
```  
void CleanUp();
```  
## <a name="d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
### <a name="parameters"></a>매개 변수   
 *각도*  
 시계 방향 회전 각도 (도)에서입니다.  
  
 *center*  
 회전 하는 방법에 대 한 점입니다.  
  
 *행렬*  
 이 메서드는 반환 될 때 새 회전 변환을 포함 합니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않은 경우 성공 하면 s_ok이 고, 또는 오류 값을 반환 합니다.  
  
## <a name="drawparentbackground"></a> Afx_global_data:: drawparentbackground
지정된 영역에 컨트롤 부모의 배경을 그립니다.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *pWnd*  
 컨트롤의 창에 대한 포인터입니다.  
  
 [in] *pDC*  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] *lpRect*  
 그리는 영역 경계가 되는 사각형에 대한 포인터입니다. 기본값은 NULL입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
## <a name="drawtextonglass"></a> Afx_global_data:: drawtextonglass
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
 [in] *hTheme*  
 창의 테마 데이터를 처리 하 하거나 NULL 키를 누릅니다. 프레임 워크를 지정된 된 테마를 사용 하 여이 매개 변수가 NULL이 아니고 테마가 지원 되는 경우 텍스트를 그립니다. 그렇지 않으면 테마를 사용하여 텍스트를 그리지 않습니다.  
  
 사용 된 [OpenThemeData](http://msdn.microsoft.com/library/windows/desktop/bb759821) HTHEME를 만드는 방법.  
  
 [in] *pDC*  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] *iPartId*  
 원하는 텍스트 모양이 있는 컨트롤 파트입니다. 자세한 내용은 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)에 설명된 표의 파트 열을 참조하세요. 이 값이 0이면 텍스트가 기본 글꼴로 그려지거나 장치 컨텍스트로 선택된 글꼴로 그려집니다.  
  
 [in] *iStateId*  
 원하는 텍스트 모양이 있는 컨트롤 상태입니다. 자세한 내용은 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)에 설명된 표의 상태 열을 참조하세요.  
  
 [in] *strText*  
 그릴 텍스트입니다.  
  
 [in] *rect*  
 지정된 텍스트가 그려지는 영역의 경계입니다.  
  
 [in] *dwFlags*  
 지정된 텍스트가 그려지는 방식을 지정하는 플래그의 비트 조합(OR)입니다.  
  
 경우는 *hTheme* 매개 변수가 `NULL` 테마는 지원 되지 않으며 사용 하도록 설정 된 경우 또는 *nFormat* 의 매개 변수는 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) 메서드 유효한 설명 플래그입니다. 테마가 지원 되는 경우는 *dwFlags* 의 매개 변수를 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) 메서드 유효한 플래그를 설명 합니다.  
  
 [in] *nGlowSize*  
 지정된 텍스트를 그리기 전에 배경에 그려지는 글로우 효과의 크기입니다. 기본값은 0입니다.  
  
 [in] *clrText*  
 지정된 텍스트가 그려지는 색입니다. 기본값은 기본 색입니다.  
  
### <a name="return-value"></a>반환 값  
 테마를 지정된 된 텍스트를 그리는 데 사용 되는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 테마는 응용 프로그램의 비주얼 스타일을 정의합니다. 텍스트를 그리는 경우에 테마가 사용 되지 않습니다는 *hTheme* 매개 변수는 NULL 이거나 합니다 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) 메서드가 지원 되지 않습니다 이거나 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션을 사용 되지 않습니다.  
  
### <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [파트 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="enableaccessibilitysupport"></a> Afx_global_data:: enableaccessibilitysupport
Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *bEnable*  
 내게 필요한 옵션 지원을 사용 하도록 설정 내게 필요한 옵션 지원 기능을 해제 하려면 FALSE입니다. 기본값은 TRUE입니다.  
  
### <a name="remarks"></a>설명  
 Active Accessibility는 프로그램의 방식을 향상시키는 COM 기반의 기술이고 Windows 운영 체제는 보조 기술 제품과 함께 작동합니다. 이는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 메서드를 제공합니다. 그러나 이제부터 Microsoft UI 자동화라고 하는 새로운 내게 필요한 옵션 모델을 사용할 수 있습니다. 두 기술을 비교를 참조 하세요 [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)합니다.  
  
 사용 된 [afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport) Microsoft Active Accessibility 지원이 활성화 되어 있는지 여부를 결정 하는 방법입니다.  
  
 
### <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)   
 [Afx_global_data:: isaccessibilitysupport](#isaccessibilitysupport)

## <a name="excludetag"></a> Afx_global_data:: excludetag
지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *strBuffer*  
 텍스트 버퍼입니다.  
  
 [in] *lpszTag*  
 열고 닫는 XML 태그 쌍의 이름입니다.  
  
 [out] *strTag*  
 이 메서드가 반환 하는 경우는 *strTag* 사이 있는 여는 태그와 닫는 XML 태그에서 이름이 지정 된 텍스트를 포함 하는 매개 변수를 *lpszTag* 매개 변수입니다. 결과에서 선행 또는 후행 공백이 잘립니다.  
  
 [in] *bIsCharsList*  
 이스케이프 문자에 대 한 기호를 변환 하려면 true로 설정 합니다 *strTag* 실제 이스케이프 문자에 대 한 매개 변수 변환을 수행할 필요가 FALSE입니다. 기본값은 FALSE입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 성공 하는 경우 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 XML 태그 쌍을 열고 닫는 태그 시작 및 지정 된 버퍼에서 텍스트 실행의 끝을 나타내는 이름이 구성 됩니다. 합니다 *strBuffer* 매개 변수 버퍼를 지정 하며 *lpszTag* 매개 변수에서 XML 태그 이름을 지정 합니다.  
  
 다음 표에 지정된 된 버퍼에서 이스케이프 문자 집합을 인코딩할 기호를 사용 합니다. 에 대해 TRUE를 지정 합니다 *bIsCharsList* 기호를 변환 하는 매개 변수를 *strTag* 실제 이스케이프 문자에 대 한 매개 변수. 다음 테이블에서는 합니다 [_t](../../c-runtime-library/data-type-mappings.md) 기호를 지정 하 고 문자열을 이스케이프 하는 매크로입니다.  
  
|기호|이스케이프 문자|  
|------------|----------------------|  
|_T ("\\\t")|_T("\t")|  
|_T ("\\\n")|_T("\n")|  
|_T ("\\\r")|_T("\r")|  
|_T ("\\\b")|_T("\b")|  
|_T("LT")|_T ("\<")|  
|_T("GT")|_T("&GT;")|  
|_T("AMP")|_T("&AMP;")|  
  
## <a name="getcolor"></a> Afx_global_data:: getcolor
지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *nColor*  
 색을 검색 하는 사용자 인터페이스 요소를 지정 하는 값입니다. 유효한 값 목록을 참조 하세요. 합니다 *nIndex* 의 매개 변수를 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) 메서드.  
  
### <a name="return-value"></a>반환 값  
 지정 된 사용자 인터페이스 요소의 RGB 색 값입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="remarks"></a>설명  
 경우는 *nColor* 매개 변수가 범위를 벗어나면 반환 값은 0입니다. 0이 유효한 RGB 값도 이기 때문에 시스템 색이 현재 운영 체제에서 지원 되는지 여부를 확인 하려면이 메서드를 사용할 수 없습니다. 대신 합니다 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) 색이 지원 되지 않는 경우 NULL을 반환 하는 메서드.  
  
### <a name="see-also"></a>참고 항목  

 [GetSysColor 함수](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 글로벌 데이터에 저장 된 ID2D1Factory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리의 만들기 성공 하거나 만들 수 없는 경우 NULL 경우 ID2D1Factory 인터페이스 또는 현재 운영 체제에 대 한 포인터 D2D 지원이 필요가 없습니다.  
  
## <a name="gethandcursor"></a>  Afx_global_data:: gethandcursor
미리 정의 된 커서는 손 모양의 이며 식별자 IDC_HAND를 검색 합니다.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
### <a name="return-value"></a>반환 값  
 손 모양 커서의 핸들입니다.  

## <a name="getnonclientmetrics"></a> Afx_global_data:: getnonclientmetrics
최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
### <a name="parameters"></a>매개 변수   
 [out에서] *정보*  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) 최소화 되지 않은 창의 비클라이언트 영역을 사용 하 여 관련 확장성 메트릭을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
 
  
### <a name="see-also"></a>참고 항목   
 [NONCLIENTMETRICS 구조](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="gettextheight"></a> Afx_global_data:: gettextheight
 현재 글꼴에서 텍스트 문자의 높이를 검색합니다.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *bHorz*  
 텍스트를 가로로; 실행 될 때 문자의 높이 검색 하려면 TRUE 텍스트 세로 방향으로 실행 될 때 문자의 높이 검색 하려면 FALSE입니다. 기본값은 TRUE입니다.  
  
### <a name="return-value"></a>반환 값  
 해당 디센더를 해당 ascender에서 측정 된 현재 글꼴의 높이입니다.  
  
## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
글로벌 데이터에 저장 되는 IWICImagingFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리의 만들기 성공 하거나 만들 수 없는 경우 NULL 경우 IWICImagingFactory 인터페이스 또는 현재 운영 체제에 대 한 포인터 WIC 지원이 필요가 없습니다.  
  
## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
글로벌 데이터에 저장 된 IDWriteFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
### <a name="return-value"></a>반환 값  
 팩터리의 만들기 성공 하거나 만들 수 없는 경우 NULL 경우 IDWriteFactory 인터페이스 또는 현재 운영 체제에 대 한 포인터 DirectWrite 지원이 필요가 없습니다.  
 
## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D
D2D 고 DirectWrite, WIC 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>매개 변수   
 *d2dFactoryType*  
 D2d 및 리소스의 스레딩 모델을 만듭니다.  
  
 *writeFactoryType*  
 쓰기 팩터리 개체를 공유 또는 격리는 지 여부를 지정 하는 값  
  
### <a name="return-value"></a>반환 값  
 TRUE를 반환 하는 경우 팩터리 된 intilalizrd, FALSE-그렇지 않으면  
  
## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons
미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
### <a name="return-value"></a>반환 값  
 미리 정의 된 32 비트 아이콘이 지원 되 면 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 프레임 워크에서 아이콘을 기본 제공 하는 32 비트, 지 원하는 경우 16 비트 / 픽셀 이상의 운영 체제에서 지원 되는 경우 및 고대비에서 이미지 표시 되지 않으면 TRUE를 반환 합니다.  
  
## <a name="isaccessibilitysupport"></a> Afx_global_data:: isaccessibilitysupport
Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.  
  
  
```  
BOOL IsAccessibilitySupport() const; 
```  
  
### <a name="return-value"></a>반환 값  
 Accessibility 지원이 활성화 되 면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Active Accessibility에 내게 필요한 옵션이 응용 프로그램에 대 한 이전 솔루션 이었습니다. Microsoft UI 자동화 보조 기술 제품의 요구를 해결 하기 위해 및 자동화 된 테스트 도구는 Microsoft Windows에 대 한 새로운 접근성 모델로 합니다.   
  
 사용 된 [afx_global_data:: enableaccessibilitysupport](#enableaccessibilitysupport) Active Accessibility 지원을 설정 또는 해제 방법입니다.  
  

### <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)

## <a name="isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 D2D 초기화 되었는지 여부를 결정 합니다.  
  
  
```  
BOOL IsD2DInitialized() const; 
```  
  
### <a name="return-value"></a>반환 값  
 D2D 초기화 되었습니다. 그렇지 않으면 FALSE입니다.  
  
## <a name="isdwmcompositionenabled"></a> Afx_global_data:: isdwmcompositionenabled
Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션이 되 고, 그렇지 않으면 FALSE입니다.  
  
### <a name="see-also"></a>참고 항목    
 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="ishighcontrastmode"></a> Afx_global_data:: ishighcontrastmode
 이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.    
```  
BOOL IsHighContrastMode() const; 
```  
  
### <a name="return-value"></a>반환 값  
 이미지 검정 또는 흰색 고대비 모드에서 현재 표시 되어 있으면 TRUE입니다. 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 검은색 고대비 모드에서 광원 가장자리 흰색 되며 배경이 검은색입니다. 흰색 고대비 모드에서 광원 가장자리는 검은색 및 배경이 흰색입니다.  
  
## <a name="iswindowslayersupportavailable"></a> Afx_global_data:: iswindowslayersupportavailable
운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const; 
```  
  
### <a name="return-value"></a>반환 값  
 계층화 된 창이 지원 되 면 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 계층화 된 창이 지원 되 면 *스마트 도킹* 표식 계층화 된 창을 사용 합니다.  
  
## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
### <a name="remarks"></a>설명  
 TRUE 사용 하도록 지정 하는 프레임 워크 32 비트 컬러 아이콘; FALSE 낮은 해상도 아이콘을 지정합니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자로이 멤버를 초기화 합니다.  
  
 응용 프로그램 시작 시이 멤버를 설정 해야 합니다.  
  
## <a name="m_busesystemfont"></a> Afx_global_data:: m_busesystemfont
시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
### <a name="remarks"></a>설명  
 TRUE는 시스템 글꼴;를 사용 하도록 지정 그렇지 않으면 FALSE입니다. `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자에 FALSE로이 멤버를 초기화 합니다.  
  
 이 멤버를 테스트 하는를 사용 하 여 글꼴을 결정 하기 위해 프레임 워크에 대 한 유일한 방법은 아닙니다. `AFX_GLOBAL_DATA::UpdateFonts` 메서드는 또한 기본 및 대체 글꼴 메뉴, 도구 모음 및 리본에 적용할 수 있는 비주얼 스타일 확인을 테스트 합니다.  
  
## <a name="m_hcurhand"></a> Afx_global_data:: m_hcurhand
손 모양 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="m_hcurstretch"></a> Afx_global_data:: m_hcurstretch
가로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="m_hcurstretchvert"></a> Afx_global_data:: m_hcurstretchvert
세로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="m_hicontool"></a> Afx_global_data:: m_hicontool
도구 아이콘에 대한 핸들을 저장합니다.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="m_nautohidetoolbarmargin"></a> Afx_global_data:: m_nautohidetoolbarmargin
맨 왼쪽 자동 숨기기 도구 모음에서 도킹 모음의 왼쪽 까지의 오프셋을 지정합니다.  
  
  
```  
int  m_nAutoHideToolBarMargin;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀이 멤버를 초기화 합니다.  
  
## <a name="m_nautohidetoolbarspacing"></a> Afx_global_data:: m_nautohidetoolbarspacing
자동 숨기기 도구 모음 사이의 간격을 지정합니다.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 14 픽셀이 멤버를 초기화 합니다.  
  
## <a name="m_ndragframethicknessdock"></a> Afx_global_data:: m_ndragframethicknessdock

도킹된 된 상태를 나타내는 데 사용 되는 끌기 프레임의 두께 지정 합니다.  
  
  
```  
int  m_nDragFrameThicknessDock;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자를 3 픽셀로이 멤버를 초기화 합니다.  
  
## <a name="m_ndragframethicknessfloat"></a> Afx_global_data:: m_ndragframethicknessfloat
부동 상태를 나타내는 데 사용 되는 끌기 프레임의 두께 지정 합니다.  
  
  
```  
int  m_nDragFrameThicknessFloat;  
```  
  
### <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀이 멤버를 초기화 합니다.  
  
## <a name="onsettingchange"></a> Afx_global_data:: onsettingchange
데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.  
  
  
```  
void OnSettingChange();
```  
  
### <a name="remarks"></a>설명  
 이 메서드는 사용자의 데스크톱의 특정 한 특성의 상태를 framework 변수를 설정합니다. 이 메서드는 작업 표시줄 자동 숨기기 기능, 메뉴 페이드 메뉴 애니메이션의 현재 상태를 검색합니다.  
  
## <a name="registerwindowclass"></a> Afx_global_data:: registerwindowclass
지정된 MFC 창 클래스를 등록합니다.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *lpszClassNamePrefix*  
 등록 창 클래스의 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 등록 된 클래스의 정규화 된 이름 그렇지 않은 경우는 [리소스 예외](http://msdn.microsoft.com/library/ddd99292-819b-4fa4-8371-b1954ed5856d)합니다.  
  
### <a name="remarks"></a>설명  
 반환 값은 콜론으로 구분 된 목록을 합니다 *lpszClassNamePrefix* 매개 변수 문자열 및 현재 응용 프로그램 인스턴스의; 핸들의 16 진수 텍스트 표현을 화살표는 응용 프로그램 커서 식별자가 IDC_ARROW; 커서 및 배경 브러시입니다. MFC 창 클래스 등록에 대 한 자세한 내용은 참조 하십시오 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)합니다.  
  
### <a name="see-also"></a>참고 항목    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="resume"></a> Afx_global_data:: resume
 Windows 테마 및 비주얼 스타일을 지 원하는 메서드에 액세스 하는 내부 함수 포인터를 다시 초기화 합니다. 
  
  
```  
BOOL Resume();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다. 디버그 모드에서이 메서드는이 메서드가 성공한 경우 어설션 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 프레임 워크를 받을 때 호출 되는 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) 메시지입니다.  
  
## <a name="setlayeredattrib"></a> Afx_global_data:: setlayeredattrib
Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *hwnd*  
 계층화된 창을 처리합니다.  
  
 [in] *crKey*  
 투명색 키를 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) 계층화 된 창을 구성를 사용 하 여 합니다.  
  
 [in] *bAlpha*  
 계층화된 창의 불투명도를 기술하는 데 사용되는 알파 값입니다.  
  
 [in] *dwFlags*  
 사용할 메서드 매개 변수를 지정하는 플래그의 비트 조합(OR)입니다. 사용 하려면 LWA_COLORKEY를 지정 합니다 *crKey* 투명 색상으로 매개 변수입니다. LWA_ALPHA를 지정 합니다 *bAlpha* 계층화 된 창의 불투명도 결정 하는 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다.   
 
### <a name="see-also"></a>참고 항목   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="setmenufont"></a> Afx_global_data:: setmenufont
지정된 논리 글꼴을 만듭니다.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수   
 [in] *lpLogFont*  
 글꼴의 특성을 포함 하는 구조체에 대 한 포인터입니다.  
  
 [in] *bHorz*  
 텍스트를 가로로; 실행 되도록 지정. 텍스트를 세로 방향으로 실행 되도록 지정 하려면 FALSE입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 TRUE입니다. 그렇지 않으면 FALSE입니다. 디버그 모드에서이 메서드는이 메서드가 성공한 경우 어설션 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 밑줄된 글꼴 가로 일반 글꼴, 만들고 있는 굵은 글꼴 사용 되는 기본 메뉴 항목 합니다. 이 메서드는 필요에 따라 일반 세로 방향 글꼴을 만듭니다. 논리 글꼴에 대 한 자세한 내용은 참조 하세요. [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect)합니다.  
  
## <a name="updatefonts"></a> Afx_global_data:: updatefonts
프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.  
  
  
```  
void UpdateFonts();
```  
  
### <a name="remarks"></a>설명  
 논리 글꼴에 대 한 자세한 내용은 참조 하세요. `CFont::CreateFontIndirect`합니다.  
  
## <a name="updatesyscolors"></a> Afx_global_data:: updatesyscolors
프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7
Windows 7 이상 응용 프로그램 실행 되는지를 나타냅니다.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="clractivecaptiongradient"></a> Afx_global_data:: clractivecaptiongradient
활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="clrinactivecaptiongradient"></a> Afx_global_data:: clrinactivecaptiongradient
비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="getitaskbarlist"></a> Afx_global_data:: getitaskbarlist
만들고 글로벌 데이터에 대 한 포인터를 저장 합니다 `ITaskBarList` 인터페이스입니다.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 `ITaskbarList` 목록 개체 모음 작업 만들기에 성공 하면; 인터페이스 현재 운영 체제가 Windows 7 보다 작은 경우 또는 만들 수 없는 경우 NULL입니다.  
  
## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3
만들고 글로벌 데이터에 대 한 포인터를 저장 합니다 `ITaskBarList3` 인터페이스입니다.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 `ITaskbarList3` 목록 개체 모음 작업 만들기에 성공 하면; 인터페이스 현재 운영 체제가 Windows 7 보다 작은 경우 또는 만들 수 없는 경우 NULL입니다.  
  
## <a name="getshellautohidebars"></a> Afx_global_data:: getshellautohidebars
셸 자동 숨기기 막대의 위치를 결정합니다.  
  
  
```  
int GetShellAutohideBars();
```  
  
### <a name="return-value"></a>반환 값  
 자동 위치를 지정 하는 인코딩된 플래그를 사용 하 여 정수 값 숨기기 막대입니다. 다음 값을 결합할 수 있습니다: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT AFX_AUTOHIDE_RIGHT 합니다.  
  
## <a name="releasetaskbarrefs"></a> Afx_global_data:: releasetaskbarrefs
통해 얻은 인터페이스를 해제 합니다 `GetITaskbarList` 고 `GetITaskbarList3` 메서드.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="shellcreateitemfromparsingname"></a> Afx_global_data:: shellcreateitemfromparsingname
구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
### <a name="parameters"></a>매개 변수   
 *pszPath*  
 [in] 표시 이름에 대 한 포인터입니다.  
  
 *pbc*  
 구문 분석 작업을 제어 하는 바인딩 컨텍스트에 대 한 포인터입니다.  
  
 *riid*  
 인터페이스 ID에 대 한 참조  
  
 *ppv*  
 [out] 이 함수는 반환 될 때에서 요청 된 인터페이스 포인터를 포함 *riid*합니다. 일반적으로 `IShellItem` 또는 `IShellItem2`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고, 반환 그렇지 않으면 오류 값입니다.  

