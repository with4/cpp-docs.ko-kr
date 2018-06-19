---
title: CMFCToolBarComboBoxEdit 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d541702d73befedab72ad7b130b56a125a5817aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376310"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit 클래스
프레임 워크를 사용 하 여는 `CMFCToolBarComboBoxEdit` 클래스는 편집 가능한 콤보 상자 컨트롤 처럼 동작 하는 도구 모음 단추를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCToolBarComboBoxEdit : public CEdit  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit](#cmfctoolbarcomboboxedit)|`CMFCToolBarComboBoxEdit` 개체를 생성합니다.|  
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|창 메시지를 변환 하 여 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|  
  
### <a name="remarks"></a>설명  
 클래스를 파생는 `CMFCToolBarComboBoxEdit` 편집 작업을 사용자 지정 하는 클래스입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxtoolbarcomboboxbutton.h  
  
##  <a name="cmfctoolbarcomboboxedit"></a>  CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit  
 `CMFCToolBarComboBoxEdit` 개체를 생성합니다.  
  
```  
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `combo`  
 에 대 한 참조는 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체 콤보 상자 컨트롤을 포함 하는 도구 모음 단추입니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는의 개체를 생성 하는 `CMFCToolBarComboBoxEdit` 클래스입니다. 이 코드 조각은의 일부인는 [IE 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarComboBoxButton 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
