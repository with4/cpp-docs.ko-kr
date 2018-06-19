---
title: CMFCToolTipInfo 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 325650f35d097b54eda160bbdbbd5c877dbd0242
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368376"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo 클래스
도구 설명의 시각적 모양에 대한 정보를 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|도구 설명이 풍선 모양인지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|도구 설명 레이블이 굵은 글꼴로 표시되는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|도구 설명이 설명을 포함하는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|도구 설명이 아이콘을 포함하는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|도구 설명 레이블과 도구 설명 사이에 구분 기호가 표시되는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|도구 설명 모서리가 둥근지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|시각화 관리자 도구 설명의 표시를 제어 해야 하는지 여부를 나타내는 부울 변수 (참조 [CMFCVisualManager 클래스](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|도구 설명 테두리 색입니다.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|도구 설명 배경색입니다.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|도구 설명의 그라데이션 채우기 색입니다.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|도구 설명의 텍스트 색입니다.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|도구 설명의 그라데이션 채우기 각도입니다.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|도구 설명의 가능한 최대 설명 너비(픽셀)입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, 및 [CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md) 응용 프로그램에서 사용자 지정된 도구 설명을 구현에 함께 합니다. 이러한 도구 설명 클래스를 사용 하는 방법의 예제를 보려면는 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md) 항목입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCToolTipInfo` 클래스에서 다양한 멤버 변수의 값을 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtooltipctrl.h  
  
##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip  
 모든 도구 설명의 표시 스타일을 지정합니다.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>설명  
 `TRUE` 도구 설명이 풍선 스타일을 사용 함을 나타냅니다 `FALSE` 도구 설명 사각형 스타일을 사용 함을 나타냅니다.  
  
##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel  
 도구 설명 텍스트의 글꼴을 굵게 있는지 여부를 지정 합니다.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 설정 `TRUE` 굵은 글꼴이 포함 된 도구 설명 텍스트를 표시 하려면 또는 `FALSE` 굵은 글꼴이 아닌 글꼴 도구 설명 레이블을 표시 합니다.  
  
##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription  
 각 도구 설명을 설명 텍스트를 표시 하는지 여부를 지정 합니다.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 설정 `TRUE` 설명, 표시 또는 `FALSE` 설명을 숨길입니다. 호출 하 여 도구 설명에 대 한 설명을 지정할 수 있습니다 [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon  
 모든 도구 설명 아이콘을 표시 하는지 여부를 지정 합니다.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 설정 `TRUE` 각 도구 설명에 아이콘을 표시 또는 `FALSE` 아이콘 없이 도구 설명을 표시 하도록 합니다.  
  
##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator  
 각 도구 설명에 해당 레이블과 설명 사이 구분 기호에 있는지 여부를 지정 합니다.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 설정 `TRUE` 도구 설명 레이블과 설명 사이 구분 기호를 표시 하려면 또는 `FALSE` 구분 기호 없이 차례로 도구 설명을 표시 하도록 합니다.  
  
##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners  
 모든 도구 설명 모서리가 둥글게 여부를 지정 합니다.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>설명  
 이 멤버를 설정 `TRUE` 둥근된 모서리 도구 설명에 표시 하려면 또는 `FALSE` 사각형 모퉁이 도구 설명에 표시 합니다.  
  
##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder  
 모든 도구 설명에는 테두리의 색을 지정합니다.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill  
 도구 설명 배경의 색을 지정 합니다.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>설명  
 경우 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) 은-1, 도구 설명 배경색은 `m_clrFill`합니다. 그렇지 않으면 `m_clrFill` 색 그라데이션의 시작 부분을 지정 하 고 `m_clrFillGradient` 그라데이션의 끝 색을 지정 합니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의의 방향을 결정 합니다.  
  
##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient  
 도구 설명에 대 한 그라데이션 배경에 대 한 마지막 색을 지정합니다.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>설명  
 경우 `m_clrFillGradient` 은-1는 그라데이션 없음. 그라데이션 초기 색은에서 지정 하는 그렇지 않은 경우 [CMFCToolTipInfo::m_clrFill](#m_clrfill) 마침 그라데이션 색은에서 지정 하 고 `m_clrFillGradient`합니다. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) 그라데이션의의 방향을 결정 합니다.  
  
##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText  
 모든 도구 설명의 텍스트 색을 지정합니다.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle  
 도구 설명의 배경 그라데이션을 그릴 각도 지정 합니다.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>설명  
 `m_nGradientAngle` 도구 설명의 배경 그라데이션 가로에서 오프셋 된 각도로 각도 지정 합니다. 경우 `m_nGradientAngle` 가 0 이면 그라데이션 왼쪽에서 오른쪽에 그려집니다. 경우 `m_nGradientAngle` 는 1에서 360 사이 그라데이션을 회전 시계 방향으로 회전 각도 만큼 해당 합니다. 경우 `m_nGradientAngle` 인 기본 값-1은 그라데이션 위쪽에서 아래쪽에 그려집니다. 이 설정과 동일 `m_nGradientAngle` 90으로 합니다.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` 색 그라데이션의 시작 부분을 지정 하 고 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` 그라데이션의 끝 색을 지정 합니다. 경우 `m_clrFillGradient` 은-1는 그라데이션 없음.  
  
##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth  
 각 도구 설명에 표시 되는 설명의 최대 너비를 지정 합니다. 설명 너비 지정된 값을 초과 하는 경우 텍스트가 래핑됩니다.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme  
 비주얼 관리자 응용 프로그램의 모든 도구 설명의 모양을 제어 하는지 여부를 지정 합니다.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>설명  
 경우 `m_bVislManagerTheme` 은 `TRUE`, 모든 도구 설명 새 요청 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) 화면에 표시 되 고 해당 개체에 값을 사용 하 여 모양을 결정 하기 전에 응용 프로그램의 비주얼 관리자에서 합니다. 다른 멤버 여 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) 무시 됩니다.  
  
##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `src`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager 클래스](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl 클래스](../../mfc/reference/cmfctooltipctrl-class.md)
