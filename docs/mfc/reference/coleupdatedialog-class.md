---
title: "COleUpdateDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
- AFXODLGS/COleUpdateDialog
- AFXODLGS/COleUpdateDialog::COleUpdateDialog
- AFXODLGS/COleUpdateDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- Update dialog
- links [C++], updating
- updating OLE links
- OLE dialog boxes, Edit Link
- OLE link updating
- COleUpdateDialog class
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8066a8dc9e572c14e9423af62d340e249351ac11
ms.lasthandoff: 02/24/2017

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
|[COleUpdateDialog::DoModal](#domodal)|표시는 **링크 편집** 업데이트 모드에서 대화 상자입니다.|  
  
## <a name="remarks"></a>주의  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서를 참조 하십시오. [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
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
  
##  <a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
 `COleUpdateDialog` 개체를 생성합니다.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDoc`  
 업데이트 해야 할 수 있는 링크를 포함 하는 문서를 가리킵니다.  
  
 *bUpdateLinks*  
 연결 된 개체가 업데이트 될 지 여부를 결정 하는 플래그입니다.  
  
 *bUpdateEmbeddings*  
 포함 된 개체가 업데이트 될 지 여부를 결정 하는 플래그입니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 개체가 속한 합니다. 있으면 **NULL**, 대화 상자의 부모 창 기본 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 이 함수가 구성만 `COleUpdateDialog` 개체입니다. 대화 상자를 표시 하려면 호출 [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal)합니다. 이 클래스를 대신 사용 해야 `COleLinksDialog` 기존 업데이트 하려는 경우 연결 항목 또는 포함 합니다.  
  
##  <a name="domodal"></a>COleUpdateDialog::DoModal  
 링크 편집 대화 상자에 표시 모드를 업데이트 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자에서 성공적으로 반환 하는 경우.  
  
- **IDCANCEL** 업데이트 해야 하는 경우 현재 문서에 연결 되거나 포함 된 항목 중입니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 발생 한 오류 유형에 대 한 자세한 정보를 멤버 함수입니다. 목록이 가능한 오류에 대 한 참조는 [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 사용자가 취소 단추를 선택 하지 않으면 모든 링크 및/또는 포함 문서가 업데이트 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog 클래스](../../mfc/reference/colelinksdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog 클래스](../../mfc/reference/colelinksdialog-class.md)

