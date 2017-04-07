---
title: "COlePasteSpecialDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- Paste Special dialog box
- dialog boxes, Paste Special
- OLE Paste Special dialog box
- COlePasteSpecialDialog class
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
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
ms.openlocfilehash: 6984d714248815b062c564c7eed5c315990855af
ms.lasthandoff: 02/24/2017

---
# <a name="colepastespecialdialog-class"></a>COlePasteSpecialDialog 클래스
OLE 선택하여 붙여넣기 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|사용자 지정 형식을 응용 프로그램에 붙여 넣을 수는 형식 목록에 추가 합니다.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|지원 되는 클립보드 형식 목록에 새 항목을 추가 합니다.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|추가 **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`, 선택적으로 `CF_LINKSOURCE` 응용 프로그램 형식 목록에 붙여넣을 수 있습니다.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|지정 된 형식을 사용 하 여 컨테이너 문서에 항목을 만듭니다.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE 붙여넣기 대화 상자를 표시합니다.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|또는 항목을 아이콘으로 그릴 것인지를 알려 줍니다.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘 폼과 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|사용자가 선택 된 사용 가능한 붙여넣기 옵션의 인덱스를 가져옵니다.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|선택한 항목의 형식을 가져옵니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|형식의 구조 **OLEUIPASTESPECIAL** 대화 상자의 기능을 제어 하 합니다.|  
  
## <a name="remarks"></a>주의  
 클래스의 개체를 만들 `COlePasteSpecialDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COlePasteSpecialDialog` 개체를 생성, 사용할 수는 [AddFormat](#addformat) 및 [AddStandardFormats](#addstandardformats) 대화 상자에 클립보드 형식을 추가 하는 멤버 함수입니다. 사용할 수도 있습니다는 [m_ps](#m_ps) 구조에서 값 또는 대화 상자에서 컨트롤의 상태를 초기화 합니다. `m_ps` 형식의 구조는 **OLEUIPASTESPECIAL**합니다.  
  
 자세한 내용은 참조는 [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서를 참조 하십시오. [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 응용 프로그램에서 선택 하 여 붙여넣기 작업을 지원할 수 형식 목록에 새 형식을 추가 하려면이 함수를 호출 합니다.  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>매개 변수  
 *fmt*  
 추가할 데이터 형식에 대 한 참조입니다.  
  
 `lpszFormat`  
 사용자에 게 형식을 설명 하는 문자열입니다.  
  
 *lpszResult*  
 대화 상자에서이 형식을 선택 하면 결과 설명 하는 문자열입니다.  
  
 `flags`  
 다른 연결 및 포함이 형식에 사용할 수 있는 옵션입니다. 이 플래그는 하나 이상의 다른 값의 비트 조합 된 **OLEUIPASTEFLAG** 열거 형식입니다.  
  
 `cf`  
 추가할 클립보드 형식입니다.  
  
 *미디어 유형입니다.*  
 이 형식으로 사용할 수 있는 미디어 형식입니다. 값 중 하나 이상의 비트 조합입니다.는 **미디어 유형입니다.** 열거 형식입니다.  
  
 `nFormatID`  
 이 형식을 식별 하는 문자열의 ID입니다. 이 문자열의 형식은 서로 다른 두 문자열 '\n' 문자로 구분 합니다. 첫 번째 문자열이 같습니다에 전달 되는 *lpstrFormat* 매개 변수를 두 번째 같습니다는 *lpstrResult* 매개 변수입니다.  
  
 *bEnableIcon*  
 목록 상자에서이 형식을 선택 하면 아이콘으로 표시 확인란을 사용할 수 있는지 여부를 결정 하는 플래그입니다.  
  
 *깜박임*  
 목록 상자에서이 형식을 선택 하면 연결 하 여 붙여넣기 라디오 단추를 사용할 수 있는지 여부를 결정 하는 플래그입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하 여 등의 표준 형식 중 하나를 추가할 수 있습니다 **CF_TEXT** 또는 **CF_TIFF** 또는 응용 프로그램에 시스템에 등록 된 사용자 지정 형식입니다. 응용 프로그램에 데이터 개체를 붙여 넣는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [데이터 개체 및 데이터 소스: 조작](../../mfc/data-objects-and-data-sources-manipulation.md)합니다.  
  
 자세한 내용은 참조는 [미디어 유형입니다.](http://msdn.microsoft.com/library/windows/desktop/ms691227) 열거형 형식 및 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 자세한 내용은 참조는 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) 열거 형식에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 지원 되는 클립보드 형식 목록에 새 항목을 추가 합니다.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 추가할 클립보드 형식입니다.  
  
### <a name="return-value"></a>반환 값  
 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) 새 링크 항목에 대 한 정보가 포함 된 구조입니다.  
  
##  <a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 응용 프로그램에서 선택 하 여 붙여넣기 작업을 지원할 수 형식 목록에 다음 클립보드 형식을 추가 하려면이 함수를 호출 합니다.  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bEnableLink*  
 추가할 것인지를 결정 하는 플래그 `CF_LINKSOURCE` 응용 프로그램 형식 목록에 붙여넣을 수 있습니다.  
  
### <a name="remarks"></a>주의  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **"포함 된 개체"**  
  
-   (선택 사항) **"소스 링크"**  
  
 이러한 형식은 포함 하 고 연결을 지 원하는 데 사용 됩니다.  
  
##  <a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog  
 `COlePasteSpecialDialog` 개체를 생성합니다.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 생성 플래그는 비트 OR 연산자를 사용 하 여 결합 하는 다음 플래그를 개수를 제한 없이 포함 되어 있습니다.  
  
- `PSF_SELECTPASTE`대화 상자가 호출 될 때 붙여넣기 라디오 단추는 처음에 확인을 지정 합니다. 와 함께에서 사용할 수 없습니다 `PSF_SELECTPASTELINK`합니다. 이 값이 기본값입니다.  
  
- `PSF_SELECTPASTELINK`라디오 단추 수 링크 붙여넣기 대화 상자가 호출 될 때 확인 처음 않도록 지정 합니다. 와 함께에서 사용할 수 없습니다 `PSF_SELECTPASTE`합니다.  
  
- `PSF_CHECKDISPLAYASICON`대화 상자가 호출 될 때 아이콘으로 표시 확인란이 처음 검사를 지정 합니다.  
  
- `PSF_SHOWHELP`도움말 단추가 표시 대화 상자를 호출할 때 지정 합니다.  
  
 `pDataObject`  
 가리키는 [COleDataObject](../../mfc/reference/coledataobject-class.md) 붙여 넣도록 합니다. 이 값이 **NULL**, 가져옵니다는 `COleDataObject` 클립보드에 저장에서 합니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 개체가 속한 합니다. 있으면 **NULL**, 대화 상자의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 이 함수가 구성 된 `COlePasteSpecialDialog` 개체입니다. 대화 상자를 표시 하려면 호출의 [DoModal](#domodal) 함수입니다.  
  
 자세한 내용은 참조는 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) 열거 형식에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="createitem"></a>COlePasteSpecialDialog::CreateItem  
 선택 하 여 붙여넣기 대화 상자에서 선택 된 새 항목을 만듭니다.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>매개 변수  
 *pNewItem*  
 가리키는 `COleClientItem` 인스턴스. 안 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 항목이 성공적으로 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 후에이 함수를 호출 해야 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
##  <a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 OLE 붙여넣기 대화 상자를 표시합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자가 성공적으로 표시 된 경우.  
  
- **IDCANCEL** 사용자 대화 상자를 취소 합니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 `COleDialog::GetLastError` 발생 한 오류 유형에 대 한 자세한 정보를 멤버 함수입니다. 목록이 가능한 오류에 대 한 참조는 [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_ps](#m_ps) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 **IDOK**, 다른 멤버 대화 상자에 설정 또는 사용자가 입력 한 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
##  <a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 사용자를 아이콘으로 선택한 항목을 표시 하도록 선택 하는 경우를 결정 합니다.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체를 렌더링 하는 데 필요한 메서드입니다.  
  
- `DVASPECT_CONTENT`대화 상자를 해제할 때 아이콘으로 표시 확인란 확인 하지가 반환 됩니다.  
  
- `DVASPECT_ICON`대화 상자를 해제할 때 아이콘으로 표시 확인란을 선택 하는 경우를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 만 후이 함수를 호출 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 그리기 측면에 대 한 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 사용자가 선택한 항목에 연결 된 메타 파일을 가져옵니다.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자를 선택 하 여 해제할 때 아이콘으로 표시 확인란을 선택한 경우 선택한 항목의 아이콘 모양을 포함 하 여 메타 파일에 대 한 핸들 **확인**고, 그렇지 않으면 **NULL**합니다.  
  
##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 가져옵니다 인덱스 값 항목과 연결 된 사용자가 선택한 합니다.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>반환 값  
 배열에 대 한 인덱스 **OLEUIPASTEENTRY** 사용자가 선택 된 구조입니다. 붙여넣기 작업을 수행할 때 선택 된 인덱스에 해당 하는 형식을 사용 해야 합니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조는 [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType  
 선택한 사용자의 유형을 결정 합니다.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목의 형식을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 반환 형식 값으로 지정 됩니다는 **선택** 에 선언 된 열거형 형식은 `COlePasteSpecialDialog` 클래스입니다.  
  
```  
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };  
```  
  
 이러한 값에 대 한 간략 한 desccriptions를 수행합니다.  
  
- **COlePasteSpecialDialog::pasteLink** 라디오 단추는 연결 하 여 붙여넣기를 검사 하 고 선택한 형식이 표준 OLE 형식 되었습니다.  
  
- **COlePasteSpecialDialog::pasteNormal** The 붙여넣기 라디오 단추를 검사 하 고 선택한 형식이 표준 OLE 형식 되었습니다.  
  
- **COlePasteSpecialDialog::pasteOther** 선택한 형식이 표준 OLE 형식입니다.  
  
- **COlePasteSpecialDialog::pasteStatic** 는 선택한 형식의 메타 파일을 했습니다.  
  
##  <a name="m_ps"></a>COlePasteSpecialDialog::m_ps  
 형식의 구조 **OLEUIPASTESPECIAL** 하 여 붙여넣기 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>주의  
 이 구조체의 멤버는 멤버 함수를 통해 또는 직접 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)

