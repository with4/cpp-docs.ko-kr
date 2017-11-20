---
title: "CMFCPreviewCtrlImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
dev_langs: C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ab328ca6f114ffb390ad99b6684e26a7d2d56266
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl 클래스
이 클래스는 for Rich Preview 셸에서 제공 하는 호스 창에 배치 하는 창을 구현 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|미리 보기 컨트롤 개체를 destructs 합니다.|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|미리 보기 컨트롤 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|오버로드됨. Windows 창을 만들기 위해 서식 있는 미리 보기 처리기에서 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|이 컨트롤을 삭제 하는 데 필요한 풍부한 미리 보기 처리기에서 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|입력이 컨트롤에 포커스를 설정 합니다.|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|이 미리 보기 컨트롤에 연결 하는 문서를 반환 합니다.|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|이 컨트롤을 다시 그리게 지시 합니다.|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|문서 구현 및 미리 보기 컨트롤 간의 관계를 만드는 미리 보기 처리기에서 호출 됩니다.|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|이 컨트롤에 대 한 새 부모를 설정합니다.|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|호출한 풍부한 미리 보기 처리기 풍부한 미리 보기의 시각적 개체를 설정 해야 할 때 콘텐츠 됩니다.|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|이 컨트롤에 대 한 새로운 경계 사각형을 설정합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|미리 보기를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|미리 보기 창의 배경색입니다.|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|미리 보기 창의 텍스트 색입니다.|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|미리 보기 창에 텍스트를 표시 하는 데 사용 하는 글꼴입니다.|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|컨트롤에서 해당 콘텐츠를 미리 볼 문서에 대 한 포인터입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
미리 보기 컨트롤 개체를 만듭니다.

### <a name="syntax"></a>구문
CMFCPreviewCtrlImpl();  

## <a name="create"></a>CMFCPreviewCtrlImpl::Create
오버로드됨. Windows 창을 만들기 위해 서식 있는 미리 보기 처리기에서 호출 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 서식 있는 미리 보기에 대 한 셸에서 제공 호스트 창에 대 한 핸들입니다.  
  
 `prc`  
 초기 크기와 창의 위치를 지정합니다.  
  
 `pContext`  
 컨텍스트를 만들지에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`만들기 성공 그렇지 않으면 `FALSE`합니다.  
  
## <a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy
이 컨트롤을 삭제 하는 데 필요한 풍부한 미리 보기 처리기에서 호출 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void Destroy();  
```  
  
## <a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint  
미리 보기를 렌더링 하기 위해 프레임 워크에서 호출 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 그리기 장치 컨텍스트 포인터입니다.  


## <a name="focus"></a>CMFCPreviewCtrlImpl::Focus  
입력이 컨트롤에 포커스를 설정 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void Focus();  
```  
## <a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument
이 미리 보기 컨트롤에 연결 하는 문서를 반환 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤에서 해당 콘텐츠를 미리 볼 문서에 대 한 포인터입니다.

## <a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor  
미리 보기 창의 배경색입니다.  
  
### <a name="syntax"></a>구문  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor
미리 보기 창의 텍스트 색입니다.  
  
### <a name="syntax"></a>구문  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="m_font"></a>미리 보기 창에 텍스트를 표시 하는 데 사용 되는 CMFCPreviewCtrlImpl::m_font 글꼴입니다.  
  
### <a name="syntax"></a>구문  
  
```  
CFont m_font;  
```  
## <a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument  
컨트롤에서 해당 콘텐츠를 미리 볼 문서에 대 한 포인터입니다.  
  
### <a name="syntax"></a>구문  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw  
이 컨트롤을 다시 그리게 지시 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void Redraw();  
```  
## <a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument 
문서 구현 및 미리 보기 컨트롤 간의 관계를 만드는 미리 보기 처리기에서 호출 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pDocument`  
 문서 구현에 대 한 포인터입니다.  

## <a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost  
이 컨트롤에 대 한 새 부모를 설정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hWndParent`  
 새 부모 창에 대 한 핸들입니다.  

## <a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals  
호출한 풍부한 미리 보기 처리기 풍부한 미리 보기의 시각적 개체를 설정 해야 할 때 콘텐츠 됩니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `clrBack`  
 미리 보기 창의 배경색입니다.  
  
 `clrText`  
 미리 보기 창의 텍스트 색입니다.  
  
 `plf`  
 미리 보기 창에 텍스트를 표시 하는 데 사용 하는 글꼴입니다. 

##  <a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect  
이 컨트롤에 대 한 새로운 경계 사각형을 설정합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `prc`  
 새 크기와 미리 보기 컨트롤의 위치를 지정합니다.  
  
 `bRedraw`  
 컨트롤 그려야 하는지 여부를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 일반적으로 새 경계 사각형에 호스트 컨트롤의 크기를 조정할 때 설정 됩니다.  

## <a name="dtor"></a>CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
미리 보기 컨트롤 개체를 destructs 합니다.  
  
### <a name="syntax"></a>구문  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  
