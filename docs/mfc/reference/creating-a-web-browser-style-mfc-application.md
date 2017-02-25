---
title: "웹 브라우저 스타일 MFC 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfcweb.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC, 웹 응용 프로그램"
  - "웹 응용 프로그램, 만들기"
  - "웹 브라우저"
  - "웹 브라우저, MFC 아키텍처에서 만들기"
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 웹 브라우저 스타일 MFC 응용 프로그램 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

웹 브라우저 스타일 응용 프로그램에서는 로컬 파일 시스템과 네트워크에 있는 폴더뿐 아니라 HTML이나 액티브 문서와 같은 인터넷 정보 또는 인트라넷 정보에 액세스할 수 있습니다.  [CHtmlView](../../mfc/reference/chtmlview-class.md)에서 응용 프로그램의 뷰 클래스를 파생시키면 WebBrowser 컨트롤이 있는 뷰를 제공하여 응용 프로그램을 웹 브라우저로 쉽게 만들 수 있습니다.  
  
### MFC 문서\/뷰 아키텍처를 기반으로 하는 웹 브라우저 응용 프로그램을 만들려면  
  
1.  [MFC 응용 프로그램 만들기](../../mfc/reference/creating-an-mfc-application.md)의 지시를 따릅니다.  
  
2.  MFC 응용 프로그램 마법사의 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지에서 **문서\/뷰 아키텍처** 상자가 선택되어 있는지 확인합니다. **단일 문서**나 **다중 문서**는 선택할 수 있지만 **대화 상자 기반**은 선택할 수 없습니다.  
  
3.  [생성된 클래스 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지의 **기본 클래스** 드롭다운 메뉴에서 `CHtmlView`를 선택합니다.  
  
4.  원하는 다른 옵션을 모두 선택하여 기초 응용 프로그램을 빌드합니다.  
  
5.  **마침**을 클릭합니다.  
  
 WebBrowser 컨트롤은 하이퍼링크와 URL\(Uniform Resource Locator\) 탐색을 통한 웹 검색을 지원합니다.  이 컨트롤은 사용자가 이전에 검색한 사이트, 폴더, 문서 등을 앞뒤로 찾아볼 수 있도록 검색 기록 목록을 유지합니다.  WebBrowser 컨트롤은 탐색, 하이퍼링크, 검색 기록 목록, 즐겨찾기 및 보안을 직접 처리합니다.  응용 프로그램에서는 WebBrowser 컨트롤을 액티브 문서 컨테이너로 사용하여 액티브 문서를 호스팅할 수도 있습니다.  따라서, Microsoft Excel 스프레드시트나 Word 문서와 같이 다양한 서식을 사용하는 문서를 WebBrowser 컨트롤 내에서 열고 그 자리에서 편집할 수 있습니다.  WebBrowser 컨트롤은 또한 모든 ActiveX 컨트롤을 호스팅할 수 있는 ActiveX 컨트롤 컨테이너입니다.  
  
> [!NOTE]
>  WebBrowser ActiveX 컨트롤과 `CHtmlView`는 Internet Explorer 4.0 이상이 설치된 Windows 버전에서 실행되는 응용 프로그램에서만 사용할 수 있습니다.  
  
 `CHtmlView`는 단순히 Microsoft 웹 브라우저 컨트롤을 구현하기 때문에 다른 [CView](../../mfc/reference/cview-class.md) 파생 클래스와 달리 인쇄를 지원하지 않습니다.  WebBrowser 컨트롤이 오히려 프린터 사용자 인터페이스 및 인쇄 기능을 구현합니다.  결과적으로, `CHtmlView`는 인쇄 미리 보기를 지원하지 않으며 프레임워크에서는 다른 인쇄 지원 함수\(예: 다른 MFC 응용 프로그램에서 사용할 수 있는 [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md), [CView::OnBeginPrinting](../Topic/CView::OnBeginPrinting.md), [CView::OnEndPrinting](../Topic/CView::OnEndPrinting.md) 등\)를 제공하지 않습니다.  
  
 `CHtmlView`는 웹 브라우저 컨트롤의 래퍼 역할을 담당하여 응용 프로그램에 웹 페이지나 HTML 페이지에 대한 뷰를 제공합니다.  마법사에서는 뷰 클래스의 [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) 함수를 재정의하여 Microsoft Visual C\+\+ 웹 사이트에 대한 탐색 링크를 제공합니다.  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),NULL,NULL);  
}  
```  
  
 이 사이트를 직접 만든 다른 사이트로 대체하거나, [LoadFromResource](../Topic/CHtmlView::LoadFromResource.md) 멤버 함수를 사용하여 프로젝트의 리소스 스크립트에 상주하는 HTML 페이지를 뷰의 기본 내용으로 열 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
void CWebView::OnInitialUpdate()  
{  
   CHtmlView::OnInitialUpdate();  
  
   // TODO: This code navigates to a popular spot on the web.  
   //  change the code to go where you'd like.  
   LoadFromResource(IDR_HTML1);  
}  
```  
  
## 참고 항목  
 [MFC Sample MFCIE](http://msdn.microsoft.com/ko-kr/7391aa0c-fca8-4994-a6c9-6c5c7470fba0)   
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [속성 페이지](../../ide/property-pages-visual-cpp.md)   
 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)   
 [Deploying Applications](http://msdn.microsoft.com/ko-kr/4ff8881d-0daf-47e7-bfe7-774c625031b4)