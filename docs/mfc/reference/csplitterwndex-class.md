---
title: "CSplitterWndEx 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs: C++
helpviewer_keywords: CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94ec633718dda81a5183a59eb46387b361d0f004
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx 클래스



사용자 지정된 분할자 창을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|기본 생성자입니다.|  
|`CSplitterWndEx::~CSplitterWndEx`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|분할 창 그리기 위해 프레임 워크에서 호출 됩니다. (재정의 [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|  
  
## <a name="remarks"></a>설명  
 재정의 `OnDrawSplitter` 창에 그래픽 컴포넌트의 모양을 사용자 지정 하는 메서드.  
  
 `CSplitterWndEx` 클래스와 함께 사용 되는 [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder), [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox), 및 [OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground) 는 메서드를 비주얼 관리자 구현합니다. 응용 프로그램에서 분할자 창 그리는 비주얼 관리자를 교체의 선언 된 `CSplitterWnd` 클래스와 `CSplitterWndEx` 클래스. 프레임 창 응용 프로그램에 대 한 분할 창 클래스 mainfrm.h에 있는 CMainFrame 클래스에서 선언 됩니다. 예를 들어 참조는 `OutlookDemo` 샘플 디렉터리에 샘플입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>요구 사항  
 **헤더:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 분할 창 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대 한 포인터입니다. 이 매개 변수가 `NULL`, 프레임 워크 활성 창을 다시 그립니다.  
  
 [in] `nType`  
 중 하나는 `CSplitterWnd::ESplitType` 분할자 창 요소 그리기를 지정 하는 열거형 값입니다. 유효한 값은 `splitBox`, `splitBar`, `splitIntersection` 및 `splitBorder`입니다.  
  
 [in] `rect`  
 차원 및에서 지정 된 분할자 창을 요소를 그릴 위치를 지정 하는 경계 사각형입니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../hierarchy-chart.md)   
 [클래스](mfc-classes.md)   
 [CSplitterWnd 클래스](csplitterwnd-class.md)   
 [CMFCVisualManager 클래스](cmfcvisualmanager-class.md)