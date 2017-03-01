---
title: "CFontDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFontDialog
dev_langs:
- C++
helpviewer_keywords:
- CFontDialog class
- dialog boxes, fonts
- fonts
- fonts, selecting
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
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
ms.openlocfilehash: 6f277ba8fba72106918e03397f57726bd5beb0ff
ms.lasthandoff: 02/24/2017

---
# <a name="cfontdialog-class"></a>CFontDialog 클래스
글꼴 선택 대화 상자 응용 프로그램에 통합할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|`CFontDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|대화 상자를 표시 하 고 선택할 수 있습니다.|  
|[CFontDialog::GetCharFormat](#getcharformat)|선택한 글꼴의 문자 형식을 검색 합니다.|  
|[CFontDialog::GetColor](#getcolor)|선택한 글꼴의 색을 반환 합니다.|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|현재 선택 된 글꼴의 특성 할당을 `LOGFONT` 구조입니다.|  
|[CFontDialog::GetFaceName](#getfacename)|선택한 글꼴의 글꼴 이름을 반환합니다.|  
|[CFontDialog::GetSize](#getsize)|선택한 글꼴의 포인트 크기를 반환합니다.|  
|[CFontDialog::GetStyleName](#getstylename)|선택한 글꼴의 스타일 이름을 반환합니다.|  
|[CFontDialog::GetWeight](#getweight)|선택한 글꼴의 두께 반환합니다.|  
|[CFontDialog::IsBold](#isbold)|굵은 글꼴 인지 여부를 결정 합니다.|  
|[CFontDialog::IsItalic](#isitalic)|글꼴이 기울임꼴로 표시 되는지 확인 합니다.|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|글꼴 서식을 취소선으로 표시 되는지 여부를 결정 합니다.|  
|[CFontDialog::IsUnderline](#isunderline)|글꼴에 밑줄이 있는지 여부를 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|사용자 지정 하는 데 사용 되는 구조는 `CFontDialog` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 A `CFontDialog` 개체는 현재 시스템에 설치 되어 있는 글꼴의 목록이 있는 대화 상자입니다. 사용자 특정 글꼴 목록에서 선택 하 고이 선택 항목은 응용 프로그램에 다시 보고 키를 누릅니다.  
  
 생성 하는 `CFontDialog` 개체, 제공 된 생성자를 사용 하거나 새 하위 클래스를 파생 및 고유한 사용자 지정 생성자를 사용 합니다.  
  
 한 번는 `CFontDialog` 개체를 생성, 사용할 수는 `m_cf` 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조입니다. [m_cf](#m_cf) 형식의 구조는 [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832)합니다. 이 구조에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 대화 상자 개체의 컨트롤을 초기화 한 후 호출 하는 `DoModal` 멤버 함수를 대화 상자를 표시 하 고 글꼴을 선택 하는 데 사용할 수 있습니다. `DoModal`사용자는 확인 선택 여부를 반환 ( **IDOK**) 하거나 취소 ( **IDCANCEL**) 단추입니다.  
  
 경우 `DoModal` 반환 **IDOK**, 중 하나를 사용 하면 `CFontDialog`의 사용자가 입력 한 정보를 검색 하는 멤버 함수입니다.  
  
 창을 사용 하 여 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 대화 상자의 초기화 하는 동안 오류가 발생 했는지 여부를 확인 하 고 오류에 대 한 자세한 내용을 보려면 함수입니다. 이 함수에 대 한 자세한 내용은 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `CFontDialog`COMMDLG에 의존합니다. 버전 3.1 이상 Windows와 함께 제공 되는 DLL 파일입니다.  
  
 대화 상자를 사용자 지정 하려면에서 클래스를 파생 `CFontDialog`는 사용자 지정 대화 상자 템플릿을 제공 하 고 확장 된 컨트롤에서 알림 메시지를 처리 한 메시지 맵을 추가 합니다. 처리 되지 않은 모든 메시지는 기본 클래스에 전달 되어야 합니다.  
  
 후크 함수를 사용자 지정 필요 하지 않습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CFontDialog`, 참조 [일반 대화 상자 클래스](../../mfc/common-dialog-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="a-namecfontdialoga--cfontdialogcfontdialog"></a><a name="cfontdialog"></a>CFontDialog::CFontDialog  
 `CFontDialog` 개체를 생성합니다.  
  
```  
CFontDialog(
    LPLOGFONT lplfInitial = NULL,  
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,  
    DWORD dwFlags = CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 l`plfInitial`  
 에 대 한 포인터는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 일부 글꼴 특성을 설정할 수 있는 데이터 구조입니다.  
  
 `charFormat`  
 에 대 한 포인터는 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) rich에서 일부 글꼴 특성을 설정할 수 있도록 하는 데이터 구조 컨트롤을 편집 합니다.  
  
 `dwFlags`  
 하나 이상의 글꼴 선택 플래그를 지정합니다. 비트 OR 연산자를 사용하여 하나 이상의 미리 설정된 값을 결합할 수 있습니다. `m_cf.Flag` 구조체 멤버를 수정하는 경우 기본 동작을 그대로 유지하려면 변경에서 비트 OR 연산자를 사용해야 합니다. 이러한 플래그에 자세한 설명을 참조는 [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 pdcPrinter  
 프린터 장치 컨텍스트에 대한 포인터입니다. 제공하는 경우 이 매개 변수는 글꼴을 선택할 프린터에 대한 프린터 장치 컨텍스트를 가리킵니다.  
  
 `pParentWnd`  
 글꼴 대화 상자의 부모 또는 소유자 창에 대한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 생성자는 `CHOOSEFONT` 구조의 멤버를 자동으로 채웁니다. 기본값과는 다른 글꼴 대화 상자를 사용하려는 경우에만 이러한 멤버를 변경해야 합니다.  
  
> [!NOTE]
>  rich edit 컨트롤이 지원되지 않는 경우에만 이 함수의 첫 번째 버전이 제공됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&78;](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="a-namedomodala--cfontdialogdomodal"></a><a name="domodal"></a>CFontDialog::DoModal  
 Windows 일반 글꼴 대화 상자를 표시 하 고 사용자가 글꼴을 선택할 수 있도록 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 **IDOK** 또는 **IDCANCEL**합니다. 경우 **IDCANCEL** 은 Windows 호출 반환 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 오류가 발생 한 것인지 확인 합니다.  
  
 **IDOK** 및 **IDCANCEL** 는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.  
  
### <a name="remarks"></a>주의  
 멤버를 설정 하 여 다양 한 글꼴 대화 상자 컨트롤을 초기화 하려는 경우는 [m_cf](#m_cf) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 **IDOK**, 다른 멤버 대화 상자에 설정 또는 사용자가 입력 한 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
### <a name="example"></a>예제  
  예제를 참조 하십시오 [CFontDialog::CFontDialog](#cfontdialog) 및 [CFontDialog::GetColor](#getcolor)합니다.  
  
##  <a name="a-namegetcharformata--cfontdialoggetcharformat"></a><a name="getcharformat"></a>CFontDialog::GetCharFormat  
 선택한 글꼴의 문자 형식을 검색 합니다.  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 A [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 선택한 글꼴의 문자 서식 지정 하는 방법에 대 한 정보가 포함 된 구조입니다.  
  
##  <a name="a-namegetcolora--cfontdialoggetcolor"></a><a name="getcolor"></a>CFontDialog::GetColor  
 선택한 글꼴 색을 검색 하려면이 함수를 호출 합니다.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴의 색입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&79;](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="a-namegetcurrentfonta--cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a>CFontDialog::GetCurrentFont  
 현재 선택 된 글꼴의 특성의 멤버에 할당 하려면이 함수를 호출 하는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다.  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>매개 변수  
 *lplf*  
 에 대 한 포인터는 `LOGFONT` 구조입니다.  
  
### <a name="remarks"></a>주의  
 다른 `CFontDialog` 멤버 함수는 액세스는 현재 글꼴의 개별 특성에 제공 됩니다.  
  
 이 함수를 호출 하는 동안 호출 [DoModal](#domodal), 시간에 현재 선택 영역을 반환 (사용자에 게 표시 하거나이 대화 상자에서 변경). 이 함수를 호출한 후 호출 되 면 `DoModal` (경우에만 `DoModal` 반환 **IDOK**), 선택한 실제로 어떤 사용자를 반환 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&80;](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="a-namegetfacenamea--cfontdialoggetfacename"></a><a name="getfacename"></a>CFontDialog::GetFaceName  
 선택한 글꼴의 글꼴 이름을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴의 글꼴 이름을 `CFontDialog` 대화 상자입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&81;](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="a-namegetsizea--cfontdialoggetsize"></a><a name="getsize"></a>CFontDialog::GetSize  
 선택한 글꼴의 크기를 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>반환 값  
 글꼴의 크기는 포인트의&1;/10 초입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&82;](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="a-namegetstylenamea--cfontdialoggetstylename"></a><a name="getstylename"></a>CFontDialog::GetStyleName  
 선택한 글꼴의 스타일 이름을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 글꼴의 스타일 이름입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&83;](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="a-namegetweighta--cfontdialoggetweight"></a><a name="getweight"></a>CFontDialog::GetWeight  
 선택한 글꼴의 두께 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴의 두께입니다.  
  
### <a name="remarks"></a>주의  
 글꼴의 두께에 자세한 내용은 참조 [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&84;](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="a-nameisbolda--cfontdialogisbold"></a><a name="isbold"></a>CFontDialog::IsBold  
 선택한 글꼴에 굵게 표시 된 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴에 굵게 표시 된 특성, 그렇지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&85;](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="a-nameisitalica--cfontdialogisitalic"></a><a name="isitalic"></a>CFontDialog::IsItalic  
 선택한 글꼴에 기울임꼴 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴에 기울임꼴 특성, 그렇지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&86;](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="a-nameisstrikeouta--cfontdialogisstrikeout"></a><a name="isstrikeout"></a>CFontDialog::IsStrikeOut  
 선택한 글꼴 서식을 취소선으로 표시 되는지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴, 그렇지 않으면 취소선 특징이 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&87;](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="a-nameisunderlinea--cfontdialogisunderline"></a><a name="isunderline"></a>CFontDialog::IsUnderline  
 선택한 글꼴 밑줄을 표시 하는 경우를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 글꼴, 그렇지 않으면 밑줄 특징이 있으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&88;](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="a-namemcfa--cfontdialogmcf"></a><a name="m_cf"></a>CFontDialog::m_cf  
 대화 상자 개체의 특성을 저장 하는 구성원으로 포함 하는 구조입니다.  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>주의  
 생성 한 후 한 `CFontDialog` 개체를 사용할 수 있습니다 `m_cf` 호출 하기 전에 대화 상자의 다양 한 측면을 수정 하는 `DoModal` 멤버 함수입니다. 이 구조에 대 한 자세한 내용은 참조 하십시오. [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&89;](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




