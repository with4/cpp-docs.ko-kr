---
title: "CMFCCustomColorsPropertyPage 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCCustomColorsPropertyPage class
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fa534f22438b7be37e7893e545c3e060df69384f
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage 클래스
색 대화 상자에서 사용자 지정 색을 선택할 수 있는 속성 페이지를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|기본 생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|`CMFCCustomColorsPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|속성 페이지의 색 구성 요소로 설정합니다.|  
  
### <a name="remarks"></a>설명  
 `CMFCColorDialog` 클래스가이 클래스를 사용 하 여 사용자 지정 색 속성 페이지를 표시 합니다. 에 대 한 자세한 내용은 `CMFCColorDialog`, 참조 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCCustomColorsPropertyPage` 개체 및 속성 페이지의 색 구성 요소를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&35;](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcustomcolorspropertypage.h  
  
##  <a name="a-namesetupa--cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFCCustomColorsPropertyPage::Setup  
 속성 페이지의 색 구성 요소로 설정합니다.  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `R`|RGB 값의 빨간색 구성 요소입니다.|  
|[in] `G`|RGB 값의 녹색 구성 요소입니다.|  
|[in] `B`|RGB 값의 파란색 구성 요소입니다.|  
  
### <a name="remarks"></a>주의  
 이 메서드는 현재 RGB와의 연결된 된 HLS (색상, 밝기 및 채도) 색 값의 속성 페이지를 업데이트합니다. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) 메서드는 프레임 워크에는 색 대화 상자를 초기화 합니다. 또는 사용자가 왼쪽된 마우스 단추를 누를 때이 메서드를 호출 합니다. 에 대 한 자세한 내용은 `CMFCColorDialog`, 참조 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog 클래스](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage 클래스](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)

