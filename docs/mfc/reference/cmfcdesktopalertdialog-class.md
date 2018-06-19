---
title: CMFCDesktopAlertDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertDialog [MFC], CreateFromParams
- CMFCDesktopAlertDialog [MFC], GetDlgSize
- CMFCDesktopAlertDialog [MFC], HasFocus
- CMFCDesktopAlertDialog [MFC], PreTranslateMessage
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 815f9e8177cc908d7d76ca6d0f3130d1d50c93ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368172"
---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog 클래스
`CMFCDesktopAlertDialog` 클래스와 함께 사용 되는 [CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md) 팝업 창에 사용자 지정 대화 상자를 표시 하려면.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDesktopAlertDialog : public CDialogEx  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||  
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||  
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||  
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|(`CDialogEx::PreTranslateMessage`를 재정의합니다.)|  
  
### <a name="remarks"></a>설명  
 다음 단계를 수행하여 팝업 창에 사용자 지정 대화 상자를 표시합니다.  
  
1.  `CMFCDesktopAlertDialog`에서 클래스를 파생합니다.  
  
2.  프로젝트 리소스에서 자식 대화 상자 템플릿을 만듭니다.  
  
3.  호출 [cmfcdesktopalertwnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 대화 상자 템플릿의 리소스 id 매개 변수로 파생된 클래스의 런타임 클래스 정보에 대 한 포인터입니다.  
  
4.  호스트된 컨트롤에서 생성되는 모든 알림을 처리하는 사용자 지정 대화 상자를 프로그래밍하거나 이러한 알림을 직접 처리하는 호스트된 컨트롤을 프로그래밍합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDesktopAlertDialog.h  
  
##  <a name="createfromparams"></a>  CMFCDesktopAlertDialog::CreateFromParams  

  
```  
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,  
    CMFCDesktopAlertWnd* pParent);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `params`  
 [in] `pParent`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdlgsize"></a>  CMFCDesktopAlertDialog::GetDlgSize  

  
```  
CSize GetDlgSize();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="hasfocus"></a>  CMFCDesktopAlertDialog::HasFocus  

  
```  
BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="pretranslatemessage"></a>  CMFCDesktopAlertDialog::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pMsg`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd 클래스](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWndInfo 클래스](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CDialogEx 클래스](../../mfc/reference/cdialogex-class.md)
