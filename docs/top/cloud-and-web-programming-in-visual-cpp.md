---
title: "Visual C++의 클라우드 및 웹 프로그래밍 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: 13
caps.handback.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Visual C++의 클라우드 및 웹 프로그래밍
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.  
  
 [Microsoft Azure 모바일 서비스](http://www.windowsazure.com/develop/mobile/)  
 Microsoft Azure 모바일 서비스에 연결할 Windows 스토어 앱이나 Windows 데스크톱 앱에서 사용할 수 있는 API를 제공합니다. 웹 사이트의 대부분 예제는 C\#으로 작성되지만 C\+\+를 사용할 수도 있습니다. 자세한 내용은 [빠른 시작: C\+\+를 사용하여 모바일 서비스 추가](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx)를 참조하세요.  
  
 [라이브 REST 인터페이스](http://msdn.microsoft.com/library/live/hh243648.aspx)  
 Windows 스토어 앱, Windows 데스크톱 앱 또는 C\+\+ Linux 응용 프로그램을 사용하여 SkyDrive, Outlook.com 및 Skype와 같은 [라이브](http://msdn.microsoft.com/live/ff519582) 서비스에 연결할 수 있는 REST 끝점을 제공합니다. C\+\+ 앱에서는 .NET 앱에만 적용되는 Live SDK를 통과하지 않고 직접 이들 끝점을 사용할 수 있습니다.  
  
 [C\+\+ REST SDK\(코드명 "Casablanca"\)](../top/cpp-rest-sdk-codename-casablanca.md)  
 플랫폼 간 호환성을 위해 디자인되고 운영 체제의 데스크톱 앱에서 다시 Windows 7 및 Windows Server 2012로 사용하도록 디자인된 편리한 비동기 HTTP 래퍼 메서드를 제공합니다. 유니버설 Windows 플랫폼 앱에서 이러한 메서드를 사용할 수도 있지만 유니버설 Windows 플랫폼만 대상으로 지정한 앱에는 `Windows::Web:HttpClient` 클래스를 사용하는 것이 좋습니다. C\+\+ REST SDK\(코드명 "Casablanca"\)에서는 REST 호출을 지원하고 JSON 데이터를 C\+\+ 형식으로 변환하는 도우미 클래스도 제공합니다. SDK는 [CodePlex](http://casablanca.codeplex.com/)에서 사용할 수 있으며 [라이브](http://msdn.microsoft.com/live/ff519582) 서비스에 연결하기 위한 도우미 메서드를 제공하는 [live\_connect.h](http://casablanca.codeplex.com/SourceControl/latest#Release/collateral/Samples/WindowsLiveAuth/live_connect.h)과 같은 샘플 파일을 포함합니다.  
  
 [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 System.Web 네임스페이스에 있는 같은 이름의 .NET Framework 클래스에서 모델링된 Windows 런타임 HTTP 클라이언트 클래스입니다.`HttpClient`는 HTTP를 통한 비동기 업로드 및 다운로드와 사용자 지정 HTTP 처리기를 파이프라인에 삽입할 수 있게 하는 파이프라인 필터를 완벽하게 지원합니다. Windows SDK에는 데이터 통신 연결 네트워크, OAuth 인증 등에 대한 샘플 필터가 포함됩니다.  
  
 [IXMLHTTPRequest2 인터페이스](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 HTTP를 통해 인터넷에 연결할 Windows 스토어 앱이나 Windows 데스크톱 앱에서 사용하고 GET, PUT 및 기타 HTTP 명령을 실행할 수 있는 네이티브 COM 인터페이스를 제공합니다. 자세한 내용은 [연습: 작업 및 XML HTTP 요청을 사용하여 연결](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)을 참조하세요.  
  
 [Windows 인터넷\(WinInet\)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 인터넷에 연결할 Windows 데스크톱 앱에서 사용할 수 있는 Windows API입니다.  
  
## 참고 항목  
 [Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)   
 [네트워크 및 웹 서비스\(C\#\/VB\/C\+\+ 및 XAML을 사용하는 Windows 스토어 앱\)에 연결](http://msdn.microsoft.com/library/windows/apps/br229573.aspx)