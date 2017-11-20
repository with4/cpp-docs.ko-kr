---
title: "CCommonDialog 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs: C++
helpviewer_keywords: CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d97bef4a21a926f1b6015d43f4da74bfc52185f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccommondialog-class"></a>CCommonDialog 클래스
Windows 공용 대화 상자의 기능을 캡슐화하는 클래스의 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|`CCommonDialog` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 Windows 공용 대화 상자의 기능을 캡슐화 하는 다음 클래스:  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>CCommonDialog::CCommonDialog  
 `CCommonDialog` 개체를 생성합니다.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속해 있는 합니다. 이 경우 **NULL**, 대화 상자 개체의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 참조 [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) 완전 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFileDialog 클래스](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog 클래스](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog 클래스](../../mfc/reference/ccolordialog-class.md)   
 [CPageSetupDialog 클래스](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog 클래스](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog 클래스](../../mfc/reference/cfindreplacedialog-class.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)
