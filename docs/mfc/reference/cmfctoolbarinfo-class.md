---
title: "CMFCToolBarInfo 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo class
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a9e66ffa0b5a751a7e5711ed20927a6adcede45d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo 클래스
다양한 상태의 도구 모음 이미지의 리소스 ID를 포함합니다. `CMFCToolBarInfo`클래스의 매개 변수로 사용 되는 도우미 클래스는 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>멤버  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|일반 (콜드) 도구 모음 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|사용할 수 없는 도구 모음 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|선택한 (핫) 도구 모음 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|대규모의 일반 도구 모음 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|큰 경우 포함 된 도구 모음 비트맵의 리소스 ID 도구 모음 이미지를 사용할 수 없습니다.|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|대규모의 선택 된 도구 모음 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|비활성화 된 메뉴 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|메뉴 이미지를 포함 하는 도구 모음 비트맵의 리소스 ID입니다.|  
  
## <a name="remarks"></a>주의  
 전체 도구 모음 비트맵을 고정된 된 크기의 작은 도구 모음 이미지 (단추)으로 구성 됩니다. 에 저장 된 각 리소스 ID는 `CMFCToolBarInfo` 개체는 단일 상태 (예, 선택한, 사용 안 함, 대형 또는 메뉴 이미지)에 도구 모음 이미지의 전체 집합을 포함 하는 비트맵입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 도구 모음의 모든 일반 단추 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 도구 모음 단추를 사용할 수 없는 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 도구 모음의 모든 강조 표시 된 단추 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 도구 모음의 모든 큰 일반 단추 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 도구 모음의 모든 큰 비활성화 된 단추 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 도구 모음의 모든 큰 강조 표시 된 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 도구 모음 명령을 사용할 수 없는 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 도구 모음의 모든 일반적인 메뉴 항목 이미지에 대 한 리소스 ID를 지정합니다.  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)

