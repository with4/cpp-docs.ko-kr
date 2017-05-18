---
title: "CSingleDocTemplate 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- templates, SDI
- document templates, single
- single document interface (SDI), applications
- CSingleDocTemplate class
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 78e288dd958e73495a8d513d7fe3427ccc956a61
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate 클래스
SDI(단일 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|`CSingleDocTemplate` 개체를 생성합니다.|  
  
## <a name="remarks"></a>주의  
 SDI 응용 프로그램의 주 프레임 창을 사용 하 여 문서; 표시 하려면 한 번에 한 개의 문서만 열 수 있습니다.  
  
 문서 서식 파일을&3; 가지 유형의 클래스 간의 관계를 정의합니다.  
  
-   문서 클래스에서 파생 되는 **CDocument**합니다.  
  
-   위에 나열 된 문서 클래스에서 데이터를 표시 하는 뷰 클래스 이 클래스에서 파생 시킬 수 있습니다 `CView`, `CScrollView`, `CFormView`, 또는 `CEditView`합니다. (사용할 수 있습니다 `CEditView` 직접.)  
  
-   프레임 창 클래스-보기가 포함 합니다. SDI 문서 서식 파일에 대 한에서이 클래스를 파생 시킬 수 `CFrameWnd`경우 기본 동작을 사용자 지정할 필요가 없습니다; 프레임 창에서 사용할 수 있습니다 `CFrameWnd` 사용자 고유의 클래스를 파생 하지 않고 직접.  
  
 SDI 응용 프로그램는 일반적으로 한 가지 유형의 문서를 지원 하므로 하나만 `CSingleDocTemplate` 개체입니다. 한 번에 한 개의 문서만 열 수 있습니다.  
  
 모든 멤버의 함수를 호출할 필요가 없습니다 `CSingleDocTemplate` 생성자를 제외 하 고 있습니다. 프레임 워크 핸들 `CSingleDocTemplate` 내부적으로 개체입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CSingleDocTemplate`, 참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>CSingleDocTemplate::CSingleDocTemplate  
 `CSingleDocTemplate` 개체를 생성합니다.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDResource`  
 문서 형식으로 사용 하는 리소스의 ID를 지정 합니다. 여기에 메뉴, 아이콘, 액셀러레이터 키 테이블 및 문자열 리소스가 포함 될 수 있습니다.  
  
 문자열 리소스 '\n' 문자로 구분 하는 최대&7; 개의 부분으로 구성 됩니다 ('\n' 문자 자리 표시자로 필요한 부분 문자열이 포함 되지 않은 경우, 후행 '\n' 문자가 필요 하지 않은 반면); 이러한 부분 문자열에는 문서 유형에 대해 설명합니다. 부분 문자열에 대 한 정보를 참조 하십시오. [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)합니다. 이 문자열 리소스를 응용 프로그램의 리소스 파일에서 찾을 수 있습니다. 예:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 문자열 편집기;를 사용 하 여이 문자열을 편집할 수 있습니다. 전체 문자열&7; 별도 항목 아니라 문자열 편집기에서 단일 항목으로 나타납니다.  
  
 이러한 리소스 종류에 대 한 자세한 내용은 참조는 [문자열 편집기](../../windows/string-editor.md)합니다.  
  
 `pDocClass`  
 가리키는 `CRuntimeClass` 문서 클래스의 개체입니다. 이 클래스는 한 **CDocument**-문서를 나타내기 위해 정의한 클래스를 파생 합니다.  
  
 `pFrameClass`  
 가리키는 `CRuntimeClass` 프레임 창 클래스의 개체입니다. 될 수 있는이 클래스는 `CFrameWnd`-클래스를 파생 하거나, `CFrameWnd` 자체의 주 프레임 창에 대 한 기본 동작을 수행 합니다.  
  
 `pViewClass`  
 가리키는 `CRuntimeClass` 뷰 클래스의 개체입니다. 이 클래스는는 `CView`-문서를 표시 하기 위해 정의 하는 클래스를 파생 합니다.  
  
### <a name="remarks"></a>주의  
 동적으로 할당 한 `CSingleDocTemplate` 개체를 전달 `CWinApp::AddDocTemplate` 에서 `InitInstance` 응용 프로그램 클래스의 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocViewSDI #&13;](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI #&14;](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument 클래스](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate 클래스](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)

