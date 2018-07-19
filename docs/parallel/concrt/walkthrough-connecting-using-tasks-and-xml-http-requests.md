---
title: '연습: 작업 및 XML HTTP 요청을 사용 하 여 연결 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 411d52201aad69a94267615cd0a2acbe6376f64d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692589"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>연습: 작업 및 XML HTTP 요청을 사용하여 연결
사용 하는 방법을 보여 주는이 예제는 [IXMLHTTPRequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) 및 [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) 함께 웹 서비스에는 유니버설 Windows 플랫폼 (UWP에 HTTP GET 및 POST 요청을 보낼 인터페이스 ) 응용 프로그램입니다. `IXMLHTTPRequest2`를 작업과 함께 결합하여 다른 작업을 사용하여 구성되는 코드를 작성할 수 있습니다. 예를 들어 일련의 작업 중 일부로 다운로드 작업을 사용할 수 있습니다. 다운로드 작업은 작업이 취소되는 경우에도 응답할 수 있습니다.  
  
> [!TIP]
>  또한 c + + 응용 프로그램을 사용 하 여 UWP 앱에서 나 데스크톱 c + + 응용 프로그램에서에서 HTTP 요청을 수행 하는 c + + REST SDK를 사용할 수 있습니다. 자세한 내용은 참조 하십시오. [c + + REST SDK (코드명 "Casablanca")](https://github.com/Microsoft/cpprestsdk)합니다.  
  
 작업에 대 한 자세한 내용은 참조 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)합니다. UWP 앱에서 작업을 사용 하는 방법에 대 한 자세한 내용은 참조 [c + +의 비동기 프로그래밍](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps) 및 [비동기 작업 만들기 c + +의 UWP 앱 용](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)합니다.  
  
 이 문서에서는 먼저 `HttpRequest` 및 해당 지원 클래스를 만드는 방법을 보여 줍니다. C + + 및 XAML을 사용 하는 UWP 앱에서이 클래스를 사용 하는 방법을 보여 줍니다.  
  
 사용 하는 전체 예제는 `HttpReader` 참조 클래스는이 문서에 설명 된 [개발 Bing Maps Trip Optimizer, JavaScript 및 c + + Windows 스토어 앱](http://msdn.microsoft.com/library/974cf025-de1a-4299-b7dd-c6c7bf0e5d30)합니다. 사용 하는 또 다른 예에 대 한 `IXMLHTTPRequest2` 않습니다 작업 사용을 제외한 참조 [빠른 시작: XML HTTP 요청 (IXMLHTTPRequest2)를 사용 하 여 연결](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)합니다.  
  
> [!TIP]
>  `IXMLHTTPRequest2` 및 `IXMLHTTPRequest2Callback` 는 UWP 앱에서 사용 하기 위해 권장 되는 인터페이스입니다. 데스크톱 응용 프로그램에서 사용할 수 있도록 이 예제를 조정할 수도 있습니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest, HttpRequestBuffersCallback 및 HttpRequestStringCallback 클래스 정의  
 `IXMLHTTPRequest2` 인터페이스를 사용하여 HTTP를 통한 웹 요청을 만드는 경우 서버 응답을 받고 다른 이벤트에 대응하는 `IXMLHTTPRequest2Callback` 인터페이스를 구현합니다. 이 예제에서는 웹 요청을 만들기 위해 `HttpRequest` 클래스를 정의하고, 응답을 처리하기 위해 `HttpRequestBuffersCallback` 및 `HttpRequestStringCallback` 클래스를 정의합니다. `HttpRequestBuffersCallback` 및 `HttpRequestStringCallback` 클래스는 `HttpRequest` 클래스를 지원합니다. 응용 프로그램 코드에서 `HttpRequest` 클래스만 사용하여 작업할 수 있습니다.  
  
 `GetAsync` 클래스의 `PostAsync` 및 `HttpRequest` 메서드는 각각 HTTP GET 및 POST 작업을 시작할 수 있도록 합니다. 이러한 메서드는 `HttpRequestStringCallback` 클래스를 사용하여 서버 응답을 문자열로 읽습니다. `SendAsync` 및 `ReadAsync` 메서드를 사용하면 큰 콘텐츠를 청크로 스트리밍할 수 있습니다. 이러한 메서드는 각각 반환 [concurrency:: task](../../parallel/concrt/reference/task-class.md) 작업을 나타내는입니다. `GetAsync` 및 `PostAsync` 메서드는 `task<std::wstring>` 부분이 서버의 응답을 나타내는 `wstring` 값을 생성합니다. `SendAsync` 및 `ReadAsync` 메서드는 `task<void>` 값을 생성합니다. 이러한 작업은 보내기 및 읽기 작업이 끝날 때 완료됩니다.  
  
 때문에 `IXMLHTTPRequest2` 인터페이스가 비동기적으로 작동, 사용 하 여이 예제 [concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) 콜백 개체가 완료 하거나 다운로드 작업을 취소 한 후 완료 되는 작업을 만들려고 합니다. `HttpRequest` 클래스는 최종 결과를 설정하기 위해 이 작업에서 작업 기반 연속 작업을 만듭니다. `HttpRequest` 클래스는 작업 기반 연속 작업을 사용하여 이전 작업이 오류를 생성하거나 취소되는 경우에도 연속 작업이 실행되도록 합니다. 작업 기반 연속에 대 한 자세한 내용은 참조 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
 취소를 지원하기 위해 `HttpRequest`, `HttpRequestBuffersCallback` 및 `HttpRequestStringCallback` 클래스는 취소 토큰을 사용합니다. `HttpRequestBuffersCallback` 및 `HttpRequestStringCallback` 사용 하는 클래스는 [concurrency::cancellation_token::register_callback](reference/cancellation-token-class.md#register_callback) 메서드가 작업 완료 이벤트가 취소에 응답할 수 있도록 합니다. 이 취소 콜백은 다운로드를 중단합니다. 취소에 대 한 자세한 내용은 참조 하십시오. [취소](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)합니다.  
  
#### <a name="to-define-the-httprequest-class"></a>HttpRequest 클래스를 정의하려면  
  
1.  Visual c + +를 사용 하 여 **새 응용 프로그램 (XAML)** 템플릿을 빈 XAML 응용 프로그램 프로젝트를 만듭니다. 이 예에서는 프로젝트 이름을 `UsingIXMLHTTPRequest2`로 지정합니다.  
  
2.  HttpRequest.h라는 헤더 파일과 HttpRequest.cpp라는 소스 파일을 프로젝트에 추가합니다.  
  
3.  pch.h에서 다음 코드를 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]  
  
4.  HttpRequest.h에서 다음 코드를 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]  
  
