---
title: CHtmlEditView 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ca4d5a88b14f32064e473bd129fcd0f8ddd7898
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040615"
---
# <a name="chtmleditview-class"></a>CHtmlEditView 클래스
MFC의 문서/뷰 아키텍처 컨텍스트 내에서 WebBrowser 편집 플랫폼의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|`CHtmlEditView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|새 창 개체를 만듭니다.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|반환 된 **IHTMLDocument2** 현재 문서에 대 한 인터페이스입니다.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|이 보기에 대 한 기본 문서의 이름을 검색합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxhtml.h  
  
##  <a name="chtmleditview"></a>  CHtmlEditView::CHtmlEditView  
 `CHtmlEditView` 개체를 생성합니다.  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>  CHtmlEditView::Create  
 새 창 개체를 만듭니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszClassName*  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 클래스 이름에 등록 된 모든 이름일 수 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 전역 함수 또는 **RegisterClass** Windows 함수입니다. 경우 **NULL**, 미리 정의 된 기본값을 사용 하 여 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 특성입니다.  
  
 *lpszWindowName*  
 창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다.  
  
 *dwStyle*  
 창 스타일 특성을 지정합니다. 기본적으로는 **WS_VISIBLE** 및 **WS_CHILD** 창 스타일 설정 됩니다.  
  
 *rect*  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와 창의 위치를 지정 하는 구조입니다. *rectDefault* 크기와 새 창의 위치를 지정 하려면 Windows를 허용 하는 값입니다.  
  
 *pParentWnd*  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 *nID*  
 보기의 ID. 기본적으로로 설정 **AFX_IDW_PANE_FIRST**합니다.  
  
 *pContext*  
 에 대 한 포인터는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)합니다. **NULL** 기본적으로 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드에서 포함 된 WebBrowser 호출 또한 **탐색** 기본 문서를 로드 하는 메서드 (참조 [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>  CHtmlEditView::GetDHtmlDocument  
 반환 된 **IHTMLDocument2** 현재 문서에 대 한 인터페이스입니다.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *ppDocument*  
 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) 인터페이스입니다.  
  
##  <a name="getstartdocument"></a>  CHtmlEditView::GetStartDocument  
 이 보기에 대 한 기본 문서의 이름을 검색합니다.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>참고 항목  
 [HTMLEdit 샘플](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


