---
title: "CFormView 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFormView
dev_langs:
- C++
helpviewer_keywords:
- views, containing controls
- CFormView class
- form views
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
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
ms.openlocfilehash: 82b38b04aa3cf2368d41ee20847c952c3082d4e4
ms.lasthandoff: 02/24/2017

---
# <a name="cformview-class"></a>CFormView 클래스
폼 뷰에 사용되는 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|`CFormView` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Cformview:: Isinitdlgcompleted](#isinitdlgcompleted)|초기화하는 동안 동기화에 사용됩니다.|  
  
## <a name="remarks"></a>주의  
 폼 뷰는 기본적으로 컨트롤을 포함하는 뷰입니다. 이러한 컨트롤은 대화 상자 템플릿 리소스에 따라 배치됩니다. 응용 프로그램에서 폼을 사용하려면 `CFormView`를 사용합니다. 이러한 뷰 스크롤을 사용 하 여 필요에 따라 지원는 [CScrollView](../../mfc/reference/cscrollview-class.md) 기능입니다.  
  
 중이면 [폼 기반 응용 프로그램을 만드는](../../mfc/reference/creating-a-forms-based-mfc-application.md), 기반 해당 뷰 클래스를 만들 수 있습니다 `CFormView`, 폼 기반 응용 프로그램을 만드는 합니다.  
  
 새로운 삽입할 수도 있습니다 [양식 항목](../../mfc/form-views-mfc.md) 응용 프로그램 문서 뷰를 기반으로 합니다. 응용 프로그램이 초기에 폼을 지원하지 않은 경우에도 새 폼을 삽입하면 Visual C++에서 이 지원 기능을 추가합니다.  
  
 폼 기반 응용 프로그램을 만들 때는 MFC 응용 프로그램 마법사 및 클래스 추가 명령을 사용하는 것이 좋습니다. 이러한 메서드를 사용 하지 않고 폼 기반 응용 프로그램 만들기, 참조 하는 경우 [폼 기반 응용 프로그램을 만드는](../../mfc/reference/creating-a-forms-based-mfc-application.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="a-namecformviewa--cformviewcformview"></a><a name="cformview"></a>CFormView::CFormView  
 `CFormView` 개체를 생성합니다.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTemplateName`  
 대화 상자 템플릿 리소스의 이름에 해당 하는 null로 끝나는 문자열을 포함 합니다.  
  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID 번호를 포함합니다.  
  
### <a name="remarks"></a>주의  
 파생 된 형식의 개체를 만들 때 `CFormView`, view 개체를 만들고 보기의 기반이 되는 대화 상자 리소스를 식별 하는 생성자 중 하나를 호출 합니다. (생성자에는 문자열을 인수로 전달) 이름 또는 ID (pass 인수로 부호 없는 정수)가 리소스를 식별할 수 있습니다.  
  
 폼 보기 창 및 자식 컨트롤 될 때까지 만들어지지 않습니다 `CWnd::Create` 호출 됩니다. `CWnd::Create`문서 서식 파일에 의해 제어 되는 문서와 뷰 만들기 프로세스를의 일환으로 프레임 워크에 의해 호출 됩니다.  
  
> [!NOTE]
>  파생된 클래스의 *해야* 자체 생성자를 제공 합니다. 생성자에는 생성자를 호출 `CFormView::CFormView`, 리소스 이름 또는 ID를 인수로 위의 클래스 개요와 같이 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&90;](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView #&91;](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="a-nameisinitdlgcompleteda--cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a>Cformview:: Isinitdlgcompleted  
 MFC에서 다른 작업을 수행하기 전에 초기화가 완료되었는지 확인하는 데 사용됩니다.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 대화 상자에 대한 초기화 함수가 완료된 경우 true입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [MFC 샘플 VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView 클래스](../../mfc/reference/cscrollview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)   
 [CScrollView 클래스](../../mfc/reference/cscrollview-class.md)

