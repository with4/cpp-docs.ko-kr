---
title: "클라우드 및 Visual c + +에서 프로그래밍 웹 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-azure
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c04939aea508afed60b32ae51d627a1f5d902fd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++의 클라우드 및 웹 프로그래밍
C++에는 웹 및 클라우드에 연결하기 위한 다양한 옵션이 있습니다.  
  
 [Microsoft Azure 모바일 서비스](http://www.windowsazure.com/develop/mobile/)  
 유니버설 Windows 플랫폼 (UWP) 앱 이나 Windows 데스크톱 앱에서 Windows Azure 모바일 서비스에 연결 하는 데 사용할 수 있는 Api를 제공 합니다. 웹 사이트의 대부분 예제는 C#으로 작성되지만 C++를 사용할 수도 있습니다. 자세한 내용은 [빠른 시작: C++를 사용하여 모바일 서비스 추가](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx)를 참조하세요.  

 [C + + 용 Microsoft Azure 저장소 클라이언트 라이브러리](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)  
 C + +에 대 한 Azure 저장소 클라이언트 라이브러리에서는 다음 기능에 제한 되지 않음 포함 한 Azure 저장소를 사용 하기 위한 포괄적인 API를 제공 합니다.

- 만들기, 읽기, 삭제 및 blob 컨테이너, 테이블 및 큐를 나열 합니다.
- 만들기, 읽기, blob 나열 및 복사 더하기 한 읽기 및 쓰기 blob 범위를 삭제 합니다.
- 삽입, 삭제, replace, merge 및 Azure 테이블의 엔터티를 쿼리 합니다.
- Enqueue 및 Azure 큐에서 메시지를 큐에서 제거 합니다.
- 지연 컨테이너, blob, 테이블 및 큐를 나열 하 고 지연 엔터티 쿼리

[OneDrive API](https://dev.onedrive.com/README.htm)  
 OneDrive API의 응용 프로그램을 SharePoint Server 2016 및 Office 365에서 파일 및 폴더를 연결 하는 데 HTTP 서비스를 제공 합니다.

[C++ REST SDK(코드명 "Casablanca")](https://github.com/Microsoft/cpprestsdk)  
REST 서비스와 상호 작용 하기 위한 현대적이 고, 플랫폼 간 비동기 API를 제공 합니다.

-   JSON 문서를 구문 분석 및 serialization에 대 한 기본 제공 지원으로 모든 HTTP 서버에 대 한 REST 호출을 수행 합니다.
-   OAuth 1 및 2에는 로컬 리디렉션 수신기를 포함 하 여 지원
-   원격 서비스에 대 한 Websocket 연결
-   완벽 하 게 비동기 작업 PPL에 기본 제공 스레드 풀을 포함 하 여 기반 API

Windows 바탕 화면 (7 이상), Windows Server (2012 이상), 유니버설 Windows 플랫폼, Linux, OSX, Android 및 iOS를 지원합니다. 
  
[Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)  
 System.Web 네임스페이스에 있는 같은 이름의 .NET Framework 클래스에서 모델링된 Windows 런타임 HTTP 클라이언트 클래스입니다. `HttpClient` 는 HTTP를 통한 비동기 업로드 및 다운로드와 사용자 지정 HTTP 처리기를 파이프라인에 삽입할 수 있게 하는 파이프라인 필터를 완벽하게 지원합니다. Windows SDK에는 데이터 통신 연결 네트워크, OAuth 인증 등에 대한 샘플 필터가 포함됩니다. 유니버설 Windows 플랫폼을 대상으로 하는 응용 프로그램의 경우 사용 하는 권장는 `Windows::Web:HttpClient` 클래스입니다. 
  
[IXMLHTTPRequest2 인터페이스](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)  
 HTTP를 통해 인터넷에 연결 하는 Windows 런타임 앱 이나 Windows 데스크톱 앱에서 사용할 수 있습니다 및 GET, PUT 및 기타 HTTP 명령을 실행할 네이티브 COM 인터페이스를 제공 합니다. 자세한 내용은 참조 [연습:를 사용 하 여 작업 연결 및 XML HTTP 요청](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)합니다.  
  
[Windows 인터넷(WinInet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)  
 인터넷에 연결할 Windows 데스크톱 앱에서 사용할 수 있는 Windows API입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++](../visual-cpp-in-visual-studio.md)   
 [네트워크 및 웹 서비스](/windows/uwp/networking/)