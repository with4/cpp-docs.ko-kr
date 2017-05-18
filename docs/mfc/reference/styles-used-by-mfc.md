---
title: "MFC에서 사용 되는 스타일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.styles
dev_langs:
- C++
helpviewer_keywords:
- edit styles [MFC]
- window styles, in MFC
- styles
- frame windows, styles
- message-box styles
- styles, MFC
- buttons, MFC toolbars
- list boxes, styles
- static styles
- scroll-bar styles [MFC]
- combo boxes, styles
- extended window styles
ms.assetid: d3b9af37-31b5-4c97-a8ad-189fd724b04c
caps.latest.revision: 10
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
ms.openlocfilehash: 344d2ce3de15403e17f29dc9504253cbb0ade607
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="styles-used-by-mfc"></a>MFC에서 사용하는 스타일
해당 하는 MFC 개체를 만들 때 다음과 같은 스타일을 사용 합니다. 대부분의 경우 이러한 스타일 설정 되어는 `dwStyle` 클래스의 매개 변수 **만들기** 함수입니다.  
  
### <a name="mfc-styles"></a>MFC 스타일  
  
|스타일|설명|  
|-----------|-----------------|  
|[단추 스타일](../../mfc/reference/button-styles.md)|적용 대상 [CButton 클래스](../../mfc/reference/cbutton-class.md) 라디오 단추와 같은 개체 확인란 및 누름 단추입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CButton::Create](../../mfc/reference/cbutton-class.md#create)합니다.|  
|[콤보 상자 스타일](../../mfc/reference/combo-box-styles.md)|적용 대상 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CComboBox::Create](../../mfc/reference/ccombobox-class.md#create)합니다.|  
|[스타일 편집](../../mfc/reference/edit-styles.md)|적용 대상 [CEdit 클래스](../../mfc/reference/cedit-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CEdit::Create](../../mfc/reference/cedit-class.md#create)합니다.|  
|[프레임 창 스타일](../../mfc/reference/frame-window-styles-mfc.md)|적용 대상 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CFrameWnd::Create](../../mfc/reference/cframewnd-class.md#create)합니다.|  
|[목록 상자 스타일](../../mfc/reference/list-box-styles.md)|적용 대상 [CListBox 클래스](../../mfc/reference/clistbox-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)합니다.|  
|[메시지 상자 스타일](../../mfc/reference/message-box-styles.md)|적용 대상 [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 항목입니다. 스타일의 조합을 지정는 `nType` 의 매개 변수 `AfxMessageBox`합니다.|  
|[스크롤 막대 스타일](../../mfc/reference/scroll-bar-styles.md)|적용 대상 [CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CScrollBar::Create](../../mfc/reference/cscrollbar-class.md#create)합니다.|  
|[정적 스타일](../../mfc/reference/static-styles.md)|적용 대상 [CStatic 클래스](../../mfc/reference/cstatic-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CStatic::Create](../../mfc/reference/cstatic-class.md#create)합니다.|  
|[창 스타일](../../mfc/reference/window-styles.md)|적용 대상 [CWnd 클래스](../../mfc/reference/cwnd-class.md) 개체입니다. 스타일의 조합을 지정는 `dwStyle` 의 매개 변수 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 또는 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)합니다.|  
|[확장된 창 스타일](../../mfc/reference/extended-window-styles.md)|적용 대상 [CWnd 클래스](../../mfc/reference/cwnd-class.md) 개체입니다. 스타일의 조합을 지정는 `dwExStyle` 의 매개 변수 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../mfc/class-library-overview.md)


