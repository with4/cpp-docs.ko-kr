---
title: CMultiPageDHtmlDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be83e3791121bdea4d7f650f7d6801517df31ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog 클래스
여러 페이지로 구성된 대화 상자는 여러 HTML 페이지를 순차적으로 표시하고 각 페이지의 이벤트를 처리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|여러 페이지 (마법사-스타일) DHTML 대화 개체를 만듭니다.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|다중 페이지 DHTML 대화 상자 개체를 제거합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업을 수행 하기 위한 메커니즘은는 [DHTML 및 URL 이벤트 맵](dhtml-event-maps.md), 포함 된 각 페이지에 대 한 이벤트 맵을 포함 합니다.  
  
## <a name="example"></a>예제  
 이 다중 페이지 대화 상자에서는 간단한 마법사와 비슷한 기능을 정의 하는 세 가지 HTML 리소스를 가정 합니다. 첫 번째 페이지에는 `Next` 단추, 두 번째는 **Prev** 및 `Next` 단추 및 세 번째는 **Prev** 단추입니다. 처리기 함수를 호출 하는 단추 중 하나를 누르면 [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) 적절 한 새 페이지를 로드 합니다.  
  
 (CMyMultiPageDlg.h)에서 클래스 선언의 관련 부분인:  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 (CMyMultipageDlg.cpp)에서 클래스 구현의 관련 부분인:  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdhtml.h  
  
##  <a name="cmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 여러 페이지 (마법사-스타일) DHTML 대화 개체를 만듭니다.  
  
```  
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID = NULL,  
    CWnd* pParentWnd = NULL);

 
CMultiPageDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd* pParentWnd = NULL);  
  
CMultiPageDHtmlDialog();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszTemplateName`  
 대화 상자 템플릿 리소스의 이름을 나타내는 null로 끝나는 문자열.  
  
 `szHtmlResID`  
 HTML 리소스의 이름을 나타내는 null로 끝나는 문자열.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체에 대 한 포인터 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 상자 개체 속해 있는 합니다. 이 경우 **NULL**, 대화 상자 개체의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID 번호를 포함합니다.  
  
 `nHtmlResID`  
 HTML 리소스의 ID 번호를 포함합니다.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>  CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 다중 페이지 DHTML 대화 상자 개체를 제거합니다.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>참고 항목  
 [CDHtmlDialog 클래스](../../mfc/reference/cdhtmldialog-class.md)
