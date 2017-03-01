---
title: "CMFCLinkCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl class
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
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
ms.openlocfilehash: 8c926c0ef611470b137d2bb897c012a85645c90c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl 클래스
`CMFCLinkCtrl` 클래스 단추를 하이퍼링크로 표시 하 고 단추를 클릭할 때 링크 대상을 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|단추 텍스트와 지정된 된 URL을 표시합니다.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|암시적 프로토콜 설정 (예를 들어, "http:")의 URL입니다.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|단추 텍스트 또는 비트맵을 포함 하는 단추 크기가 조정 됩니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|포커스 사각형의 단추를 그리기 전에 프레임 워크에서 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 파생 되는 단추를 클릭할 때는 `CMFCLinkCtrl` 클래스를 프레임 워크 단추의 URL에 매개 변수로 전달 된 `ShellExecute` 메서드. 그런 다음 `ShellExecute` 메서드는 대상 url을 엽니다.  
  
## <a name="example"></a>예제  
 크기를 설정 하는 방법은 다음 예제에서는 한 `CMFCLinkCtrl` 개체 및에 도구 설명 및 url을 설정 하는 `CMFCLinkCtrl` 개체입니다. 이 예제는의 일부는 [새 컨트롤 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_NewControls #&9;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls #&10;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxlinkctrl.h  
  
##  <a name="a-nameondrawfocusrecta--cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 포커스 사각형의 단추를 그리기 전에 프레임 워크에서 호출 합니다.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rectClient`  
 링크 컨트롤 경계를 설정 하는 사각형입니다.  
  
### <a name="remarks"></a>주의  
 버튼의 포커스 사각형을 그리는 사용자 고유의 코드를 사용 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="a-nameseturla--cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl::SetURL  
 단추 텍스트와 지정된 된 URL을 표시합니다.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszURL`  
 단추 표시할 텍스트입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameseturlprefixa--cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 암시적 프로토콜 설정 (예를 들어, "http:")의 URL입니다.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszPrefix`  
 URL 프로토콜의 접두사입니다.  
  
### <a name="remarks"></a>주의  
 URL 접두사를 설정 하려면이 메서드를 사용 합니다. 접두사 단추의 얼굴에 표시 되지 않으면 있지만 URL의 대상으로 이동 하는 데 사용할 수 있습니다.  
  
##  <a name="a-namesizetocontenta--cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 단추 텍스트 또는 비트맵을 포함 하는 단추 크기가 조정 됩니다.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bVCenter`  
 `TRUE`단추 텍스트와 비트맵 위쪽과 아래쪽의 링크 컨트롤 간에 세로로 가운데 맞춤 하려면 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
 [in] `bHCenter`  
 `TRUE`단추 텍스트 및 링크 컨트롤;의 왼쪽과 오른쪽 간 가로 방향으로 비트맵 가운데 그렇지 않으면 `FALSE`합니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 링크 컨트롤의 새 크기를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl 클래스](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton 클래스](../../mfc/reference/cmfcbutton-class.md)

