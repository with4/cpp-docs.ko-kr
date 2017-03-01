---
title: "웹 브라우저 스타일 MFC 응용 프로그램 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcweb.project
dev_langs:
- C++
helpviewer_keywords:
- MFC, Web applications
- Web browsers, creating from MFC architecture
- Web browsers
- Web applications, creating
ms.assetid: 257f8c03-33c3-428c-832e-0b70aff6168d
caps.latest.revision: 9
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ccfb093a65c3f9a72b6180c4f415a92ebaf18684
ms.lasthandoff: 02/24/2017

---
# <a name="creating-a-web-browser-style-mfc-application"></a>웹 브라우저 스타일 MFC 응용 프로그램 만들기
로컬 파일 시스템 및 네트워크에서 웹 브라우저 스타일 응용 프로그램 폴더 뿐 아니라 (예: HTML 또는 액티브 문서)는 인터넷 또는 인트라넷에서 정보에 액세스할 수 있습니다. 응용 프로그램의 뷰 클래스를 파생 하 여 [CHtmlView](../../mfc/reference/chtmlview-class.md), 효과적으로 WebBrowser 컨트롤에서 보기를 제공 하 여 응용 프로그램이 웹 브라우저 확인 합니다.  
  
### <a name="to-create-a-web-browser-application-based-on-the-mfc-documentview-architecture"></a>MFC 문서/뷰 아키텍처에 따라 웹 브라우저 응용 프로그램을 만들려면  
  
1.  지침에 따라 [MFC 응용 프로그램을 만드는](../../mfc/reference/creating-an-mfc-application.md)합니다.  
  
2.  MFC 응용 프로그램 마법사에서 [응용 프로그램 종류](../../mfc/reference/application-type-mfc-application-wizard.md) 페이지 있는지 확인 합니다.는 **문서/뷰 아키텍처** 확인란을 선택 합니다. (중 하나를 선택할 수 있습니다 **단일 문서** 또는 **여러 문서**, 하지 않고 **대화 상자 기반**.)  
  
3.  에 [생성 된 클래스 검토](../../mfc/reference/generated-classes-mfc-application-wizard.md) 페이지를 사용 하 여는 **기본 클래스** 드롭다운 메뉴를 `CHtmlView`합니다.  
  
4.  다른 옵션을 선택 하려는 기초 응용 프로그램에 기본 제공 합니다.  
  
5.  **마침**을 클릭합니다.  
  
 WebBrowser 컨트롤 로케이터 URL (Uniform Resource) 탐색 및 하이퍼링크를 통해 웹 검색을 지원 합니다. 컨트롤을 앞으로 탐색할 수 있도록 기록 목록을 관리 하 고 뒤로 이전에 검색 사이트, 폴더 및 문서 키를 누릅니다. 탐색, 하이퍼링크, 기록 목록, 즐겨찾기 및 보안을 직접 처리 하는 컨트롤입니다. 응용 프로그램 호스트 활성 문서도 액티브 문서 컨테이너도 WebBrowser 컨트롤을 사용할 수 있습니다. 따라서 Word 문서 또는 Microsoft Excel 스프레드시트와 같은 서식 있는 문서 수 열고 WebBrowser 컨트롤 내에서 위치에서 편집 합니다. WebBrowser 컨트롤 ActiveX 컨트롤을 호스팅할 수 있는 ActiveX 컨트롤 컨테이너 이기도 합니다.  
  
> [!NOTE]
>  WebBrowser ActiveX 컨트롤 (및 따라서 `CHtmlView`)는 Internet Explorer 4.0에서 버전의 Windows에서 실행 되는 응용 프로그램에만 사용할 수 없거나 나중에 설치 된 합니다.  
  
 때문에 `CHtmlView` 같은 다른 인쇄 되지 않는 Microsoft 웹 브라우저 컨트롤을 지 원하는 단순히 구현 [CView](../../mfc/reference/cview-class.md)-클래스를 파생 합니다. 대신, 프린터 사용자 인터페이스 및 인쇄 WebBrowser 컨트롤을 구현합니다. 결과적으로, `CHtmlView` 가 지원 하지 인쇄 미리 보기, 및 기타 인쇄 지원 기능에 대 한 프레임 워크를 제공 하지 않습니다: 예를 들어 [CView::OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting), [CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting), 및 [CView::OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting), 다른 MFC 응용 프로그램에서 사용할 수 있습니다.  
  
 `CHtmlView`응용 프로그램을 웹 또는 HTML 페이지는 뷰를 제공 하는 웹 브라우저 컨트롤에 대 한 래퍼 역할을 합니다. 마법사에 대 한 재정의 만듭니다는 [OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) Microsoft Visual c + + 웹 사이트에 대 한 탐색 링크를 제공 하는 뷰 클래스의 함수:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
    Navigate2(_T("http://www.msdn.microsoft.com/vstudio/"),
    NULL,
    NULL);

} 
```  
  
 자신의이 사이트를 대체 하거나 사용할 수 있습니다는 [LoadFromResource](../../mfc/reference/chtmlview-class.md#loadfromresource) 멤버 함수를 보기에 대 한 기본 내용으로 프로젝트의 리소스 스크립트에 상주 하는 HTML 페이지를 엽니다. 예:  
  
```  
void CWebView::OnInitialUpdate()  
{  
    CHtmlView::OnInitialUpdate();

 *// TODO: This code navigates to a popular spot on the web. *//  change the code to go where you'd like.  
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


