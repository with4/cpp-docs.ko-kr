---
title: "CMultiDocTemplate 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs: C++
helpviewer_keywords: CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d5862a547b41ec8d359b09795f7b9985530fc97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate 클래스
MDI(다중 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 MDI 응용 프로그램이 문서를 표시 하며 각 작업 영역 사용자 0 개 이상의 문서 프레임 창을 열 수 있습니다 사용할으로 주 프레임 창을 사용 합니다. MDI의 자세한 설명을 참조 하십시오. *소프트웨어 디자인에 대 한 Windows 인터페이스 지침*합니다.  
  
 문서 서식 파일을 3 가지 유형의 클래스 간의 관계를 정의합니다.  
  
-   문서 클래스에서 파생 되는 [CDocument](../../mfc/reference/cdocument-class.md)합니다.  
  
-   위에 나열 된 문서 클래스에서 데이터를 표시 하는 뷰 클래스 이 클래스를 파생 시켜 [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, 또는 `CEditView`합니다. (사용할 수 있습니다 `CEditView` 직접.)  
  
-   프레임 창 클래스-보기가 포함 합니다. 이 클래스를 파생 시켜 MDI 문서 서식 파일에 대 한 `CMDIChildWnd`, 문서 프레임 창 동작을 사용자 지정할 필요가 없습니다 경우 사용할 수 있습니다 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 사용자 고유의 클래스를 파생 하지 않고 직접 합니다.  
  
 MDI 응용 프로그램 문서 형식을 여러 개 지원할 수 있습니다 및 동시에 다른 형식의 문서를 열 수 있습니다. 응용 프로그램에서 지 원하는 각 문서 유형에 대 한 하나의 문서 서식 파일을 있습니다. 예를 들어 MDI 응용 프로그램 모두 스프레드시트 및 텍스트 문서를 지 원하는 경우 응용 프로그램에는 두 개의 `CMultiDocTemplate` 개체입니다.  
  
 응용 프로그램 사용자가 새 문서를 만들 때 문서 템플릿을 사용 합니다. 응용 프로그램이 둘 이상의 형식의 문서를 지 원하는 경우 프레임 워크는 문서 템플릿을 지원 되는 문서 유형의 이름을 가져옵니다 및 새 파일 대화 상자에서 목록에 표시 합니다. 사용자가 문서 종류를 선택 되 면 응용 프로그램 문서 클래스 개체, 프레임 창 개체 및 view 개체를 만들고에 연결 합니다.  
  
 모든 멤버의 함수를 호출할 필요가 없습니다 `CMultiDocTemplate` 생성자를 제외 하 고 있습니다. 프레임 워크 핸들 `CMultiDocTemplate` 내부적으로 개체입니다.  
  
 대 한 자세한 내용은 `CMultiDocTemplate`, 참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>CMultiDocTemplate::CMultiDocTemplate  
 `CMultiDocTemplate` 개체를 생성합니다.  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDResource`  
 문서 종류를 사용 하는 리소스의 ID를 지정 합니다. 이 메뉴, 아이콘, 액셀러레이터 키 테이블 및 문자열 리소스 포함 될 수 있습니다.  
  
 '\N' 문자로 구분 되는 최대 7 개의 부분 문자열로 이루어진 문자열 리소스 구성 (부분 문자열에 포함 되지 않은 경우 '\n' 문자 자리 표시자 변수로 필요; 그러나 후행 '\n' 문자가 필요 하지 않은); 이러한 부분 문자열에는 문서 유형에 대해 설명합니다. 부분 문자열 대 한 자세한 내용은 참조 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)합니다. 이 문자열 리소스를 응용 프로그램의 리소스 파일에서 찾을 수 있습니다. 예:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 '\N' 문자로 시작 하는 첫 번째 하위 문자열이 MDI 응용 프로그램에 대 한 사용 되지 않으며 있으므로 포함 되지 않은 때문입니다. 문자열 편집기;를 사용 하 여이 문자열을 편집할 수 있습니다. 전체 문자열 7 개 항목을 구분이 아니라 문자열 편집기에서 단일 항목으로 표시 됩니다.  
  
 이러한 리소스 종류에 대 한 자세한 내용은 참조 [리소스 편집기](../../windows/resource-editors.md)합니다.  
  
 `pDocClass`  
 가리키는 `CRuntimeClass` 문서 클래스의 개체입니다. 이 클래스는는 **CDocument**-문서를 나타내기 위해 정의한 클래스를 파생 합니다.  
  
 `pFrameClass`  
 가리키는 `CRuntimeClass` 프레임 창 클래스의 개체입니다. 될 수 있는이 클래스는 `CMDIChildWnd`-파생 클래스가 될 수 있습니다 또는 `CMDIChildWnd` 자체 문서 프레임 창에 대 한 기본 동작을 수행 합니다.  
  
 `pViewClass`  
 가리키는 `CRuntimeClass` 뷰 클래스의 개체입니다. 이 클래스는는 `CView`-문서를 표시 하기 위해 정의 하는 클래스를 파생 합니다.  
  
### <a name="remarks"></a>설명  
 동적으로 하나를 할당 `CMultiDocTemplate` 응용 프로그램을 지원 하 고 각 전달 각 문서 유형에 대 한 개체 `CWinApp::AddDocTemplate` 에서 `InitInstance` 응용 프로그램 클래스의 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 두 번째 예제는 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate 클래스](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
