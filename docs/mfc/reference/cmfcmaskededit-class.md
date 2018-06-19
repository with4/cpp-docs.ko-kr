---
title: CMFCMaskedEdit 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 985cd4011dbb1ea8ccad7cd40c81833dd5507f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371799"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit 클래스
`CMFCMaskedEdit` 클래스 마스크에 대해 사용자 입력의 유효성을 검사 하 고 템플릿에 따라 유효성이 검사 된 결과 표시 하는 마스킹된 편집 컨트롤을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|기본 생성자입니다.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|사용자 입력 유효성 검사를 해제 합니다.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|지정 여부는 `GetWindowText` 메서드 마스킹된 문자로 검색 합니다.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|초기화 하는 마스킹된 편집 컨트롤입니다.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|마스킹된 편집 컨트롤 특정 또는 그룹에 사용자 입력을 모든 사용자 입력을 선택할지 여부를 지정 합니다.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|문자 마스킹됩니다만 텍스트에 대해 유효성이 검사 되는지를 전체 마스크에 대해 지정 합니다.|  
|`CMFCMaskedEdit::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|마스킹된 편집 컨트롤에서 텍스트 검색의 유효성이 검사.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|사용자가 입력할 수 있는 유효한 문자는 문자열을 지정 합니다.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|마스킹된 편집 컨트롤에 메시지를 표시 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|해당 마스크 문자에 대해 지정 된 문자의 유효성을 검사 하기 위해 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 사용 하려면 다음 단계는 `CMFCMaskedEdit` 응용 프로그램에서 컨트롤:  
  
 1. 포함 된 `CMFCMaskedEdit` 창 클래스에는 개체입니다.  
  
 2. 호출의 [CMFCMaskedEdit::EnableMask](#enablemask) 메서드를 마스크를 지정 합니다.  
  
 3. 호출 된 [CMFCMaskedEdit::SetValidChars](#setvalidchars) 메서드를 사용할 수 있는 문자 목록을 지정 합니다.  
  
 4. 호출의 [CMFCMaskedEdit::SetWindowText](#setwindowtext) 메서드는 마스킹된 편집 컨트롤에 대 한 기본 텍스트를 지정 합니다.  
  
 5. 호출 된 [CMFCMaskedEdit::GetWindowText](#getwindowtext) 유효성이 검사 된 텍스트를 검색 하는 메서드입니다.  
  
 마스크, 유효한 문자 및 기본 텍스트를 초기화 하는 하나 이상의 메서드를 호출 하면 마스킹된 편집 컨트롤에 표준 편집 컨트롤의 동작을 동일 하 게 동작 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 마스크 (예: 전화 번호)를 사용 하 여 설정 하는 `EnableMask` 메서드는 마스킹된 편집 컨트롤에 대 한 마스크를 만들는 `SetValidChars` 입력할 수 있는 유효한 문자 및 문자열을지정하는메서드`SetWindowText` 컨트롤을 편집 하는 메서드는 마스크의 프롬프트를 표시 합니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxmaskededit.h  
  
##  <a name="disablemask"></a>  CMFCMaskedEdit::DisableMask  
 사용자 입력 유효성 검사를 해제 합니다.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>설명  
 사용자 입력된 유효성 검사 하지 않으면 마스킹된 편집 컨트롤에는 편집 컨트롤은 표준와 비슷하게 동작 합니다.  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 지정 여부는 `GetWindowText` 메서드 마스킹된 문자로 검색 합니다.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE` 지정 하는 [CMFCMaskedEdit::GetWindowText](#getwindowtext) 메서드 검색만 지정할 때;에 마스크 `FALSE` 메서드 전체 텍스트 검색을 지정할 수 있습니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 마스킹된 문자 검색을 사용 하도록 설정 합니다. 그런 다음 (425) 555-0187 등의 전화 번호에 해당 하는 마스킹된 편집 컨트롤을 만듭니다. 호출 하는 경우는 `GetWindowText` 반환 "4255550187" 메서드를 합니다. 마스크 된 문자를 검색 사용 하지 않도록 설정 하는 경우는 `GetWindowText` 메서드 "(425) 555-0187" 예를 들어 편집 컨트롤에 표시 되는 텍스트를 반환 합니다.  
  
##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask  
 초기화 하는 마스킹된 편집 컨트롤입니다.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszMask`  
 사용자 입력의 각 위치에 나타날 수 있는 문자 형식을 지정 하는 마스크 문자열입니다. 길이 `lpszInputTemplate` 및 `lpszMask` 매개 변수 문자열이 동일 해야 합니다. 마스크 문자에 대 한 자세한 내용은 설명 섹션을 참조 하십시오.  
  
 [in] `lpszInputTemplate`  
 리터럴 문자를 지정 하는 마스크 템플릿 문자열로 사용자 입력의 각 위치에 나타날 수 있습니다. 밑줄 문자 ('_')는 문자 자리 표시자로 사용 합니다. 길이 `lpszInputTemplate` 및 `lpszMask` 매개 변수 문자열이 동일 해야 합니다.  
  
 [in] `chMaskInputTemplate`  
 프레임 워크는 사용자 입력에 잘못 된 각 문자에 대 한 대체 하는 기본 문자입니다. 이 매개 변수의 기본값은 밑줄 ('_').  
  
 [in] `lpszValid`  
 유효한 문자 집합을 포함 하는 문자열입니다. `NULL` 모든 문자가 올바른지를 나타냅니다. 이 매개 변수의 기본값은 `NULL`입니다.  
  
### <a name="remarks"></a>설명  
 마스킹된 편집 컨트롤에 대 한 마스크를 만들려면이 메서드를 사용 합니다. 클래스를 파생는 `CMFCMaskedEdit` 클래스 및 재정의 [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) 메서드를 사용자 지정 마스크 처리를 위해 사용자 고유의 코드를 사용 합니다.  
  
 다음 표에서 기본 마스크 문자를 나열 합니다.  
  
|마스크 문자|정의|  
|--------------------|----------------|  
|D|자리 수입니다.|  
|d|숫자 또는 공백이 있습니다.|  
|+|더하기 ('+ '), 빼기 ('-'), 또는 공간입니다.|  
|C|알파벳 문자입니다.|  
|c|알파벳 문자 또는 공간입니다.|  
|A|영숫자 문자입니다.|  
|a|영숫자 문자 또는 공간입니다.|  
|*|인쇄 가능한 문자입니다.|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 마스킹된 편집 컨트롤 사용자를 특정 그룹을 선택할 입력 또는 모든 입력을 허용 하는지 여부를 지정 합니다.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE` 그룹에만;를 선택 하려면 `FALSE` 전체 텍스트를 선택 합니다. 기본값은 `TRUE`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 마스킹된 편집 컨트롤에 사용자를 그룹 또는 전체 텍스트로 선택할 수 있는지 여부를 지정 합니다.  
  
 기본적으로 선택 그룹에 의해 사용 됩니다. 이 경우 사용자는 유효한 문자 연속 그룹만 선택할 수 있습니다.  
  
 예를 들어, 전화 번호 유효성을 검사 하려면 다음 마스킹된 편집 컨트롤을 사용할 수 있습니다.  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 그룹에 의해 선택을 사용 하는 경우 사용자만는 "425", "555" 또는 "0187" 문자열 그룹을 검색할 수 있습니다. 그룹을 선택 하지 않으면 사용자의 전화 번호의 전체 텍스트를 검색할 수 있습니다: "(425) 555-0187"입니다.  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 지정 여부는 텍스트의 유효성을 검사 마스킹된 문자로 또는 전체 / / 마스크에 대 한 합니다.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE` 유효성을 검사할 사용자 입력에 대해만 마스크 지정할 때; `FALSE` 전체 마스크를 검사할 수 있습니다. 기본값은 `TRUE`입니다.  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
 마스킹된 편집 컨트롤에서 텍스트 검색의 유효성이 검사.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `lpszStringBuf`  
 편집 컨트롤에서 텍스트를 수신 하는 버퍼에 대 한 포인터입니다.  
  
 [in] `nMaxCount`  
 수신할 문자의 최대 수입니다.  
  
 [out] `rstrString`  
 편집 컨트롤에서 텍스트를 수신 하는 문자열 개체에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 에 복사 되는 문자열의 바이트 수를 반환 하는 첫 번째 메서드 오버 로드는 `lpszStringBuf` 매개 변수 버퍼; 마스킹된 편집 컨트롤에 텍스트가 없는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 마스킹된 편집 컨트롤에서 텍스트를 복사 하는이 메서드는 `lpszStringBuf` 버퍼 또는 `rstrString` 문자열입니다.  
  
 이 메서드를 재정의 [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext)합니다.  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 해당 마스크 문자에 대해 지정 된 문자의 유효성을 검사 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `chChar`  
 유효성을 검사 하는 문자입니다.  
  
 [in] `chMaskChar`  
 다음 마스크 문자열에서 해당 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 경우는 `chChar` 매개 변수는 형식에서 허용 하는 문자는 `chMaskChar` 매개 변수, 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 입력된 문자를 직접 유효성을 검사 하려면이 메서드를 재정의 합니다. 마스크 문자에 대 한 자세한 내용은 참조는 [CMFCMaskedEdit::EnableMask](#enablemask) 메서드.  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 사용자가 입력할 수 있는 유효한 문자는 문자열을 지정 합니다.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszValid`  
 유효한 입력된 문자 집합을 포함 하는 문자열입니다. `NULL` 모든 문자가 유효함을 의미 합니다. 이 매개 변수의 기본값은 `NULL`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 사용할 수 있는 문자 목록을 정의할 수입니다. 이 목록에는 입력된 문자가 없으면 마스킹된 편집 컨트롤은 사용할 수 없는 합니다.  
  
 다음 코드 예제에서는 16 진수만 허용합니다.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 마스킹된 편집 컨트롤에 메시지를 표시 합니다.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszString`  
 Null로 끝나는 문자열을 프롬프트로 사용 될를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 컨트롤 텍스트를 설정합니다.  
  
 이 메서드를 재정의 [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)
