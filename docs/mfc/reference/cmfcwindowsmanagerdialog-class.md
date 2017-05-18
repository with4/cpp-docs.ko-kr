---
title: "CMFCWindowsManagerDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog class
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9f1508cfd3844fed413edd69063f1b3e64e80195
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog 클래스
`CMFCWindowsManagerDialog` 개체를 사용 하면 사용자가 MDI 응용 프로그램에서 MDI 자식 창을 관리할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` 개체를 생성합니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCWindowsManagerDialog` 응용 프로그램에서 현재 열려 있는 MDI 자식 창의 목록을 포함 합니다. 수동으로 사용자가 대화 상자를 사용 하 여 MDI 자식 창의 상태를 제어할 수 있습니다.  
  
 `CMFCWindowsManagerDialog`내에 포함 된 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)합니다. `CMFCWindowsManagerDialog` 수동으로 만들어야 하는 클래스가 아닙니다. 함수를 호출 하는 대신, [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)를 만들고 표시 하 고는 `CMFCWindowsManagerDialog` 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCWindowsManagerDialog` 개체를 호출 하 여 `CMDIFrameWndEx::ShowWindowsDialog`합니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&18;](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxWindowsManagerDialog.h  
  
##  <a name="cmfcwindowsmanagerdialog"></a>CMFCWindowsManagerDialog::CMFCWindowsManagerDialog  
 생성 된 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 개체입니다.  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMDIFrame`  
 부모 또는 소유자 창에 대 한 포인터입니다.  
  
 [in] `bHelpButton`  
 프레임 워크가 표시 여부를 지정 하는 부울 매개 변수는 **도움말** 단추입니다.  
  
### <a name="remarks"></a>주의  
 비주얼 관리자에 대 한 자세한 내용은 참조 [시각화 관리자](../../mfc/visualization-manager.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)

