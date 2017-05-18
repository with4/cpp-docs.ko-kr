---
title: "CMFCRibbonUndoButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton class
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d4406e21a7e2a945965020d85a748b93d66b5682
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton 클래스
`CMFCRibbonUndoButton` 클래스는 가장 최근 사용자 명령에 포함 된 드롭다운 목록에서 단추를 구현 합니다. 사용자에 게 다시 실행 하거나 해당 변경 내용을 취소 하려면 드롭다운 목록에서 가장 최근 명령 중 하나 이상을 선택할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|새 `CMFCRibbonUndoButton` 지정 하는 명령 ID, 텍스트 레이블 및 부모 개체의 이미지 목록에서 이미지를 사용 하 여 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|작업 목록에 새 동작을 추가합니다.|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|드롭 다운 목록 작업 목록을 지웁니다.|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|사용자가 선택한 드롭 다운 목록에서 항목의 수를 결정 합니다.|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|메뉴 개체에 포함 되어 있는지 여부를 나타냅니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCRibbonUndoButton` 클래스는 스택을 드롭 다운 목록을 나타내는 데 사용 합니다.  
  
## <a name="example"></a>예제  
 개체를 생성 하는 방법은 다음 예제는 `CMFCRibbonUndoButton` 클래스 및 동작의 목록에 새 작업을 추가 합니다. 이 코드 조각은의 일부인는 [리본 가젯 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_RibbonGadgets #&2;](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 작업 목록에 새 동작을 추가합니다.  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszLabel`  
 드롭다운 목록에 표시 될 작업 레이블.  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 드롭 다운 목록 작업 목록을 지웁니다.  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 새 `CMFCRibbonUndoButton` 지정 하는 명령 ID, 텍스트 레이블 및 부모 개체의 이미지 목록에서 이미지를 사용 하 여 개체입니다.  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 명령 식별자를 지정합니다.  
  
 [in] `lpszText`  
 단추의 텍스트 레이블을 지정합니다.  
  
 [in] `nSmallImageIndex`  
 버튼의 작은 이미지에 대 한 부모 개체의 이미지 목록 인덱스&0;부터 시작 합니다.  
  
 [in] `nLargeImageIndex`  
 인덱스에 대 한 부모 개체의 이미지 목록에는 단추의 큰 이미지의 합니다.  
  
 [in] `hIcon`  
 버튼의 이미지로 사용할 수 있는 아이콘에 대 한 핸들입니다.  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 사용자가 선택한 드롭 다운 목록에서 항목의 수를 결정 합니다.  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 선택한 항목의 수입니다.  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 메뉴 개체에 포함 되어 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery 클래스](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton 클래스](../../mfc/reference/cmfcribbonbutton-class.md)