5.  HttpRequest.cpp에서 다음 코드를 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]  
  
## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP 앱에서 HttpRequest 클래스를 사용 하 여  
 이 섹션에서는 사용 하는 방법을 보여 줍니다.는 `HttpRequest` UWP 앱에서 클래스입니다. 응용 프로그램은 URL 리소스를 정의하는 입력 상자, GET 및 POST 작업을 수행하는 단추 명령 및 현재 작업을 취소하는 단추 명령을 제공합니다.  
  
#### <a name="to-use-the-httprequest-class"></a>HttpRequest 클래스를 사용하려면  
  
1.  MainPage.xaml에서 정의 된 [StackPanel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.stackpanel.aspx) 다음과 같이 요소입니다.  
  
     [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]  
  
2.  MainPage.xaml.h에서 다음 `#include` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]  
  
3.  MainPage.xaml.h에서 다음 `private` 멤버 변수를 `MainPage` 클래스에 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]  
  
4.  MainPage.xaml.h에서 `private` 메서드 `ProcessHttpRequest`를 선언합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]  
  
5.  MainPage.xaml.cpp에서 다음 `using` 문을 추가합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]  
  
6.  MainPage.xaml.cpp에서 `GetButton_Click` 클래스의 `PostButton_Click`, `CancelButton_Click` 및 `MainPage` 메서드를 구현합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]  
  
    > [!TIP]


    >  응용 프로그램에 취소에 대 한 지원이 필요 하지 않으면, 전달 [concurrency:: cancellation_token:: none](reference/cancellation-token-class.md#none) 에 `HttpRequest::GetAsync` 및 `HttpRequest::PostAsync` 메서드.  


  
7.  MainPage.xaml.cpp에서 `MainPage::ProcessHttpRequest` 메서드를 구현합니다.  
  
     [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]  
  
8.  프로젝트 속성에서 아래 **링커**, **입력**, 지정 `shcore.lib` 및 `msxml6.lib`합니다.  
  
 다음은 실행 중인 응용 프로그램입니다.  
  
 ![실행 중인 Windows 런타임 앱](../../parallel/concrt/media/concrt_usingixhr2.png "concrt_usingixhr2")  
  
## <a name="next-steps"></a>다음 단계  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)  
  
## <a name="see-also"></a>참고 항목  
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [C + +의 비동기 프로그래밍](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)   
 [C + + UWP 앱 용 비동기 작업 만들기](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)   
 [빠른 시작: XML HTTP 요청 (IXMLHTTPRequest2)를 사용 하 여 연결](http://msdn.microsoft.com/en-us/cc7aed53-b2c5-4d83-b85d-cff2f5ba7b35)   
 [task 클래스 (동시성 런타임)](../../parallel/concrt/reference/task-class.md)   
 [task_completion_event 클래스](../../parallel/concrt/reference/task-completion-event-class.md)
