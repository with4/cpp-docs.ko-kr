---
title: CMFCRibbonCustomizeDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e693a0e6a2353693f676ed0d63d7087d3e57455
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040901"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog 클래스
리본에 표시 됩니다 **사용자 지정** 페이지.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` 개체를 생성합니다.|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에서는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식과 연결 된 개체입니다.|  
  
## <a name="remarks"></a>설명  
 MFC는 메시지 처리기에서 0을 반환 하는 경우 또는 AFX_WM_ON_RIBBON_CUSTOMIZE 메시지를 처리 하지 않는 경우이 클래스를 자동으로 인스턴스화합니다.  
  
 응용 프로그램에서이 클래스를 사용 하 여 리본 메뉴를 표시 하려면 **사용자 지정** 대화 상자만 인스턴스화해야 하 고, 호출 된 `DoModal` 메서드.  
  
 이 클래스에서 파생 되기 때문에 [CMFCPropertySheet 클래스](../../mfc/reference/cmfcpropertysheet-class.md)를 사용 하 여 사용자 지정 페이지를 추가할 수 있습니다는 `CMFCPropertySheet` API입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribboncustomizedialog.h  
  
##  <a name="cmfcribboncustomizedialog"></a>  CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 `CMFCRibbonCustomizeDialog` 개체를 생성합니다.  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pWndParent*  
 부모 창 (일반적으로 주 프레임)에 대 한 포인터입니다.  
  
 [in] *pRibbon*  
 에 대 한 포인터는 `CMFCRibbonBar` 를 사용자 지정할 수입니다.  
  
### <a name="example"></a>예  
 다음 예제에서는 생성 하는 방법을 `CMFCRibbonCustomizeDialog` 개체입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>설명  
 생성자를 인스턴스화하는 [CMFCRibbonCustomizePropertyPage 클래스](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) 개체 및 속성 시트 페이지 컬렉션에 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)
