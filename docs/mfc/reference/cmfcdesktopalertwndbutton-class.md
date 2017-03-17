---
title: "CMFCDesktopAlertWndButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton class
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 52294143c6caf5a8e0458c152540c41f7df78c57
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton 클래스
단추를 바탕 화면 경고 대화 상자에 추가할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|기본 생성자입니다.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 결정 합니다.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|단추 경고 대화 상자를 닫는 지 여부를 결정 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 지정 하는 부울 값입니다.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|단추 경고 대화 상자를 닫는 지 여부를 지정 하는 부울 값입니다.|  
  
### <a name="remarks"></a>설명  
 생성자는 기본적으로 설정 된 `m_bIsCaptionButton` 및 `m_bIsCloseButton` 데이터 멤버를 `FALSE`합니다. 부모 `CMFCDesktopAlertDialog` 개체 집합이 `m_bIsCaptionButton` 를 `TRUE` 경고 대화 상자 캡션 영역에 있는 단추를 배치 하는 경우. `CMFCDesktopAlertDialog` 클래스를 만듭니다를 `CMFCDesktopAlertWndButton` 경고 대화 상자를 닫습니다 단추는 데 사용 상자를 설정 하는 개체 `m_bIsCloseButton` 를 `TRUE`합니다.  
  
 추가 `CMFCDesktopAlertWndButton` 개체는 `CMFCDesktopAlertDialog` 개체 모든 단추를 추가 합니다. 에 대 한 자세한 내용은 `CMFCDesktopAlertDialog`, 참조 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에 사용 하는 방법을 보여 줍니다는 `SetImage` 에서 메서드는 `CMFCDesktopAlertWndButton` 클래스입니다. 이 코드 조각은의 일부인는 [바탕 화면 경고 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo #&4;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo #&5;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton  
 경고 대화 상자 캡션 영역에는 단추가 표시 되는지 여부를 결정 합니다.  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추 경고 대화 상자; 캡션 영역에 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton  
 단추 경고 대화 상자를 닫는 지 여부를 결정 합니다.  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>반환 값  
 단추; 경고 대화 상자를 닫은 경우 0이 아닌 그렇지 않으면 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)

