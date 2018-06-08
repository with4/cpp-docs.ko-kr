---
title: 클래스 추가 대화 상자 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.addclass
dev_langs:
- C++
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6c4f108b30babcc30ffc5f2fc4c63fe764db2e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33339776"
---
# <a name="add-class-dialog-box"></a>클래스 추가 대화 상자
**클래스 추가** 대화 상자에는 다음을 수행할 수 있는 템플릿이 있습니다.  
  
-   사용 가능한 경우 해당 코드 마법사를 엽니다. 자세한 내용은 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)를 참조하세요.  
  
 \- 또는 -  
  
-   프로젝트에 적절한 파일 및 소스 코드를 추가하여 새 클래스를 자동으로 만듭니다.  
  
 **클래스 추가** 대화 상자는 **프로젝트** 메뉴, **솔루션 탐색기**또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 액세스할 수 있습니다.  
  
> [!NOTE]
>  현재 프로젝트에 적합하지 않은 클래스를 추가하려고 하면 오류 메시지가 표시됩니다. **확인** 을 클릭하여 **클래스 추가** 대화 상자로 돌아갑니다.  
  
## <a name="add-class-templates"></a>클래스 추가 템플릿  
 NET, ATL, MFC 및 제네릭이라는 네 가지 범주의 **클래스 추가** 템플릿이 있습니다. **템플릿** 창에서 템플릿을 선택하면 선택 항목을 설명하는 텍스트가 **범주** 및 **템플릿** 창 아래에 나타납니다.  
  
### <a name="net"></a>.NET  
  
|템플릿|마법사|  
|--------------|------------|  
|ASP.NET 웹 서비스|사용할 수 없음|  
|구성 요소 클래스(.NET)|사용할 수 없음|  
|설치 관리자 클래스(.NET)|사용할 수 없음|  
|사용자 정의 컨트롤(.NET)|사용할 수 없음|  
|Windows Form(.NET)|사용할 수 없음|  
  
### <a name="atl"></a>ATL  
  
|템플릿|마법사|  
|--------------|------------|  
|MFC에 ATL 지원 추가|사용할 수 없음|  
|ATL Active Server Page 구성 요소|[ATL Active Server Page 구성 요소 마법사](../atl/reference/atl-active-server-page-component-wizard.md)|  
|ATL 컨트롤|[ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)|  
|ATL 대화 상자|[ATL 대화 상자 마법사](../atl/reference/atl-dialog-wizard.md)|  
|ATL COM+ 1.0 구성 요소|[ATL COM+ 1.0 구성 요소 마법사](../atl/reference/atl-com-plus-1-0-component-wizard.md)|  
|ATL OLEDB 소비자|[ATL OLE DB 소비자 마법사](../atl/reference/atl-ole-db-consumer-wizard.md)|  
|ATL OLEDB 공급자|[ATL OLE DB 공급자 마법사](../atl/reference/atl-ole-db-provider-wizard.md)|  
|ATL 속성 페이지|[ATL 속성 페이지 마법사](../atl/reference/atl-property-page-wizard.md)|  
|ATL 단순 개체|[ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)|  
|WMI 이벤트 공급자|WMI 이벤트 제공자 마법사|  
|WMI 인스턴스 공급자|WMI 인스턴스 제공자 마법사|  
  
### <a name="mfc"></a>MFC  
  
|템플릿|마법사|  
|--------------|------------|  
|MFC 클래스|[MFC 클래스 추가 마법사](../mfc/reference/mfc-add-class-wizard.md)|  
|ActiveX 컨트롤의 MFC 클래스|[ActiveX 컨트롤의 클래스 추가 마법사](../ide/add-class-from-activex-control-wizard.md)|  
|TypeLib의 MFC 클래스|[Typelib에서 클래스 추가 마법사](../mfc/reference/add-class-from-typelib-wizard.md)|  
|MFC ODBC 소비자|[MFC ODBC 소비자 마법사](../mfc/reference/mfc-odbc-consumer-wizard.md)|  
  
### <a name="generic-classes"></a>제네릭 클래스  
  
|템플릿|마법사|  
|--------------|------------|  
|일반 C++ 클래스|[일반 C++ 클래스 마법사](../ide/generic-cpp-class-wizard.md)|  
  
## <a name="see-also"></a>참고 항목  
 [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)   
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)   
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 메시지 처리기](../mfc/reference/adding-an-mfc-message-handler.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)