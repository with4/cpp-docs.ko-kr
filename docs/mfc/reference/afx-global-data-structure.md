---
title: "AFX_GLOBAL_DATA 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GLOBAL_DATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFX_GLOBAL_DATA 구조체"
  - "AFX_GLOBAL_DATA 생성자"
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# AFX_GLOBAL_DATA 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
|[Afx_global_data:: cleanup](#afx_global_data__cleanup)|브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.|  
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#afx_global_data__d2d1makerotatematrix)|지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.|  
|[Afx_global_data:: drawparentbackground](#afx_global_data__drawparentbackground)|지정된 영역에 컨트롤 부모의 배경을 그립니다.|  
|[Afx_global_data:: drawtextonglass](#afx_global_data__drawtextonglass)|지정된 테마의 비주얼 스타일로 지정된 텍스트를 그립니다.|  
|[Afx_global_data:: excludetag](#afx_global_data__excludetag)|지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.|  
|[Afx_global_data:: getcolor](#afx_global_data__getcolor)|지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.|  
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#afx_global_data__getdirect2dfactory)|글로벌 데이터에 저장된 `ID2D1Factory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[Afx_global_data:: gethandcursor](#afx_global_data__gethandcursor)|식별자가 `IDC_HAND`인 손 모양의 미리 정의된 커서를 검색합니다.|  
|[Afx_global_data:: getitaskbarlist](#afx_global_data__getitaskbarlist)|ITaskBarList 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|  
|[Afx_global_data:: getitaskbarlist3](#afx_global_data__getitaskbarlist3)|ITaskBarList3 인터페이스에 대한 포인터를 만들고 글로벌 데이터에 저장합니다.|  
|[Afx_global_data:: getnonclientmetrics](#afx_global_data__getnonclientmetrics)|최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.|  
|[Afx_global_data:: getshellautohidebars](#afx_global_data__getshellautohidebars)|셸 자동 숨기기 막대의 위치를 결정합니다.|  
|[Afx_global_data:: gettextheight](#afx_global_data__gettextheight)|현재 글꼴에서 텍스트 문자의 높이를 검색합니다.|  
|[AFX_GLOBAL_DATA::GetWICFactory](#afx_global_data__getwicfactory)|글로벌 데이터에 저장된 `IWICImagingFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::GetWriteFactory](#afx_global_data__getwritefactory)|글로벌 데이터에 저장된 `IDWriteFactory` 인터페이스로 포인터를 반환합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|`D2D`, `DirectWrite`및 `WIC` 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.|  
|[Afx_global_data:: is32biticons](#afx_global_data__is32biticons)|미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.|  
|[AFX_GLOBAL_DATA::IsD2DInitialized](#afx_global_data__isd2dinitialized)|`D2D` 의 초기화 여부를 확인합니다.|  
|[Afx_global_data:: isdwmcompositionenabled](#afx_global_data__isdwmcompositionenabled)|Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) 메서드를 호출하는 간단한 방법을 제공합니다.|  
|[Afx_global_data:: ishighcontrastmode](#afx_global_data__ishighcontrastmode)|이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.|  
|[Afx_global_data:: onsettingchange](#afx_global_data__onsettingchange)|데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.|  
|[Afx_global_data:: registerwindowclass](#afx_global_data__registerwindowclass)|지정된 MFC 창 클래스를 등록합니다.|  
|[Afx_global_data:: releasetaskbarrefs](#afx_global_data__releasetaskbarrefs)|GetITaskbarList 및 GetITaskbarList3 메서드를 통해 얻은 인터페이스를 해제합니다.|  
|[Afx_global_data:: resume](#afx_global_data__resume)|Windows [테마 및 비주얼 스타일](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)을 지원하는 메서드에 액세스하는 내부 함수 포인터를 다시 초기화합니다.|  
|[Afx_global_data:: setlayeredattrib](#afx_global_data__setlayeredattrib)|Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) 메서드를 호출하는 간단한 방법을 제공합니다.|  
|[Afx_global_data:: setmenufont](#afx_global_data__setmenufont)|지정된 논리 글꼴을 만듭니다.|  
|[Afx_global_data:: shellcreateitemfromparsingname](#afx_global_data__shellcreateitemfromparsingname)|구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.|  
|[Afx_global_data:: updatefonts](#afx_global_data__updatefonts)|프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.|  
|[Afx_global_data:: updatesyscolors](#afx_global_data__updatesyscolors)|프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: enableaccessibilitysupport](#afx_global_data__enableaccessibilitysupport)|Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다. Active Accessibility는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 방법을 제공합니다.|  
|[Afx_global_data:: isaccessibilitysupport](#afx_global_data__isaccessibilitysupport)|Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: iswindowslayersupportavailable](#afx_global_data__iswindowslayersupportavailable)|운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[Afx_global_data:: bisosalphablendingsupport](#afx_global_data__bisosalphablendingsupport)|현재 운영 체제가 알파 혼합을 지원하는지 여부를 나타냅니다.|  
|[Afx_global_data:: biswindows7](#afx_global_data__biswindows7)|응용 프로그램이 Windows 7 운영 체제 이상에서 실행되고 있는지 여부를 나타냅니다.|  
|[Afx_global_data:: clractivecaptiongradient](#afx_global_data__clractivecaptiongradient)|활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[Afx_global_data:: clrinactivecaptiongradient](#afx_global_data__clrinactivecaptiongradient)|비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.|  
|[Afx_global_data:: m_busebuiltin32biticons](#afx_global_data__m_busebuiltin32biticons)|프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.|  
|[Afx_global_data:: m_busesystemfont](#afx_global_data__m_busesystemfont)|시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.|  
|[Afx_global_data:: m_hcurhand](#afx_global_data__m_hcurhand)|손 모양 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hcurstretch](#afx_global_data__m_hcurstretch)|가로 늘이기 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hcurstretchvert](#afx_global_data__m_hcurstretchvert)|세로 늘이기 커서에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_hicontool](#afx_global_data__m_hicontool)|도구 아이콘에 대한 핸들을 저장합니다.|  
|[Afx_global_data:: m_nautohidetoolbarmargin](#afx_global_data__m_nautohidetoolbarmargin)|맨 왼쪽 자동 숨기기 도구 모음에서 도킹 모음의 왼쪽까지의 오프셋을 지정합니다.|  
|[Afx_global_data:: m_nautohidetoolbarspacing](#afx_global_data__m_nautohidetoolbarspacing)|자동 숨기기 도구 모음 사이의 간격을 지정합니다.|  
|[Afx_global_data:: m_ndragframethicknessdock](#afx_global_data__m_ndragframethicknessdock)|도킹된 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|  
|[Afx_global_data:: m_ndragframethicknessfloat](#afx_global_data__m_ndragframethicknessfloat)|부동 상태를 전달하는 데 사용되는 끌기 프레임의 두께를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `AFX_GLOBAL_DATA` 구조에서 대부분의 데이터는 응용 프로그램 시작 시 초기화됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [AFX_GLOBAL_DATA](../../mfc/reference/afx-global-data-structure.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxglobals.h  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


## <a name="a-nameafxglobaldatabisosalphablendingsupporta-afxglobaldatabisosalphablendingsupport"></a><a name="afx_global_data__bisosalphablendingsupport"></a> Afx_global_data:: bisosalphablendingsupport
운영 체제 알파 혼합을 지원 하는지 여부를 나타냅니다.  
  
  
```  
BOOL  bIsOSAlphaBlendingSupport;  
```  
  
## <a name="remarks"></a>설명  
 `TRUE` 알파 혼합은 지원; 나타냅니다. 그렇지 않으면 `FALSE`합니다.  
  

## <a name="a-nameafxglobaldatacleanupa-afxglobaldatacleanup"></a><a name="afx_global_data__cleanup"></a> Afx_global_data:: cleanup
브러시, 글꼴 및 DLL 등 프레임워크에 의해 할당되는 리소스를 해제합니다.  
  
  
```  
void CleanUp();
```  
## <a name="a-nameafxglobaldatad2d1makerotatematrixa-afxglobaldatad2d1makerotatematrix"></a><a name="afx_global_data__d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
지정된 점을 기준으로 지정된 각도만큼 회전하는 회전 변환을 만듭니다.  
  
  
```  
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,  
    D2D1_POINT_2F center,  
    D2D1_MATRIX_3X2_F *matrix);
```  
  
#### <a name="parameters"></a>매개 변수  
 `angle`  
 시계 방향으로 회전 각도도 합니다.  
  
 `center`  
 회전 하는 방법에 대 한 지점입니다.  
  
 `matrix`  
 이 메서드가 반환 하는 경우에 새 회전 변환을 포함 되어 있습니다. 이 매개 변수에 대 한 저장소를 할당 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 또는 오류 값을 그렇지 않은 경우에 반환 합니다.  
  
## <a name="a-nameafxglobaldatadrawparentbackgrounda-afxglobaldatadrawparentbackground"></a><a name="afx_global_data__drawparentbackground"></a> Afx_global_data:: drawparentbackground
지정된 영역에 컨트롤 부모의 배경을 그립니다.  
  
  
```  
BOOL DrawParentBackground(
    CWnd* pWnd,   
    CDC* pDC,   
    LPRECT lpRect = NULL);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 컨트롤의 창에 대한 포인터입니다.  
  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `lpRect`  
 그리는 영역 경계가 되는 사각형에 대한 포인터입니다. 기본값은 `NULL`입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
## <a name="a-nameafxglobaldatadrawtextonglassa-afxglobaldatadrawtextonglass"></a><a name="afx_global_data__drawtextonglass"></a> Afx_global_data:: drawtextonglass
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
  
#### <a name="parameters"></a>매개 변수  
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
  
 하는 경우는 `hTheme` 매개 변수는 `NULL` 테마 지원 및 사용 하도록 설정 하지 않을 경우 또는 `nFormat` 의 매개 변수는 [CDC::DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext) 메서드 유효한 플래그에 설명 합니다. 테마가 지원되는 경우에는 `dwFlags` DrawThemeTextEx [메서드의](http://msdn.microsoft.com/library/windows/desktop/bb773317) 매개 변수가 유효한 플래그를 설명합니다.  
  
 [in] `nGlowSize`  
 지정된 텍스트를 그리기 전에 배경에 그려지는 글로우 효과의 크기입니다. 기본값은 0입니다.  
  
 [in] `clrText`  
 지정된 텍스트가 그려지는 색입니다. 기본값은 기본 색입니다.  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 테마는 지정 된 텍스트를 그리는 데 사용 되는 경우 그렇지 않으면 `FALSE`합니다.  
  
## <a name="remarks"></a>설명  
 테마는 응용 프로그램의 비주얼 스타일을 정의합니다. `hTheme` 매개 변수가 `NULL`인 경우, [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317) 메서드가 지원되지 않는 경우 또는 [바탕 화면 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션을 사용할 수 없는 경우에는 텍스트를 그리는 데 테마가 사용되지 않습니다.  
  
 
## <a name="see-also"></a>참고 항목  
 [AFX_GLOBAL_DATA 구조체](../../mfc/reference/afx-global-data-structure.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [부분 및 상태](http://msdn.microsoft.com/library/windows/desktop/bb773210)   
 [CDC::DrawText](../../mfc/reference/cdc-class.md#cdc__drawtext)   
 [DrawThemeTextEx](http://msdn.microsoft.com/library/windows/desktop/bb773317)   
 [데스크톱 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataenableaccessibilitysupporta-afxglobaldataenableaccessibilitysupport"></a><a name="afx_global_data__enableaccessibilitysupport"></a> Afx_global_data:: enableaccessibilitysupport
Microsoft Active Accessibility 지원을 사용하거나 사용하지 않도록 설정합니다.  
  
  
```  
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
내게 필요한 옵션 지원을 활성화하려면  `TRUE`로 설정하고 비활성화하려면 `FALSE`로 설정합니다. 기본값은 `TRUE`입니다.  
  
## <a name="remarks"></a>설명  
 Active Accessibility는 프로그램의 방식을 향상시키는 COM 기반의 기술이고 Windows 운영 체제는 보조 기술 제품과 함께 작동합니다. 이는 사용자 인터페이스 요소에 대한 정보를 노출하기 위한 신뢰할 수 있는 메서드를 제공합니다. 그러나 이제부터 Microsoft UI 자동화라고 하는 새로운 내게 필요한 옵션 모델을 사용할 수 있습니다. 두 가지 기술 비교를 참조 하십시오. [UI 자동화 및 Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)합니다.  
  
 사용 하는 [afx_global_data:: isaccessibilitysupport](#afx_global_data__IsAccessibilitySupport.md) Microsoft Active Accessibility 지원이 활성화 되어 있는지 여부를 결정할 수 있습니다.  
  
 
## <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)   
 [Afx_global_data:: isaccessibilitysupport](#afx_global_data__IsAccessibilitySupport.md)

## <a name="a-nameafxglobaldataexcludetaga-afxglobaldataexcludetag"></a><a name="afx_global_data__excludetag"></a> Afx_global_data:: excludetag
지정된 버퍼에서 지정된 XML 태그 쌍을 제거합니다.  
  
  
```  
BOOL ExcludeTag(
    CString& strBuffer,  
    LPCTSTR lpszTag,  
    CString& strTag,  
    BOOL bIsCharsList = FALSE);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `strBuffer`  
 텍스트의 버퍼입니다.  
  
 [in] `lpszTag`  
 왼쪽 괄호와 닫는 XML 태그 쌍의 이름입니다.  
  
 [out] `strTag`  
 이 메서드는 `strTag` 사이 있는 태그와 닫는 XML 태그에서 명명 된 텍스트를 포함 하는 매개 변수는 `lpszTag` 매개 변수입니다. 결과에서 모든 선행 또는 후행 공백이 잘립니다.  
  
 [in] `bIsCharsList`  
 `TRUE` 이스케이프 문자에 대 한 기호를 변환 하는 `strTag` 매개 변수를 실제 이스케이프 문자로; `FALSE` 변환을 수행 하려고 하지 않습니다. 기본값은 `FALSE`합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
## <a name="remarks"></a>설명  
 XML 태그 쌍이 있는 태그 및 닫는 태그를 시작 및 실행 하는 지정 된 버퍼에서 텍스트의 끝을 나타내는 명명 된 구성 됩니다.  `strBuffer` 는 버퍼를 지정 하는 매개 변수 및 `lpszTag` 매개 변수는 XML 태그의 이름을 지정 합니다.  
  
 다음 표에 지정된 된 버퍼에서 이스케이프 문자 집합을 인코딩할 기호를 사용 합니다. 지정 `TRUE` 에 대 한는 `bIsCharsList` 의 기호를 변환 하려면 매개 변수는 `strTag` 실제 이스케이프 문자에 대 한 매개 변수입니다. 다음 표에서 사용 하는 [_T()](../../c-runtime-library/data-type-mappings.md) 매크로 기호를 지정 하 여 문자열을 이스케이프 합니다.  
  
|기호|이스케이프 문자|  
|------------|----------------------|  
|_T("\\\t")|_T("\t")|  
|_T("\\\n")|_T("\n")|  
|_T("\\\r")|_T("\r")|  
|_T("\\\b")|_T("\b")|  
|_T("LT")|_T("\<")|  
|_T("GT")|_T(">")|  
|_T("AMP")|_T("&")|  
  
## <a name="a-nameafxglobaldatagetcolora-afxglobaldatagetcolor"></a><a name="afx_global_data__getcolor"></a> Afx_global_data:: getcolor
지정된 사용자 인터페이스 요소의 현재 색을 검색합니다.  
  
  
```  
COLORREF GetColor(int nColor);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `nColor`  
 색을 검색 하는 사용자 인터페이스 요소를 지정 하는 값입니다. 유효한 값의 목록에 대 한 참조는 `nIndex` 의 매개 변수는 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) 메서드.  
  
## <a name="return-value"></a>반환 값  
 지정 된 사용자 인터페이스 요소의 RGB 색상 값입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
## <a name="remarks"></a>설명  
 하는 경우는 `nColor` 매개 변수가 범위를 벗어나면 반환 값은 0입니다. 0이 유효한 RGB 값 이기도 하기 때문에 시스템 색이 현재 운영 체제에서 지원 되는지 여부를 확인 하려면이 메서드를 사용할 수 없습니다. 대신는 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927) 반환 하는 메서드 `NULL` 색 지원 되지 않는 경우.  
  
## <a name="see-also"></a>참고 항목  

 [GetSysColor 함수](http://msdn.microsoft.com/library/windows/desktop/ms724371)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [GetSysColorBrush](http://msdn.microsoft.com/library/windows/desktop/dd144927)

## <a name="a-nameafxglobaldatagetdirect2dfactorya-afxglobaldatagetdirect2dfactory"></a><a name="afx_global_data__getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory
 전역 데이터에 저장 되어 있는 ID2D1Factory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
ID2D1Factory* GetDirect2dFactory();
```  
  
## <a name="return-value"></a>반환 값  
 ID2D1Factory 인터페이스 팩터리 만들기 성공 하거나 만들기가 실패 하는 경우에 NULL 또는 현재 운영 체제에 대 한 포인터 D2D 지원이 필요는 없습니다.  
  
Afx_global_data:: gethandcursor 손 모양의 미리 정의 된 커서 검색 및 식별자를 갖는 `IDC_HAND`합니다.  
  
  
```  
HCURSOR GetHandCursor();
```  
  
## <a name="return-value"></a>반환 값  
 손 모양 커서의 핸들입니다.  

## <a name="a-nameafxglobaldatagetnonclientmetricsa-afxglobaldatagetnonclientmetrics"></a><a name="afx_global_data__getnonclientmetrics"></a> Afx_global_data:: getnonclientmetrics
최소화되지 않은 창의 비클라이언트 영역과 관련된 메트릭을 검색합니다.  
  
  
```  
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in, out] `info`  
 A [NONCLIENTMETRICS](http://msdn.microsoft.com/library/windows/desktop/ff729175) 최소화 되지 않은 창의 비클라이언트 영역와 관련 된 확장 가능한 메트릭이 포함 된 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다.  
 
  
## <a name="see-also"></a>참고 항목   
 [NONCLIENTMETRICS 구조](http://msdn.microsoft.com/library/windows/desktop/ff729175)

## <a name="a-nameafxglobaldatagettextheighta-afxglobaldatagettextheight"></a><a name="afx_global_data__gettextheight"></a> Afx_global_data:: gettextheight
 현재 글꼴에서 텍스트 문자의 높이를 검색합니다.  
  
  
```  
int GetTextHeight(BOOL bHorz = TRUE);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `bHorz`  
 `TRUE` 텍스트를 가로로; 실행 될 때 문자의 높이 검색 하려면 `FALSE` 텍스트를 세로로 실행 하는 경우 문자의 높이 검색 하도록 합니다. 기본값은 `TRUE`입니다.  
  
## <a name="return-value"></a>반환 값  
 해당 디센더 해당 어센더에서 측정 되는 현재 글꼴의 높이입니다.  
  
## <a name="a-nameafxglobaldatagetwicfactorya-afxglobaldatagetwicfactory"></a><a name="afx_global_data__getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory
전역 데이터에 저장 된 팩터리는 IWICImagingFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IWICImagingFactory* GetWICFactory();
```  
  
## <a name="return-value"></a>반환 값  
 IWICImagingFactory 인터페이스 팩터리 만들기 성공 하거나 만들기가 실패 하는 경우에 NULL 또는 현재 운영 체제에 대 한 포인터 WIC 지원이 필요는 없습니다.  
  
## <a name="a-nameafxglobaldatagetwritefactorya-afxglobaldatagetwritefactory"></a><a name="afx_global_data__getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory
전역 데이터에 저장 되어 있는 IDWriteFactory 인터페이스에 대 한 포인터를 반환 합니다. 인터페이스가 초기화되지 않은 경우 기본 매개 변수와 함께 인터페이스가 생성됩니다.  
  
  
```  
IDWriteFactory* GetWriteFactory();
```  
  
## <a name="return-value"></a>반환 값  
 IDWriteFactory 인터페이스 팩터리 만들기 성공 하거나 만들기가 실패 하는 경우에 NULL 또는 현재 운영 체제에 대 한 포인터 DirectWrite 지원이 필요는 없습니다.  
 
## <a name="a-nameafxglobaldatainitd2da-afxglobaldatainitd2d"></a><a name="afx_global_data__initd2d"></a> AFX_GLOBAL_DATA::InitD2D
D2D, DirectWrite, WIC 팩터리 팩터리를 초기화합니다. 주 창이 초기화되기 전에 이 메서드를 호출합니다.  
  
  
```  
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
#### <a name="parameters"></a>매개 변수  
 `d2dFactoryType`  
 D2d 및 리소스의 스레딩 모델을 만듭니다.  
  
 `writeFactoryType`  
 쓰기 팩터리 개체를 공유 하거나 격리 됩니다 있는지 여부를 지정 하는 값  
  
## <a name="return-value"></a>반환 값  
 TRUE를 반환 하는 팩터리 자가 경우 intilalizrd, FALSE-그렇지 않은 경우  
  
## <a name="a-nameafxglobaldatais32biticonsa-afxglobaldatais32biticons"></a><a name="afx_global_data__is32biticons"></a> Afx_global_data:: is32biticons
미리 정의된 32비트 아이콘이 지원되는지 여부를 나타냅니다.  
  
  
```  
BOOL Is32BitIcons() const;

 
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 미리 정의 된 32 비트 아이콘 지원 되 면 그렇지 않으면 `FALSE`합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드가 반환 `TRUE` 프레임 워크에 기본 제공 아이콘을 32 비트, 지 원하는 경우 16 비트 / 픽셀 이상의 운영 체제에서 지원 되는 경우 및 고대비에 이미지가 표시 되지 않는 경우.  
  
## <a name="a-nameafxglobaldataisaccessibilitysupporta-afxglobaldataisaccessibilitysupport"></a><a name="afx_global_data__isaccessibilitysupport"></a> Afx_global_data:: isaccessibilitysupport
Microsoft Active Accessibility 지원이 활성화되어 있는지 여부를 나타냅니다.  
  
  
```  
BOOL IsAccessibilitySupport() const;

 
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 내게 필요한 옵션 지원을 활성화 되 면 그렇지 않으면 `FALSE`합니다.  
  
## <a name="remarks"></a>설명  
 Microsoft Active Accessibility에 액세스할 수 있는 응용 프로그램을 만들기 위한 이전 솔루션 이었습니다. Microsoft UI 자동화는 Microsoft Windows에 대 한 새로운 내게 필요한 옵션 모델 및 보조 기술 제품의 요구를 해결 하며 자동화 된 테스트 도구입니다. 자세한 내용은 참조 [UI 자동화 및 Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)합니다.  
  
 사용 된 [afx_global_data:: enableaccessibilitysupport](#afx_global_data__EnableAccessibilitySupport.md) Active Accessibility 지원을 설정 또는 해제 하는 방법입니다.  
  

## <a name="see-also"></a>참고 항목  
 [UI 자동화 및 Microsoft Active Accessibility](../Topic/UI%20Automation%20and%20Microsoft%20Active%20Accessibility.md)

## <a name="a-nameafxglobaldataisd2dinitializeda-afxglobaldataisd2dinitialized"></a><a name="afx_global_data__isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized
 D2D 초기화 되었는지 여부를 결정 합니다.  
  
  
```  
BOOL IsD2DInitialized() const;

 
```  
  
## <a name="return-value"></a>반환 값  
 D2D 초기화 되었습니다. 그렇지 않으면 FALSE입니다.  
  
## <a name="a-nameafxglobaldataisdwmcompositionenableda-afxglobaldataisdwmcompositionenabled"></a><a name="afx_global_data__isdwmcompositionenabled"></a> Afx_global_data:: isdwmcompositionenabled
Windows [DwmIsCompositionEnabled](http://msdn.microsoft.com/library/windows/desktop/aa969518) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL IsDwmCompositionEnabled();
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 경우 [데스크톱 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) (DWM) 컴퍼지션이 사용 하도록 설정 하 고, 그렇지 않으면 `FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목    
 [데스크톱 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540)   
 [DWM 컴퍼지션 설정 및 제어](http://msdn.microsoft.com/library/windows/desktop/aa969538)

## <a name="a-nameafxglobaldataishighcontrastmodea-afxglobaldataishighcontrastmode"></a><a name="afx_global_data__ishighcontrastmode"></a> Afx_global_data:: ishighcontrastmode
 이미지가 현재 고대비로 표시되는지 여부를 나타냅니다.    
```  
BOOL IsHighContrastMode() const;

 
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 이미지 검정색 또는 흰색 고대비 모드에 현재 표시 된 경우 그렇지 않으면 `FALSE`합니다.  
  
## <a name="remarks"></a>설명  
 검은색 고대비 모드에서 조명 마주보는 지가 흰색 및 배경이 검은색입니다. 흰색 고대비 모드에서 조명 마주보는 가장자리는 검은색 및 배경을 흰색으로 표시 됩니다.  
  
## <a name="a-nameafxglobaldataiswindowslayersupportavailablea-afxglobaldataiswindowslayersupportavailable"></a><a name="afx_global_data__iswindowslayersupportavailable"></a> Afx_global_data:: iswindowslayersupportavailable
운영 체제가 계층화된 창을 지원하는지 여부를 나타냅니다.  
  
  
```  
BOOL IsWindowsLayerSupportAvailable() const;

 
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 계층화 된 창이 지원 되 면 그렇지 않으면 `FALSE`합니다.  
  
## <a name="remarks"></a>설명  
 계층화 된 창이 지원 되 면 *스마트 도킹* 표식 계층화 된 창을 사용 합니다.  
  
## <a name="a-nameafxglobaldatambusebuiltin32biticonsa-afxglobaldatambusebuiltin32biticons"></a><a name="afx_global_data__m_busebuiltin32biticons"></a> Afx_global_data:: m_busebuiltin32biticons
프레임워크가 미리 정의된 32비트 컬러 아이콘을 사용하는지, 아니면 더 낮은 해상도의 아이콘을 사용하는지를 나타냅니다.  
  
  
```  
BOOL  m_bUseBuiltIn32BitIcons;  
```  
  
## <a name="remarks"></a>설명  
 `TRUE` 프레임 워크 32 비트 컬러 아이콘을 사용 하도록 지정 `FALSE` 낮은 해상도 아이콘을 지정 합니다.  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자에이 멤버를 초기화 합니다. `TRUE`합니다.  
  
 이 멤버는 응용 프로그램 시작 시 설정 되어야 합니다.  
  
## <a name="a-nameafxglobaldatambusesystemfonta-afxglobaldatambusesystemfont"></a><a name="afx_global_data__m_busesystemfont"></a> Afx_global_data:: m_busesystemfont
시스템 글꼴이 메뉴, 도구 모음 및 리본에 사용되는지 여부를 나타냅니다.  
  
  
```  
BOOL m_bUseSystemFont;  
```  
  
## <a name="remarks"></a>설명  
 `TRUE` 시스템 글꼴;를 사용 하 여 지정 합니다. 그렇지 않으면 `FALSE`합니다.  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자에이 멤버를 초기화 합니다. `FALSE`합니다.  
  
 이 멤버를 테스트 하지는 유일한 방법은 글꼴을 결정 하는 프레임 워크에 대 한 사용 하도록 합니다.  `AFX_GLOBAL_DATA::UpdateFonts` 메서드는 또한 어떤 비주얼 스타일 메뉴, 도구 모음 및 리본에 적용 될 사용 가능한 지 결정 하는 기본 및 대체 글꼴이 테스트 합니다.  
  
## <a name="a-nameafxglobaldatamhcurhanda-afxglobaldatamhcurhand"></a><a name="afx_global_data__m_hcurhand"></a> Afx_global_data:: m_hcurhand
손 모양 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurHand;  
```  
  
## <a name="a-nameafxglobaldatamhcurstretcha-afxglobaldatamhcurstretch"></a><a name="afx_global_data__m_hcurstretch"></a> Afx_global_data:: m_hcurstretch
가로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretch;  
```  

## <a name="a-nameafxglobaldatamhcurstretchverta-afxglobaldatamhcurstretchvert"></a><a name="afx_global_data__m_hcurstretchvert"></a> Afx_global_data:: m_hcurstretchvert
세로 늘이기 커서에 대한 핸들을 저장합니다.  
  
  
```  
HCURSOR m_hcurStretchVert;  
```  
  
## <a name="a-nameafxglobaldatamhicontoola-afxglobaldatamhicontool"></a><a name="afx_global_data__m_hicontool"></a> Afx_global_data:: m_hicontool
도구 아이콘에 대한 핸들을 저장합니다.  
  
  
```  
HICON m_hiconTool;  
```  
## <a name="a-nameafxglobaldatamnautohidetoolbarmargina-afxglobaldatamnautohidetoolbarmargin"></a><a name="afx_global_data__m_nautohidetoolbarmargin"></a> Afx_global_data:: m_nautohidetoolbarmargin
도킹 창의 왼쪽 맨 왼쪽 자동 숨기기 도구 모음에서 오프셋을 지정합니다.  
  
  
```  
int   m_nAutoHideToolBarMargin;  
```  
  
## <a name="remarks"></a>설명  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀에이 멤버를 초기화 합니다.  
  
## <a name="a-nameafxglobaldatamnautohidetoolbarspacinga-afxglobaldatamnautohidetoolbarspacing"></a><a name="afx_global_data__m_nautohidetoolbarspacing"></a> Afx_global_data:: m_nautohidetoolbarspacing
자동 숨기기 도구 모음 사이의 간격을 지정합니다.  
  
  
```  
int   m_nAutoHideToolBarSpacing;  
```  
  
## <a name="remarks"></a>설명  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 14 픽셀에이 멤버를 초기화 합니다.  
  
## <a name="a-nameafxglobaldatamndragframethicknessdocka-afxglobaldatamndragframethicknessdock"></a><a name="afx_global_data__m_ndragframethicknessdock"></a> Afx_global_data:: m_ndragframethicknessdock

도킹 된 상태를 나타내는 데 사용 되는 끌어서 프레임의 두께 지정 합니다.  
  
  
```  
int   m_nDragFrameThicknessDock;  
```  
  
## <a name="remarks"></a>설명  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자를 3 픽셀로이 멤버를 초기화 합니다.  
  
## <a name="a-nameafxglobaldatamndragframethicknessfloata-afxglobaldatamndragframethicknessfloat"></a><a name="afx_global_data__m_ndragframethicknessfloat"></a> Afx_global_data:: m_ndragframethicknessfloat
부동 상태를 나타내는 데 사용 되는 끌어서 프레임의 두께 지정 합니다.  
  
  
```  
int   m_nDragFrameThicknessFloat;  
```  
  
## <a name="remarks"></a>설명  
  `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA` 생성자 4 픽셀에이 멤버를 초기화 합니다.  
  
## <a name="a-nameafxglobaldataonsettingchangea-afxglobaldataonsettingchange"></a><a name="afx_global_data__onsettingchange"></a> Afx_global_data:: onsettingchange
데스크톱 메뉴 애니메이션의 현재 상태 및 작업 표시줄 자동 숨기기 기능을 탐지합니다.  
  
  
```  
void OnSettingChange();
```  
  
## <a name="remarks"></a>설명  
 이 메서드는 사용자의 데스크톱의 특정 한 특성의 상태에 프레임 워크 변수를 설정합니다. 이 메서드는 메뉴 애니메이션, 메뉴 페이드 및 작업 자동 숨기기 기능 표시줄의 현재 상태를 검색합니다.  
  
## <a name="a-nameafxglobaldataregisterwindowclassa-afxglobaldataregisterwindowclass"></a><a name="afx_global_data__registerwindowclass"></a> Afx_global_data:: registerwindowclass
지정된 MFC 창 클래스를 등록합니다.  
  
  
```  
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `lpszClassNamePrefix`  
 등록 하는 창 클래스의 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드가 성공 하면 등록 된 클래스의 정규화 된 이름 그렇지 않은 경우는 [리소스 예외](../Topic/AfxThrowResourceException.md)합니다.  
  
## <a name="remarks"></a>설명  
 반환 값은 콜론으로 구분 된 목록이 `lpszClassNamePrefix` 매개 변수 문자열 및; 현재 응용 프로그램 인스턴스의 핸들의 16 진수 텍스트 표현을 식별자를 갖는 IDC_ARROW; 및 배경 브러시 화살표 커서는 응용 프로그램 커서입니다. MFC 창 클래스 등록 하는 방법에 대 한 자세한 내용은 참조 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)합니다.  
  
## <a name="see-also"></a>참고 항목    
 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)   
 [AfxThrowResourceException](../../mfc/reference/exception-processing.md#afxthrowresourceexception)

## <a name="a-nameafxglobaldataresumea-afxglobaldataresume"></a><a name="afx_global_data__resume"></a> Afx_global_data:: resume
 Windows 테마 및 비주얼 스타일을 지 원하는 메서드에 액세스 하는 내부 함수 포인터를 다시 초기화 합니다. 
  
  
```  
BOOL Resume();
```  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다. 디버그 모드에서이 메서드는이 메서드는 성공 하는 경우를 가정 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 프레임 워크 받을 때 호출 되는 [WM_POWERBROADCAST](http://msdn.microsoft.com/library/windows/desktop/aa373247) 메시지입니다.  
  
## <a name="a-nameafxglobaldatasetlayeredattriba-afxglobaldatasetlayeredattrib"></a><a name="afx_global_data__setlayeredattrib"></a> Afx_global_data:: setlayeredattrib
Windows [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540) 메서드를 호출하는 간단한 방법을 제공합니다.  
  
  
```  
BOOL SetLayeredAttrib(
    HWND hwnd,  
    COLORREF crKey,  
    BYTE bAlpha,  
    DWORD dwFlags);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `hwnd`  
 계층화된 창을 처리합니다.  
  
 [in] `crKey`  
 투명 색상 키입니다는 [데스크톱 창 관리자](http://msdn.microsoft.com/library/windows/desktop/aa969540) 계층화 된 창을 구성 하기 위해 사용 합니다.  
  
 [in] `bAlpha`  
 계층화된 창의 불투명도를 기술하는 데 사용되는 알파 값입니다.  
  
 [in] `dwFlags`  
 사용할 메서드 매개 변수를 지정하는 플래그의 비트 조합(OR)입니다. `crKey` 매개 변수를 투명 색상으로 사용하려면 LWA_COLORKEY를 지정합니다. `bAlpha` 매개 변수를 사용해서 계층화된 창의 불투명도를 결정하려면 LWA_ALPHA를 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다.   
 
## <a name="see-also"></a>참고 항목   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [SetLayeredWindowAttributes](http://msdn.microsoft.com/library/windows/desktop/ms633540)

## <a name="a-nameafxglobaldatasetmenufonta-afxglobaldatasetmenufont"></a><a name="afx_global_data__setmenufont"></a> Afx_global_data:: setmenufont
지정된 논리 글꼴을 만듭니다.  
  
  
```  
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,  
    BOOL bHorz);
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `lpLogFont`  
 글꼴 특성을 포함 하는 구조체에 대 한 포인터입니다.  
  
 [in] `bHorz`  
 `TRUE` 텍스트 가로; 실행 되도록 지정 하려면 `FALSE` 텍스트 세로 방향으로 실행 되도록 지정 하려면.  
  
## <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드가 성공 합니다. 그렇지 않으면 `FALSE`합니다. 디버그 모드에서이 메서드는이 메서드는 성공 하는 경우를 가정 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 가로 일반 글꼴로 한 밑줄된 글꼴 만들고 있는 굵은 글꼴 사용 된 메뉴 항목이 기본 합니다. 이 메서드는 필요에 따라 일반 세로 방향 글꼴을 만듭니다. 논리 글꼴에 대 한 자세한 내용은 참조 [cfont:: Createfontindirect](../../mfc/reference/cfont-class.md#cfont__createfontindirect)합니다.  
  
## <a name="a-nameafxglobaldataupdatefontsa-afxglobaldataupdatefonts"></a><a name="afx_global_data__updatefonts"></a> Afx_global_data:: updatefonts
프레임워크에서 사용하는 논리 글꼴을 다시 초기화합니다.  
  
  
```  
void UpdateFonts();
```  
  
## <a name="remarks"></a>설명  
 논리 글꼴에 대 한 자세한 내용은 참조 `CFont::CreateFontIndirect`합니다.  
  
## <a name="a-nameafxglobaldataupdatesyscolorsa-afxglobaldataupdatesyscolors"></a><a name="afx_global_data__updatesyscolors"></a> Afx_global_data:: updatesyscolors
프레임워크에서 사용하는 색, 색 농도, 브러시, 펜 및 이미지를 초기화합니다.  
  
  
```  
void UpdateSysColors();
```  
  
## <a name="a-nameafxglobaldatabiswindows7a-afxglobaldatabiswindows7"></a><a name="afx_global_data__biswindows7"></a> Afx_global_data:: biswindows7
응용 프로그램에서 Windows 7 이상을 실행 되는지를 나타냅니다.  
  
  
```  
BOOL bIsWindows7;  
```  
  
## <a name="a-nameafxglobaldataclractivecaptiongradienta-afxglobaldataclractivecaptiongradient"></a><a name="afx_global_data__clractivecaptiongradient"></a> Afx_global_data:: clractivecaptiongradient
활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrActiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldataclrinactivecaptiongradienta-afxglobaldataclrinactivecaptiongradient"></a><a name="afx_global_data__clrinactivecaptiongradient"></a> Afx_global_data:: clrinactivecaptiongradient
비활성 캡션의 그라데이션 색을 지정합니다. 도킹 창에 일반적으로 사용됩니다.  
  
  
```  
COLORREF clrInactiveCaptionGradient;  
```  
  
## <a name="a-nameafxglobaldatagetitaskbarlista-afxglobaldatagetitaskbarlist"></a><a name="afx_global_data__getitaskbarlist"></a> Afx_global_data:: getitaskbarlist
만들고에 전역 데이터에 대 한 포인터는 `ITaskBarList` 인터페이스입니다.  
  
  
```  
ITaskbarList *GetITaskbarList();
```  
  
## <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `ITaskbarList` 목록 개체 막대 작업 만들기 성공 하면 인터페이스 `NULL` 만들기가 실패 하거나 현재 운영 체제가 Windows 7 보다 작으면 메시지를 표시 합니다.  
  
## <a name="a-nameafxglobaldatagetitaskbarlist3a-afxglobaldatagetitaskbarlist3"></a><a name="afx_global_data__getitaskbarlist3"></a> Afx_global_data:: getitaskbarlist3
만들고에 전역 데이터에 대 한 포인터는 `ITaskBarList3` 인터페이스입니다.  
  
  
```  
ITaskbarList3 *GetITaskbarList3();
```  
  
## <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `ITaskbarList3` 목록 개체 막대 작업 만들기 성공 하면 인터페이스 `NULL` 만들기가 실패 하거나 현재 운영 체제가 Windows 7 보다 작으면 메시지를 표시 합니다.  
  
## <a name="a-nameafxglobaldatagetshellautohidebarsa-afxglobaldatagetshellautohidebars"></a><a name="afx_global_data__getshellautohidebars"></a> Afx_global_data:: getshellautohidebars
셸 자동 숨기기 막대의 위치를 결정합니다.  
  
  
```  
int GetShellAutohideBars();
```  
  
## <a name="return-value"></a>반환 값  
 자동의 위치를 지정 하는 인코딩된 플래그 포함 된 정수 값 모음을 숨깁니다. 다음 값을 결합할 수 있습니다: AFX_AUTOHIDE_BOTTOM, AFX_AUTOHIDE_TOP, AFX_AUTOHIDE_LEFT, AFX_AUTOHIDE_RIGHT 합니다.  
  
## <a name="a-nameafxglobaldatareleasetaskbarrefsa-afxglobaldatareleasetaskbarrefs"></a><a name="afx_global_data__releasetaskbarrefs"></a> Afx_global_data:: releasetaskbarrefs
인터페이스를 통해 얻은 해제는 `GetITaskbarList` 및 `GetITaskbarList3` 메서드.  
  
  
```  
void ReleaseTaskBarRefs();
```  
  
## <a name="a-nameafxglobaldatashellcreateitemfromparsingnamea-afxglobaldatashellcreateitemfromparsingname"></a><a name="afx_global_data__shellcreateitemfromparsingname"></a> Afx_global_data:: shellcreateitemfromparsingname
구문 분석 이름에서 셸 항목 개체를 만들고 초기화합니다.  
  
  
```  
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,  
    IBindCtx *pbc,  
    REFIID riid,  
    void **ppv);
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszPath`  
 [in] 표시 이름에 대 한 포인터입니다.  
  
 `pbc`  
 구문 분석 작업을 제어 하는 바인딩 컨텍스트에 대 한 포인터입니다.  
  
 `riid`  
 인터페이스 ID에 대 한 참조  
  
 `ppv`  
 [out] 이 함수를 반환 하는 경우에 요청 된 인터페이스 포인터를 포함 `riid`합니다. 일반적으로 `IShellItem` 또는 `IShellItem2`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고 반환 그렇지 않으면 오류 값입니다.  

