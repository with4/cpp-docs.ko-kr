---
title: COleUpdateDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- COleUpdateDialog [MFC], COleUpdateDialog
- COleUpdateDialog [MFC], DoModal
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc5d51bfeb18b51be5a54c51046e3cd420fb1cb8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852109"
---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog 클래스
OLE 편집 링크 대화 상자의 특별한 경우에 사용됩니다. 예를 들어, 문서에서 기존에 연결되거나 포함된 개체만 업데이트할 경우에 사용해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|`COleUpdateDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|표시 된 **연결 편집** 업데이트 모드에서 대화 상자.|  
  
## <a name="remarks"></a>설명  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="coleupdatedialog"></a>  COleUpdateDialog::COleUpdateDialog  
 `COleUpdateDialog` 개체를 생성합니다.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *입력*  
 업데이트 하는 데 필요할 수 있는 링크를 포함 하는 문서를 가리킵니다.  
  
 *bUpdateLinks*  
 연결 된 개체를 업데이트할 수 있는지 여부를 결정 하는 플래그입니다.  
  
 *bUpdateEmbeddings*  
 포함 된 개체를 업데이트할 수 있는지 여부를 결정 하는 플래그입니다.  
  
 *pParentWnd*  
 부모 또는 소유자 창 개체 (형식의 `CWnd`) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자의 부모 창 주 응용 프로그램 창에 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 이 함수가 구성만 `COleUpdateDialog` 개체입니다. 대화 상자를 표시 하려면 호출 [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)합니다. 이 클래스를 대신 사용 해야 `COleLinksDialog` 만 기존 업데이트 하려는 경우 연결 또는 항목을 포함 합니다.  
  
##  <a name="domodal"></a>  COleUpdateDialog::DoModal  
 모드를 업데이트 하는 링크 편집 대화 상자에 표시 됩니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- IDOK 대화 상자에서 성공적으로 반환 하는 경우입니다.  
  
- 현재 문서에서 연결 되거나 포함 된 항목이 없는 경우 IDCANCEL 업데이트 해야 합니다.  
  
- IDABORT 오류가 발생 합니다. IDABORT 반환 되 면 호출 된 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 발생 한 오류 유형에 대 한 자세한 정보를 보려면 멤버 함수입니다. 목록을 가능한 오류에 대 한 참조를 [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) Windows SDK에는 함수입니다.  
  
### <a name="remarks"></a>설명  
 사용자가 취소 단추를 선택 하지 않는 한 모든 링크 및/또는 포함 업데이트 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog 클래스](../../mfc/reference/colelinksdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog 클래스](../../mfc/reference/colelinksdialog-class.md)
