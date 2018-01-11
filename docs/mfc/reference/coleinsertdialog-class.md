---
title: "COleInsertDialog 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs: C++
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4638471ed199d08bb21bcf16465fe933af3a584c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="coleinsertdialog-class"></a>COleInsertDialog 클래스
OLE 개체 삽입 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|대화 상자에서 선택한 항목을 만듭니다.|  
|[COleInsertDialog::DoModal](#domodal)|OLE 개체 삽입 대화 상자를 표시합니다.|  
|[COleInsertDialog::GetClassID](#getclassid)|가져옵니다는 **CLSID** 선택한 항목과 연결 합니다.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|항목을 아이콘으로 그릴 것인지를 알려 줍니다.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘 폼과 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|  
|[COleInsertDialog::GetPathName](#getpathname)|대화 상자에서 선택한 파일의 전체 경로 가져옵니다.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|선택한 개체의 유형을 가져옵니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|형식의 구조 **OLEUIINSERTOBJECT** 대화 상자의 동작을 제어 하는 합니다.|  
  
## <a name="remarks"></a>설명  
 클래스의 개체를 만들 `COleInsertDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COleInsertDialog` 개체 생성 되었으며, 사용할 수 있습니다는 [m_io](#m_io) 구조를 값 이나 대화 상자에서 컨트롤의 상태를 초기화 합니다. `m_io` 형식의 구조는 **OLEUIINSERTOBJECT**합니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.  
  
 자세한 내용은 참조는 [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Windows SDK에는 구조입니다.  
  
 특정 대화 상자에 대 한 자세한 정보에 대 한 문서를 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 이 함수가 구성 된 `COleInsertDialog` 개체입니다.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 원하는 수의 비트 OR 연산자로 결합 되는 다음 값을 포함 하는 생성 플래그:  
  
- **IOF_SHOWHELP** 대화 상자를 호출할 때 도움말 단추가 표시 되도록 지정 합니다.  
  
- **IOF_SELECTCREATENEW** 대화 상자가 호출 될 때 새로 만들기 라디오 단추가 처음 선택 되도록 지정 합니다. 이 기본값이 며 함께 사용할 수 없습니다 **IOF_SELECTCREATEFROMFILE**합니다.  
  
- **IOF_SELECTCREATEFROMFILE** 대화 상자가 호출 될 때 파일에서 만들기 라디오 단추는 처음 선택 되도록 지정 합니다. 함께 사용할 수 없습니다 **IOF_SELECTCREATENEW**합니다.  
  
- **IOF_CHECKLINK** 대화 상자가 호출 될 때 연결 확인란은 처음 확인 않도록 지정 합니다.  
  
- **IOF_DISABLELINK** 대화 상자가 호출 될 때 연결 확인란을 사용할 수 없도록 지정 합니다.  
  
- **IOF_CHECKDISPLAYASICON** 아이콘으로 표시 확인란은 처음 선택 됩니다, 표시 되는 현재 아이콘 및 대화 상자를 호출할 때 변경 아이콘 단추가 활성화 되어 않도록 지정 합니다.  
  
- **IOF_VERIFYSERVERSEXIST** 지정 대화 상자 대화 상자가 표시 되기 전에 등록 데이터베이스에 지정 된 서버가 존재 하는지 확인 하 여 목록 상자에 추가 하는 클래스의 유효성을 검사 해야 합니다. 이 플래그를 설정할 성능이 크게 저하 될 수 있습니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 상자 개체 속해 있는 합니다. 이 경우 **NULL**, 대화 상자 개체의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 표시 하려면 호출는 [DoModal](#domodal) 함수입니다.  
  
##  <a name="createitem"></a>COleInsertDialog::CreateItem  
 형식의 개체를 만들려면이 함수를 호출 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 경우에만 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 만들 항목을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 만든; 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 할당 해야 합니다는 `COleClientItem` 이 함수를 호출 하기 전에 개체입니다.  
  
##  <a name="domodal"></a>COleInsertDialog::DoModal  
 OLE 개체 삽입 대화 상자를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 다음 값 중 하나입니다.  
  
 `COleInsertDialog::DocObjectsOnly`만 DocObjects를 삽입합니다.  
  
 `COleInsertDialog::ControlsOnly`ActiveX 컨트롤에만 삽입합니다.  
  
 0는 DocObject 아니고 ActiveX 컨트롤을 삽입합니다. 위에 나열 된 첫 번째 프로토타입으로 동일 하 게 구현에서이 값 결과입니다.  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
-   IDOK 대화 상자가 성공적으로 표시 된 경우입니다.  
  
-   IDCANCEL 대화 상자를 취소 합니다.  
  
-   오류가 발생 한 경우 IDABORT 합니다. IDABORT 반환 되 면 호출 된 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 형식 발생 한 오류에 대 한 자세한 정보를 보려면 멤버 함수입니다. 가능한 오류 목록을 참조 하십시오.는 [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) Windows SDK에는 함수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_io](#m_io) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 IDOK, 다른 구성원 설정 또는 사용자가 대화 상자에 대 한 정보 입력을 검색 하는 함수를 호출할 수 있습니다.  
  
##  <a name="getclassid"></a>COleInsertDialog::GetClassID  
 가져오려면이 함수를 호출 하는 **CLSID** 연결 된 경우에만 선택한 항목 [DoModal](#domodal) 반환 **IDOK** 이며 선택 형식만 **COleInsertDialog:: createNewItem**합니다.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 **CLSID** 선택된 항목과 관련 된 합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [CLSID 키](http://msdn.microsoft.com/library/windows/desktop/ms691424) Windows sdk에서입니다.  
  
##  <a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 사용자를 아이콘으로 선택한 항목을 표시 하도록 선택 하는 경우를 확인 하려면이 함수를 호출 합니다.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>반환 값  
 개체를 렌더링 하는 데 필요한 메서드입니다.  
  
- `DVASPECT_CONTENT`아이콘으로 표시 확인란 선택 하지 않은 경우 반환 됩니다.  
  
- `DVASPECT_ICON`아이콘으로 표시 확인란을 선택 된 경우 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 경우에만이 함수 호출 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 그리기 측면에 대 한 자세한 내용은 참조 하십시오. [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) Windows SDK에서 데이터 구조입니다.  
  
##  <a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 선택한 항목의 아이콘 측면을 포함 하는 메타 파일에 대 한 핸들을 가져오려면이 함수를 호출 합니다.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 아이콘으로 표시 확인란이 선택한 항목의 아이콘 측면을 포함 하는 메타 파일에 대 한 핸들을 선택 하 여 대화 상자를 해제 하는 경우 체크 **확인**고, 그렇지 않으면 **NULL**합니다.  
  
##  <a name="getpathname"></a>COleInsertDialog::GetPathName  
 경우에만 선택한 파일의 전체 경로 가져오려면이 함수를 호출 [DoModal](#domodal) 반환 **IDOK** 선택 유형을 아니며 **COleInsertDialog::createNewItem**합니다.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에서 선택한 파일에 대 한 전체 경로입니다. 선택 영역 형식이 `createNewItem`,이 함수는 반환 된 의미 없는 `CString` 릴리스 모드에서 또는 디버그 모드에서 어설션을 발생 시킵니다.  
  
##  <a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 개체 삽입 대화 상자를 선택 하 여 해제할 때 선택한 선택 유형을 가져오려면이 함수를 호출 **확인**합니다.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목의 형식입니다.  
  
### <a name="remarks"></a>설명  
 반환 형식 값으로 지정 됩니다는 **선택** 열거형 형식에 선언 된는 `COleInsertDialog` 클래스입니다.  
  
```  
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };  
```  
  
 이러한 값에 대 한 간단한 설명을 따르십시오.  
  
- **COleInsertDialog::createNewItem** The 새로 만들기 라디오 단추가 선택 되었습니다.  
  
- **COleInsertDialog::insertFromFile** The 파일에서 만들기 라디오 단추가 선택 된 하 고 연결 확인란을 선택 하지 않은 합니다.  
  
- **COleInsertDialog::linkToFile** The 파일에서 만들기 라디오 단추가 선택 된 하 고 링크 확인란이 선택 되어 있습니다.  
  
##  <a name="m_io"></a>COleInsertDialog::m_io  
 형식의 구조 **OLEUIINSERTOBJECT** 개체 삽입 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>설명  
 이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) Windows SDK에는 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)
