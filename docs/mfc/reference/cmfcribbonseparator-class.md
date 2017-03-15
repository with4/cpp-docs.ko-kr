---
title: "CMFCRibbonSeparator 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonSeparator::GetThisClass
- CMFCRibbonSeparator.CreateObject
- CMFCRibbonSeparator::CreateObject
- CMFCRibbonSeparator
- CreateObject
- CMFCRibbonSeparator.GetThisClass
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator class
- GetThisClass method
- CreateObject method
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 98a58d43b5e6299f26521d873caec06d4581f7b3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator 클래스
리본 메뉴 구분 기호를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|`CMFCRibbonSeparator` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|에 구분 기호를 추가 **명령을** 목록에 **사용자 지정** 대화 상자입니다. (재정의 [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|  
|`CMFCRibbonSeparator::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|다른 개체 로부터 구분 멤버 변수를 설정 하는 복사 메서드.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|구분 기호의 크기를 반환합니다.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|구분 기호 인지를 나타냅니다.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|이 탭은 인지를 나타냅니다.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|시스템의 구분 기호는 리본 또는 빠른 실행 도구 모음에 의해 호출 됩니다.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|시스템의 구분 기호 의해 호출 된 **명령을** 목록입니다.|  
  
## <a name="remarks"></a>주의  
 리본 메뉴 구분 기호는 세로 또는 가로 줄 구분 요소 리본 논리적으로 합니다. 리본 컨트롤, 주 응용 프로그램 메뉴, 리본 메뉴 상태 표시줄 및 빠른 실행 도구 모음에는 구분 기호를 그릴 수 있습니다.  
  
 응용 프로그램에서 구분 기호를 사용 하 여 새 개체를 생성 하 고 다음과 같이 기본 응용 프로그램 메뉴에 추가 합니다.  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
호출 [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) 리본 패널에 구분 기호를 추가 합니다. 구분 기호에 할당 되 고 내부적으로 추가 된 `AddSeparator` 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxbaseribbonelement.h  
  
##  <a name="a-nameaddtolistboxa--cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox  
 에 구분 기호를 추가 **명령을** 목록에 **사용자 지정** 대화 상자입니다.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndListBox`  
 에 대 한 포인터는 **명령을** 목록 구분 기호를 추가 하는 위치입니다.  
  
 [in] `bDeep`  
 무시됩니다.  
  
### <a name="return-value"></a>반환 값  
 목록 상자에서 지정한 문자열에&0;부터 시작 인덱스 `pWndListBox`합니다.  
  
##  <a name="a-namecmfcribbonseparatora--cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator  
 `CMFCRibbonSeparator` 개체를 생성합니다.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bIsHoriz`  
 경우 `TRUE`, 구분 기호는 가로 경우 `FALSE`, 구분 기호는 세로입니다.  
  
### <a name="remarks"></a>주의  
 가로 구분 기호는 응용 프로그램 메뉴에 사용 됩니다. 세로 구분 기호는 도구 모음에 사용 됩니다.  
  
### <a name="example"></a>예제  
 개체를 생성 하는 방법은 다음 예제는 `CMFCRibbonSeparator` 클래스입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&19;](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="a-namecopyfroma--cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom  
 다른 개체 로부터 구분 멤버 변수를 설정 하는 복사 메서드.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `Src`  
 복사할 소스 리본 요소입니다.  
  
##  <a name="a-namegetregularsizea--cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize  
 구분 기호의 크기를 반환합니다.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 내용에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 크기는 지정 된 장치 컨텍스트에 구분 기호입니다.  
  
##  <a name="a-nameisseparatora--cmfcribbonseparatorisseparator"></a><a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator  
 구분 기호 인지를 나타냅니다.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `TRUE` 이 클래스에 대 한 합니다.  
  
##  <a name="a-nameistabstopa--cmfcribbonseparatoristabstop"></a><a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop  
 이 탭은 인지를 나타냅니다.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항상 `FALSE` 이 클래스에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 리본 메뉴 구분 기호 탭은 아닙니다.  
  
##  <a name="a-nameondrawa--cmfcribbonseparatorondraw"></a><a name="ondraw"></a>CMFCRibbonSeparator::OnDraw  
 시스템의 구분 기호는 리본 또는 빠른 실행 도구 모음에 의해 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
##  <a name="a-nameondrawonlista--cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList  
 시스템의 구분 기호 의해 호출 된 **명령을** 목록입니다.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDC`|장치 컨텍스트에 대한 포인터입니다.|  
|[in] `strText`|목록에 표시할 텍스트입니다.|  
|[in] `nTextOffset`|경계 사각형의 왼쪽와 텍스트 사이의 간격입니다.|  
|[in] `rect`|경계 사각형을 지정합니다.|  
|[in] `bIsSelected`|무시됩니다.|  
|[in] `bHighlighted`|무시됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

