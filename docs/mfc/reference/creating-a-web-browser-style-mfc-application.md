---
title: 웹 브라우저 스타일 MFC 응용 프로그램 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications [MFC], creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1553f7ccc3b22b4e3d76d8c49d94ba2a61c19e97
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122555"
---
# <a name="creating-a-web-browser-style-mfc-application"></a>웹 브라우저 스타일 MFC 응용 프로그램 만들기
네트워크와 로컬 파일 시스템에는 웹 브라우저 스타일 응용 프로그램 폴더 뿐 아니라 (예: HTML 또는 활성 문서) 인터넷 또는 인트라넷에서 정보에 액세스할 수 있습니다. 응용 프로그램의 뷰 클래스를 파생 하 여 [CHtmlView](../../mfc/reference/chtmlview-class.md), 효과적으로 뷰에 WebBrowser 컨트롤이 제공 하 여 응용 프로그램 웹 브라우저 확인 합니다.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC 문서/뷰 아키텍처에 따라 웹 브라우저 응용 프로그램을 만들려면  
  
1.  지시에 따라 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.  
  
2.  MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지 있는지 확인 합니다.는 **문서/뷰 아키텍처** 확인란을 선택 합니다. (하나를 선택할 수 **단일 문서** 또는 **여러 문서**, 아닌 **대화 상자 기반**.)  
  
3.  에 [생성 된 클래스 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지에서 사용 하 여는 **기본 클래스** 선택 하려면 드롭다운 메뉴 `CHtmlView`합니다.  
  
4.  다른 옵션이 원하는 기초 응용 프로그램에 기본 제공을 선택 합니다.  
  
5.  **마침**을 클릭합니다.  
  
 WebBrowser 컨트롤 하이퍼링크와 Locator URL (Uniform Resource) 탐색을 통해 웹 검색을 지원 합니다. 컨트롤을 앞으로 탐색할 수 있는 기록 목록을 유지 하 고 뒤로 이전에 검색 사이트, 폴더 및 문서 키를 누릅니다. 탐색, 하이퍼링크, 기록 목록, 즐겨찾기 및 보안을 직접 처리 하는 컨트롤입니다. 응용 프로그램 호스트 액티브 문서도 액티브 문서 컨테이너도 WebBrowser 컨트롤을 사용할 수 있습니다. 따라서 Microsoft Excel 스프레드시트 같은 서식 있는 문서 또는 Word 문서를 열고 수 WebBrowser 컨트롤 내에서 위치에서 편집 합니다. WebBrowser 컨트롤의 ActiveX 컨트롤을 호스팅할 수 있는 ActiveX 컨트롤 컨테이너 이기도 합니다.  
  
> [!NOTE]
>  WebBrowser ActiveX 컨트롤 (및 따라서 `CHtmlView`) Internet Explorer 4.0에서 Windows 버전에서 실행 되는 응용 프로그램에만 사용할 수 없거나 이상이 설치 된 합니다.  
  
 때문에 `CHtmlView` 인쇄 다른 유사 하지 않음 하기 위한 지원을 Microsoft 웹 브라우저 컨트롤을 구현 하기만 하면 [CView](../../mfc/reference/cview-class.md)-파생 된 클래스입니다. 대신, 프린터 사용자 인터페이스 및 인쇄 WebBrowser 컨트롤을 구현합니다. 결과적으로, `CHtmlView` 않습니다 인쇄 미리 보기, 지원 하지 않으며 기타 인쇄 지원 기능에 대 한 프레임 워크를 제공 하지 않습니다: 예를 들어 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), 및 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), 다른 MFC 응용 프로그램에서 사용할 수 있습니다.  
  
 `CHtmlView` 응용 프로그램 웹 또는 HTML 페이지는 뷰를 제공 하는 웹 브라우저 컨트롤에 대 한 래퍼 역할을 합니다. 마법사에서는 재정의를 만듭니다.는 [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft Visual c + + 웹 사이트를 탐색 링크를 제공 하는 뷰 클래스의 함수:  
  
```cpp
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
        NULL,
        NULL);
}
```

직접 중 하 나와이 사이트를 교체 하거나, 사용할 수 있습니다는 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) 멤버 함수는 보기에 대 한 기본 내용으로 프로젝트의 리소스 스크립트에 있는 HTML 페이지를 엽니다. 예를 들어:  
  
```cpp
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

    // TODO: This code navigates to a popular spot on the web.
    // Change the code to go where you'd like.  
    LoadFromResource(IDR_HTML1);
}
```  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MFCIE](http://msdn.microsoft.com/en-us/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [응용 프로그램 배포](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

