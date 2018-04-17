---
title: CMFCLinkCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc83e5abf09102af8f27b1ee73fc78ed162b9335
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl 클래스
`CMFCLinkCtrl` 클래스 하이퍼링크로 단추를 표시 하 고 단추를 클릭할 때 링크 대상을 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|지정된 된 URL의 단추 텍스트로 표시합니다.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|암시적 프로토콜 설정 (예를 들어 "http:")의 URL입니다.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|단추 텍스트 또는 비트맵을 포함 단추의 크기를 조정 합니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|포커스 사각형 단추를 그리기 전에 프레임 워크에서 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 파생 되는 단추를 클릭할 때는 `CMFCLinkCtrl` 클래스, 프레임 워크 단추의 URL에 대 한 매개 변수로 전달 된 `ShellExecute` 메서드. 그런 다음 `ShellExecute` 메서드 URL 대상을 엽니다.  
  
## <a name="example"></a>예  
 다음 예제에서는의 크기를 설정 하는 `CMFCLinkCtrl` 개체 및에 도구 설명 및 url을 설정 하는 `CMFCLinkCtrl` 개체입니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxlinkctrl.h  
  
##  <a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 포커스 사각형 단추를 그리기 전에 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rectClient`  
 링크 컨트롤의 경계를 지정 하는 사각형입니다.  
  
### <a name="remarks"></a>설명  
 단추의 포커스 사각형을 그리는 사용자 고유의 코드를 사용 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="seturl"></a>CMFCLinkCtrl::SetURL  
 지정된 된 URL의 단추 텍스트로 표시합니다.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszURL`  
 단추 텍스트 표시를 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 암시적 프로토콜 설정 (예를 들어 "http:")의 URL입니다.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszPrefix`  
 URL 프로토콜 접두사를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 URL 접두사를 설정 하려면이 메서드를 사용 합니다. 접두사 단추의 면에 표시 되지 않지만 URL의 대상으로 이동 하는 데 사용할 수 있습니다.  
  
##  <a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 단추 텍스트 또는 비트맵을 포함 단추의 크기를 조정 합니다.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bVCenter`  
 `TRUE`단추 텍스트 및 비트맵 링크 컨트롤;의 위아래 간에 세로로 가운데 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
 [in] `bHCenter`  
 `TRUE`단추 텍스트 및 링크 컨트롤의 왼쪽과 오른쪽 간 가로 방향으로 비트맵 가운데 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 링크 컨트롤의 새 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl 클래스](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)
