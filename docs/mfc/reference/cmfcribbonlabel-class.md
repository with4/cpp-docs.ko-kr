---
title: "CMFCRibbonLabel 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel class
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 21
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
ms.openlocfilehash: b93e0f6c46818515c8d6bcd8d71b78dcaa435ea6
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel 클래스
리본에 대해 클릭할 수 없는 텍스트 레이블을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|생성 하 고 초기화는 `CMFCRibbonLabel` 개체를 지정된 된 텍스트 문자열입니다.|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCRibbonLabel::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|현재 리본 레이블 요소에 대 한 내게 필요한 옵션 데이터를 결정합니다. (재정의 [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|  
  
### <a name="remarks"></a>주의  
 리본 메뉴 레이블을 만든 후에 추가 패널을 호출 하 여 [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)합니다.  
  
 빠른 실행 도구 모음 리본 레이블을 추가할 수 없습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxRibbonLabel.h  
  
##  <a name="a-namecmfcribbonlabela--cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonLabel  
 생성 하 고 초기화는 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md) 지정된 된 텍스트 문자열을 표시 하는 개체입니다.  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
 텍스트에 레이블을 표시입니다.  
  
 [in] `bIsMultiLine`  
 `TRUE`레이블이 있는 여러 줄 레이블을; 임을 지정 하려면 그렇지 않으면 `FALSE`합니다.  
  
##  <a name="a-namesetaccdataa--cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonLabel::SetACCData  
 현재 리본 레이블 요소에 대 한 내게 필요한 옵션 데이터를 결정합니다.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParent`  
 현재 리본 레이블의 부모 창을 나타냅니다.  
  
 [out] `data`  
 형식의 개체 `CAccessibilityData` 현재 리본 레이블의 내게 필요한 옵션 데이터는 채워집니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하는 경우는 `data` 매개 변수는 성공적으로 현재 리본 레이블의 내게 필요한 옵션 데이터로 채워진 하 고, 그렇지 않으면 `FALSE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)

