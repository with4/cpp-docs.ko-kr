---
title: "CHtmlEditCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl class
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4aca52508663e94ee9a1b55843ad05613aa40b0b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl 클래스
MFC 창에서 WebBrowser ActiveX 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|`CHtmlEditCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|WebBrowser ActiveX 컨트롤을 만들고에 연결 된 `CHtmlEditCtrl` 개체입니다. 이 함수는 자동으로 편집 모드로 WebBrowser ActiveX 컨트롤을 넣습니다.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|검색 된 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) 포함 된 WebBrowser 컨트롤에 현재 로드 된 문서에 대 한 인터페이스입니다.|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|포함 된 WebBrowser 컨트롤에 로드 하는 기본 문서에 URL을 검색 합니다.|  
  
## <a name="remarks"></a>주의  
 만든 후 편집 모드를 호스팅된 WebBrowser 컨트롤에 자동으로 배치 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxhtml.h  
  
##  <a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 `CHtmlEditCtrl` 개체를 생성합니다.  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="create"></a>CHtmlEditCtrl::Create  
 WebBrowser ActiveX 컨트롤을 만들고에 연결 된 `CHtmlEditCtrl` 개체입니다. 이 함수에서 편집 모드를 WebBrowser ActiveX 컨트롤에서 기본 문서를 자동으로 탐색 하 고 다음에 배치 됩니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszWindowName`  
 이 매개 변수는 사용되지 않습니다.  
  
 `dwStyle`  
 이 매개 변수는 사용되지 않습니다.  
  
 `rect`  
 컨트롤의 크기와 위치를 지정합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창을 지정합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 컨트롤의 ID를 지정 합니다.  
  
 `pContext`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
##  <a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 검색 된 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) 포함 된 WebBrowser 컨트롤에 현재 로드 된 문서에 대 한 인터페이스  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `ppDocument`  
 문서 인터페이스입니다.  
  
##  <a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 포함 된 WebBrowser 컨트롤에 로드 하는 기본 문서에 URL을 검색 합니다.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


