---
title: "CMFCTabToolTipInfo 구조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
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
ms.openlocfilehash: b9750cd9369313a3ed6ea9474d401cd0068a75fa
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo 구조
이 구조는 사용자가 마우스로 가리키고 있는 MDI 탭에 대 한 정보를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>멤버  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|탭 컨트롤의 인덱스를 지정합니다.|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|탭 컨트롤에 대 한 포인터입니다.|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|도구 설명 텍스트입니다.|  
  
## <a name="remarks"></a>주의  
 에 대 한 포인터는 `CMFCTabToolTipInfo` 구조의 매개 변수로 전달 되는 `AFX_WM_ON_GET_TAB_TOOLTIP` 메시지입니다. MDI 탭을 사용할 수 있고 사용자가 탭 컨트롤을 마우스로 때이 메시지가 생성 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제와 어떻게 `CMFCTabToolTipInfo` 에 사용 되는 [MDITabsDemo 샘플: MFC 탭 MDI 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MDITabsDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxbasetabctrl.h  
  
##  <a name="a-namemntabindexa--cmfctabtooltipinfomntabindex"></a><a name="m_ntabindex"></a>CMFCTabToolTipInfo::m_nTabIndex  
 탭 컨트롤의 인덱스를 지정합니다.  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>주의  
 사용자는 가리키고 탭의 인덱스입니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `m_nTabIndex` 에 사용 되는 [MDITabsDemo 샘플: MFC 탭 MDI 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MDITabsDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemptabwnda--cmfctabtooltipinfomptabwnd"></a><a name="m_ptabwnd"></a>CMFCTabToolTipInfo::m_pTabWnd  
 탭 컨트롤에 대 한 포인터입니다.  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `m_pTabWnd` 에 사용 되는 [MDITabsDemo 샘플: MFC 탭 MDI 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MDITabsDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="a-namemstrtexta--cmfctabtooltipinfomstrtext"></a><a name="m_strtext"></a>CMFCTabToolTipInfo::m_strText  
 도구 설명 텍스트입니다.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>주의  
 문자열이 비어 있으면 도구 설명이 표시 되지 않습니다.  
  
### <a name="example"></a>예제  
 다음 예제와 어떻게 `m_strText` 에 사용 되는 [MDITabsDemo 샘플: MFC 탭 MDI 응용 프로그램](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_MDITabsDemo #&2;](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

