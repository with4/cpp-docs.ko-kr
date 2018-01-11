---
title: "WinInet 기본 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3c9502c720b0f443ace3cfe637fb4826281ecf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="wininet-basics"></a>WinInet 기본 사항
다운로드 하 여 응용 프로그램 내에서 파일을 업로드 FTP 지원을 추가 하려면 WinInet을 사용할 수 있습니다. 재정의할 수 있습니다 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 사용 하는 `dwContext` 매개 변수를 검색 하 고 파일을 다운로드할 때 사용자에 게 진행률 정보를 제공 합니다.  
  
 이 문서에는 다음 항목이 포함 됩니다.  
  
-   [간단한 브라우저 만들기](#_core_create_a_very_simple_browser)  
  
-   [웹 페이지 다운로드](#_core_download_a_web_page)  
  
-   [FTP 파일](#_core_ftp_a_file)  
  
-   [Gopher 디렉터리를 검색 합니다.](#_core_retrieve_a_gopher_directory)  
  
-   [파일을 전송 하는 동안 진행률 정보를 표시 합니다.](#_core_display_progress_information_while_transferring_files)  
  
 아래의 코드 부분에는 간단한 브라우저를 만들고 파일을 FTP, 웹 페이지 다운로드 gopher 파일을 검색 하는 방법을 보여 줍니다. 예제를 전체적으로 사용 되지 않는 한 하지 예외 처리가 포함 합니다.  
  
 WinInet에서 추가 정보를 참조 하십시오. [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)합니다.  
  
##  <a name="_core_create_a_very_simple_browser"></a>간단한 브라우저 만들기  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a>웹 페이지 다운로드  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a>FTP 파일  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a>Gopher 디렉터리를 검색 합니다.  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>OnStatusCallback 사용  
 WinInet 클래스를 사용 하는 경우 사용할 수 있습니다는 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 응용 프로그램의 구성원 [CInternetSession](../mfc/reference/cinternetsession-class.md) 상태 정보를 검색 하는 개체입니다. 직접 파생 하는 경우 `CInternetSession` 개체, 재정의 `OnStatusCallback`, 상태 콜백이 활성화 및 MFC를 호출 합니다 프로그램 `OnStatusCallback` 해당 인터넷 세션에서 모든 활동에 대 한 진행률 정보는 함수입니다.  
  
 단일 세션 (여기서에 여러 다른 고유한 작업을 수행할 수 있습니다)는 여러 연결을 지원 않기 때문에 `OnStatusCallback` 특정 연결이 나 트랜잭션이와 각 상태 변경 내용을 식별 하는 메커니즘이 필요 합니다. 해당 메커니즘은 대부분 WinInet 지원 클래스의 멤버 함수에 지정 된 컨텍스트 ID 매개 변수에서 제공 됩니다. 이 매개 변수는 항상 형식 `DWORD` 이름은 항상 및 `dwContext`합니다.  
  
 특정 인터넷 개체에 할당 된 컨텍스트 개체에서 발생 한 활동을 식별 하는 데에 사용 되는 `OnStatusCallback` 의 멤버는 `CInternetSession` 개체입니다. 에 대 한 호출 `OnStatusCallback` 여러 매개 변수를 수신 합니다. 이러한 매개 변수는 어떤 진행 있는 트랜잭션 및 연결에 대 한 응용 프로그램에 지시 하기 위해 함께 작동 합니다.  
  
 만들 때 한 `CInternetSession` 개체를 지정할 수 있습니다는 `dwContext` 생성자에 매개 변수입니다. `CInternetSession`컨텍스트 ID;을 사용 하지 않는 자체 그 대신, 모든에 컨텍스트 ID를 전달 **InternetConnection**-자체의 컨텍스트 ID를 가져오지 않음 명시적으로 개체를 파생 합니다. 게 것 `CInternetConnection` 개체에 따라 컨텍스트 ID를 전달 하 `CInternetFile` id가 다른 컨텍스트 ID를 명시적으로 지정 하지 않으면를 만들 개체 반면에 자신만의 특정 컨텍스트 ID, 개체 및 모든 작업을 지정 수행 하는 경우 않습니다 됩니다 컨텍스트 ID와 연결 컨텍스트 Id를 사용 하 여 어떤 상태 정보는에서 제공 되 고 식별 하 여 `OnStatusCallback` 함수입니다.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a>파일을 전송 하는 동안 진행률 정보를 표시 합니다.  
 예를 들어 파일을 읽는 FTP 서버를 사용 하 여 연결을 만들고 웹 페이지를 가져오기 위해 HTTP 서버에도 연결 하는 응용 프로그램을 작성 하는 경우 해야 합니다.는 `CInternetSession` 개체, 두 `CInternetConnection` 개체 (하나는 **CFtpSession** 하 고는 다른는 **CHttpSession**)와 두 개의 `CInternetFile` (각 연결 마다 하나씩) 개체입니다. 에 대 한 기본값을 사용 하는 경우는 `dwContext` 매개 변수를 됩니다 구분할 수는 `OnStatusCallback` FTP 연결과 HTTP 연결에 대 한 진행률을 표시 하는 호출에 대 한 진행률을 표시 하는 호출 합니다. 지정 하는 경우는 `dwContext` 나중에 대 한 테스트 수 있는 ID `OnStatusCallback`, 작업 생성 콜백을 알 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)   
 [Win32 인터넷 확장(WinInet)](../mfc/win32-internet-extensions-wininet.md)

