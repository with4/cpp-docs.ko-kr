---
title: "COleLinksDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- Edit Links dialog box
- COleLinksDialog class
- dialog boxes, OLE
- OLE Edit Links dialog box
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ed256b3a4d3236863e3dcccb7614949f650f058b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="colelinksdialog-class"></a>COleLinksDialog 클래스
OLE 링크 편집 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|`COleLinksDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|OLE 링크 편집 대화 상자를 표시합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|형식의 구조 **OLEUIEDITLINKS** 하는 대화 상자의 동작을 제어 합니다.|  
  
## <a name="remarks"></a>주의  
 클래스의 개체를 만들 `COleLinksDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COleLinksDialog` 개체를 생성, 사용할 수는 [m_el](#m_el) 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조입니다. `m_el` 형식의 구조는 **OLEUIEDITLINKS**합니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.  
  
 자세한 내용은 참조는 [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서를 참조 하십시오. [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="domodal"></a>COleLinksDialog::DoModal  
 OLE 링크 편집 대화 상자를 표시합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자가 성공적으로 표시 된 경우.  
  
- **IDCANCEL** 사용자 대화 상자를 취소 합니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 `COleDialog::GetLastError` 발생 한 오류 유형에 대 한 자세한 정보를 멤버 함수입니다. 목록이 가능한 오류에 대 한 참조는 [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_el](#m_el) 구조를 수행 해야 호출 하기 전에 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
##  <a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog  
 `COleLinksDialog` 개체를 생성합니다.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDoc`  
 편집 링크를 포함 하는 OLE 문서의를 가리킵니다.  
  
 `pView`  
 현재 보기를 가리키는 `pDoc`합니다.  
  
 `dwFlags`  
 0을 포함 하는 생성 플래그 또는 **ELF_SHOWHELP** 대화 상자가 표시 되 면 도움말 단추를 표시할지 여부를 지정할 수 있습니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 개체가 속한 합니다. 있으면 **NULL**, 대화 상자의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 이 함수가 구성만 `COleLinksDialog` 개체입니다. 대화 상자를 표시 하려면 호출의 [DoModal](#domodal) 함수입니다.  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 형식의 구조 **OLEUIEDITLINKS** 의 편집 링크 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>주의  
 이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)

