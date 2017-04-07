---
title: "COleIPFrameWnd 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd class
- OLE, editing
- OLE, in-place activation
- in-place editing
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
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
ms.openlocfilehash: 85ce028bb5d72c06a0e228abba1bd08a7f6526cb
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd 클래스
응용 프로그램의 내부 편집 창의 기준입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|`COleIPFrameWnd` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|내부 편집에 대 한 항목이 활성화 될 때 프레임 워크에서 호출 합니다.|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|내부 편집 창의 위치를 변경 하는 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스를 만들고 컨테이너 응용 프로그램의 문서 창 내에서 막대를 제어 하는 위치입니다. 또한 포함 된에 의해 생성 된 알림을 처리 [COleResizeBar](../../mfc/reference/coleresizebar-class.md) 개체 사용자가 내부 편집 창의 크기 조정 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `COleIPFrameWnd`, 문서를 참조 하십시오 [활성화](../../mfc/activation-cpp.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 생성 된 `COleIPFrameWnd` 개체 및 형식의 구조에 저장 되 고 전체 상태 정보를 초기화 합니다. **OLEINPLACEFRAMEINFO**합니다.  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [OLEINPLACEFRAMEINFO](http://msdn.microsoft.com/library/windows/desktop/ms693737) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 프레임 워크 호출의 `OnCreateControlBars` 내부 편집에 대 한 항목이 활성화 될 때 작동 합니다.  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndFrame*  
 컨테이너 응용 프로그램의 프레임 창에 대 한 포인터입니다.  
  
 *pWndDoc*  
 컨테이너의 문서 수준 창에 대 한 포인터입니다. 수 **NULL** SDI 응용 프로그램의 컨테이너인 경우.  
  
### <a name="return-value"></a>반환 값  
 0이 아니면 성공 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 아무 작업도 수행하지 않습니다. 컨트롤 막대 만들어질 때 필요한 특별 한 처리를 수행 하려면이 함수를 재정의 합니다.  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 프레임 워크 호출의 `RepositionFrame` 컨트롤 막대 레이아웃과 표시 않으므로 모두 내부 편집 창의 위치를 변경 하는 멤버 함수입니다.  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPosRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 개체 내부에서 포함 된 프레임 창의 현재 위치 좌표 (픽셀)를 클라이언트 영역을 기준으로 합니다.  
  
 `lpClipRect`  
 에 대 한 포인터는 `RECT` 구조 또는 `CRect` 개체 내부에서 포함 된 프레임 창의 현재 클리핑 사각형 좌표 (픽셀)를 클라이언트 영역을 기준으로 합니다.  
  
### <a name="remarks"></a>주의  
 컨테이너 창의 컨트롤 막대의 레이아웃에서 다른 비 OLE 프레임 창에서 수행 합니다. 비 OLE 프레임 창은 컨트롤 막대 및 기타 개체에 대 한 호출에서와 같이 지정 된 프레임 창 크기를에서 위치를 계산 [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout)합니다. 클라이언트 영역은 컨트롤 막대 및 기타 개체에 대 한 공간을 뺀 후 남은 것입니다. A `COleIPFrameWnd` 창을, 지정 된 클라이언트 영역에 따라 도구 모음을 반면에 배치 합니다. 즉, `CFrameWnd::RecalcLayout` 반면, 외부"에서" 작동 `COleIPFrameWnd::RepositionFrame` 작동 "안팎을."  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)

