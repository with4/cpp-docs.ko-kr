---
title: "COleConvertDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog class
- OLE Convert dialog box
- dialog boxes, OLE
- OLE dialog boxes, Convert
- Convert dialog box
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
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
ms.openlocfilehash: 6db5caf443e7f71c58e2c65b46794c2c9d246d38
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="coleconvertdialog-class"></a>COleConvertDialog 클래스
자세한 내용은 참조는 [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|대화 상자에 지정 된 변환을 수행 합니다.|  
|[COleConvertDialog::DoModal](#domodal)|OLE 변경 항목 대화 상자를 표시합니다.|  
|[COleConvertDialog::GetClassID](#getclassid)|가져옵니다는 **CLSID** 선택한 항목과 연결 합니다.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|항목 아이콘으로 그릴 것인지를 지정 합니다.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘 폼과 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|선택한 항목의 형식을 가져옵니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|대화 상자의 동작을 제어 하는 구조입니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.  
  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서를 참조 하십시오. [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
 만 생성 한 `COleConvertDialog` 개체입니다.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 활성화 또는 변환에 항목을 가리킵니다.  
  
 `dwFlags`  
 원하는 수의 다음 값을 포함 하는 생성 플래그 비트를 사용 하 여 결합-or 연산자:  
  
- **CF_SELECTCONVERTTO** 대화 상자가 호출 될 때 변환 대상 라디오 단추는 처음 선택 되도록 지정 합니다. 이 값이 기본값입니다.  
  
- **CF_SELECTACTIVATEAS** 대화 상자가 호출 될 때 다른 이름으로 활성화 라디오 단추는 처음 선택 되도록 지정 합니다.  
  
- **CF_SETCONVERTDEFAULT** 지정 하는 클래스 인 **CLSID** 에 지정 된는 **clsidConvertDefault** 의 멤버는 `m_cv` 구조 변환 대상 라디오 단추를 선택할 때 클래스 목록 상자에서 기본 선택 항목으로 사용 됩니다.  
  
- **CF_SETACTIVATEDEFAULT** 지정 하는 클래스 인 **CLSID** 에 지정 된는 **clsidActivateDefault** 의 멤버는 `m_cv` 활성화 라디오 단추를 선택할 때 구조 클래스 목록 상자에서 기본 선택 항목으로 사용 됩니다.  
  
- **CF_SHOWHELPBUTTON** 대화 상자가 호출 될 때 도움말 단추가 표시 되도록 지정 합니다.  
  
 `pClassID`  
 항목을 활성화 또는 변환의 CLSID 가리킵니다. 경우 **NULL**, **CLSID** 연관 `pItem` 사용 됩니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 개체가 속한 합니다. 있으면 **NULL**, 대화 상자의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 대화 상자를 표시 하려면 호출의 [DoModal](#domodal) 함수입니다.  
  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) 및 [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) 구조입니다.  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 성공적으로 반환 된 후이 함수를 호출 [DoModal](#domodal)형식의 개체를 활성화 하거나 변환 해야 하거나, [활성화](../../mfc/reference/coleclientitem-class.md)합니다.  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 활성화 또는 변환에 항목을 가리킵니다. 안 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 항목 또는 변환 변환 대화 상자에서 사용자가 선택한 정보에 따라 활성화 됩니다.  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 OLE 변환 대화 상자를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자가 성공적으로 표시 된 경우.  
  
- **IDCANCEL** 사용자 대화 상자를 취소 합니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 발생 한 오류 유형에 대 한 자세한 정보를 멤버 함수입니다. 목록이 가능한 오류에 대 한 참조는 [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_cv](#m_cv) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 **IDOK**, 다른 구성원 설정 또는 사용자가 대화 상자에 입력 된 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 가져오려면이 함수를 호출 하는 **CLSID** 변환 대화 상자에서 사용자가 선택한 항목으로 연결 합니다.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 **CLSID** 변환 대화 상자에서 선택한 항목과 연결 합니다.  
  
### <a name="remarks"></a>주의  
 호출 후에이 함수 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 사용자가 선택한 항목을 아이콘으로 표시 하려고 선택 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체를 렌더링 하는 데 필요한 메서드입니다.  
  
- `DVASPECT_CONTENT`아이콘으로 표시 확인란을 선택 하지 된 경우 반환 됩니다.  
  
- `DVASPECT_ICON`아이콘으로 표시 확인란을 선택 된 경우 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 호출 후에이 함수 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 그리기 측면에 대 한 자세한 내용은 참조는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 데이터 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들을 가져오려면이 함수를 호출 합니다.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 확인란 아이콘으로 표시 된 경우 선택된 된 항목의 아이콘 모양을 포함 하 여 메타 파일에 대 한 핸들을 선택 하 여 대화 상자를 해제할 때 체크 **확인**고, 그렇지 않으면 **NULL**합니다.  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 변환 대화 상자에서 선택한 변환의 형식을 확인 하려면이 함수를 호출 합니다.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목의 형식입니다.  
  
### <a name="remarks"></a>주의  
 반환 형식 값으로 지정 됩니다는 **선택** 에 선언 된 열거형 형식은 `COleConvertDialog` 클래스입니다.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 이러한 값에 대 한 간략 한 설명을 따르십시오.  
  
- **COleConvertDialog::noConversion** 대화 상자를 취소 하거나 사용자가 선택한 변환이 반환 됩니다. 경우 `COleConvertDialog::DoModal` 반환 **IDOK**를 사용자 이전에 선택한 것 보다 다른 아이콘을 선택한 수 있습니다.  
  
- **COleConvertDialog::convertItem** 사용자로 변환 하는 다른 항목을 선택한 변환 대상 라디오 단추를 선택 하는 경우 반환 되 고 `DoModal` 반환 **IDOK**합니다.  
  
- **COleConvertDialog::activateAs** 사용자를 활성화 하려면 다른 항목을 선택한 다른 이름으로 활성화 라디오 단추를 선택 하는 경우 반환 되 고 `DoModal` 반환 **IDOK**합니다.  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 형식의 구조 **OLEUICONVERT** 변환 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>주의  
 이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)

