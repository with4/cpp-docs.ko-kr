---
title: "CMultiPageDHtmlDialog 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
dev_langs:
- C++
helpviewer_keywords:
- CMultiPageDHtmlDialog class
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c00af20731b2c47a0074366722da3f4a0711ef85
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|(마법사 스타일) 다중 페이지 DHTML 대화 상자 개체를 생성합니다.|  
|[CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog](#cmultipagedhtmldialog__~cmultipagedhtmldialog)|다중 페이지 DHTML 대화 상자 개체를 소멸 시킵니다.|  
  
## <a name="remarks"></a>주의  
 이 작업을 수행 하는 메커니즘은 한 [DHTML 및 URL 이벤트 맵](http://msdn.microsoft.com/en-us/2a7332f0-79d7-46e4-b816-0a618c46777a), 포함 된 [이벤트 맵 포함](http://msdn.microsoft.com/library/5346210f-f8b7-4e28-9d2c-d9d7fd42421d) 각 페이지에 대 한 합니다.  
  
## <a name="example"></a>예제  
 이 다중 페이지 대화 상자에서는 간단한 마법사와 비슷한 기능을 정의 하는 세 가지 HTML 리소스를 가정 합니다. 첫 번째 페이지에는 `Next` 단추, 두 번째는 **Prev** 및 `Next` 단추 및 세 번째는 **Prev** 단추입니다. 처리기 함수를 호출 하는 단추 중 하나를 누르면 [CDHtmlDialog::LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) 적절 한 새 페이지를 로드 합니다.  
  
 (CMyMultiPageDlg.h)에서 클래스 선언의 관련 부분인:  
  
 [!code-cpp[NVC_MFCDocView #&181;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]  
  
 클래스 구현 (CMyMultipageDlg.cpp)의 관련 부분:  
  
 [!code-cpp[NVC_MFCDocView #&182;](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]  
  
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
  
##  <a name="cmultipagedhtmldialog"></a>CMultiPageDHtmlDialog::CMultiPageDHtmlDialog  
 (마법사 스타일) 다중 페이지 DHTML 대화 상자 개체를 생성합니다.  
  
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
 대화 상자 템플릿 리소스의 이름에 해당 하는 null로 끝나는 문자열입니다.  
  
 `szHtmlResID`  
 HTML 리소스의 이름에 해당 하는 null로 끝나는 문자열입니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체에 대 한 포인터 (형식의 [CWnd](../../mfc/reference/cwnd-class.md)) 대화 개체가 속한 합니다. 있으면 **NULL**, 대화 상자 개체의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
 `nIDTemplate`  
 대화 상자 템플릿 리소스의 ID 번호를 포함합니다.  
  
 `nHtmlResID`  
 HTML 리소스의 ID 번호를 포함합니다.  
  
##  <a name="_dtorcmultipagedhtmldialog"></a>CMultiPageDHtmlDialog:: ~ CMultiPageDHtmlDialog  
 다중 페이지 DHTML 대화 상자 개체를 소멸 시킵니다.  
  
```  
virtual ~CMultiPageDHtmlDialog();
```  
  
## <a name="see-also"></a>참고 항목  
 [CDHtmlDialog 클래스](../../mfc/reference/cdhtmldialog-class.md)

