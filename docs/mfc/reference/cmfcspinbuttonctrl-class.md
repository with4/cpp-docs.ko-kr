---
title: "CMFCSpinButtonCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl class
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 25
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
ms.openlocfilehash: c1832062461f2ed53df07a72428089179ed493ab
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl 클래스
`CMFCSpinButtonCtrl` 클래스 스핀 단추 컨트롤을 그리는 비주얼 관리자를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|기본 생성자입니다.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|현재 스핀 단추 컨트롤을 다시 그립니다.|  
  
## <a name="remarks"></a>주의  
 응용 프로그램에서 스핀 단추 컨트롤을 그리는 비주얼 관리자를 사용 하려면의 모든 인스턴스를 대체는 `CSpinButtonCtrl` 클래스는 `CMFCSpinButtonCtrl` 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 개체를 만드는 방법을 보여 줍니다는 `CMFCSpinButtonCtrl` 클래스 및 사용 하 여 해당 `Create` 메서드.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&25;](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxspinbuttonctrl.h  
  
##  <a name="a-nameondrawa--cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 현재 스핀 단추 컨트롤을 다시 그립니다.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 호출의 `CMFCSpinButtonCtrl::OnPaint` 메서드를 처리 하는 [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) 메시지 및 메서드를 차례로 호출 하는이 `CMFCSpinButtonCtrl::OnDraw` 메서드. 프레임 워크 스핀 단추 컨트롤을 그리는 방법을 사용자 지정 하려면이 메서드를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)

