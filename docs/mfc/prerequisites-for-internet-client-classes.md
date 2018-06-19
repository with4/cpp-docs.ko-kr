---
title: 인터넷 클라이언트 클래스에 대 한 필수 조건 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6c16c3658ee5d27def4892997c50115dc0b8831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354039"
---
# <a name="prerequisites-for-internet-client-classes"></a>인터넷 클라이언트 클래스의 필수 구성 요소
(예를 들어 파일을 읽는) 인터넷 클라이언트에서 수행한 일부 작업에 (이 경우 인터넷 연결을 설정) 동작을 수행 해야 합니다. 다음 표에서 일부 클라이언트 작업에 대 한 필수 구성 요소를 보여 줍니다.  
  
### <a name="general-internet-url-ftp-gopher-or-http"></a>일반 인터넷 URL (FTP, Gopher, 또는 HTTP)  
  
|작업|필수 조건|  
|------------|------------------|  
|연결을 설정 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 인터넷 클라이언트 응용 프로그램의 기반을 설정 합니다.|  
|URL을 엽니다.|연결을 설정 합니다. 호출 [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl)합니다. `OpenURL` 함수는 읽기 전용 리소스 개체를 반환 합니다.|  
|데이터 읽기 URL입니다.|URL이 열립니다. 호출 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read)합니다.|  
|인터넷 옵션을 설정 합니다.|연결을 설정 합니다. 호출 [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)합니다.|  
|상태 정보와 함께 호출 하는 함수를 설정 합니다.|연결을 설정 합니다. 호출 [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)합니다. 재정의 [cinternetsession:: Onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 호출을 처리 하도록 합니다.|  
  
### <a name="ftp"></a>FTP  
  
|작업|필수 조건|  
|------------|------------------|  
|FTP 연결을 설정 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 이 인터넷 클라이언트 응용 프로그램의 기반으로 합니다. 호출 [cinternetsession:: Getftpconnection](../mfc/reference/cinternetsession-class.md#getftpconnection) 만들려는 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 개체입니다.|  
|첫 번째 리소스를 찾습니다.|FTP 연결을 설정 합니다. 만들기는 [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) 개체입니다. 호출 [cftpfilefind:: Findfile](../mfc/reference/cftpfilefind-class.md#findfile)합니다.|  
|사용 가능한 모든 리소스를 열거 합니다.|첫 번째 파일을 찾습니다. 호출 [cftpfilefind:: Findnextfile](../mfc/reference/cftpfilefind-class.md#findnextfile) FALSE가 반환 될 때까지 합니다.|  
|FTP 파일을 엽니다.|FTP 연결을 설정 합니다. 호출 [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile) 을 만들어 여는 [CInternetFile](../mfc/reference/cinternetfile-class.md) 개체입니다.|  
|FTP 파일을 읽습니다.|읽기 액세스 권한이 있는 FTP 파일을 엽니다. 호출 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read)합니다.|  
|FTP 파일에 씁니다.|쓰기 권한으로 FTP 파일을 엽니다. 호출 [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write)합니다.|  
|서버에 클라이언트의 디렉터리를 변경 합니다.|FTP 연결을 설정 합니다. 호출 [cftpconnection:: Setcurrentdirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)합니다.|  
|서버에서 클라이언트의 현재 디렉터리를 검색 합니다.|FTP 연결을 설정 합니다. 호출 [:: Getcurrentdirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory)합니다.|  
  
### <a name="http"></a>HTTP  
  
|작업|필수 조건|  
|------------|------------------|  
|HTTP 연결을 설정 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 이 인터넷 클라이언트 응용 프로그램의 기반으로 합니다. 호출 [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) 만들려는 [CHttpConnection](../mfc/reference/chttpconnection-class.md) 개체입니다.|  
|HTTP 파일을 엽니다.|HTTP 연결을 설정 합니다. 호출 [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) 만들려는 [CHttpFile](../mfc/reference/chttpfile-class.md) 개체입니다. 호출 [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)합니다. 호출 [chttpfile:: Sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)합니다.|  
|HTTP 파일을 읽습니다.|HTTP 파일을 엽니다. 호출 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read)합니다.|  
|HTTP 요청에 대 한 정보를 가져옵니다.|HTTP 연결을 설정 합니다. 호출 [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) 만들려는 [CHttpFile](../mfc/reference/chttpfile-class.md) 개체입니다. 호출 [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo)합니다.|  
  
### <a name="gopher"></a>gopher  
  
|작업|필수 조건|  
|------------|------------------|  
|Gopher 연결을 설정 합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 이 인터넷 클라이언트 응용 프로그램의 기반으로 합니다. 호출 [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) 만들려는 [CGopherConnection](../mfc/reference/cgopherconnection-class.md)합니다.|  
|현재 디렉터리에서 첫 번째 파일을 찾습니다.|Gopher 연결을 설정 합니다. 만들기는 [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) 개체입니다. 호출 [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) 만들려는 [CGopherLocator](../mfc/reference/cgopherlocator-class.md) 개체입니다. 로케이터 전달 [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)합니다. 호출 [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) 나중에 필요할 경우 파일의 로케이터를 얻으려고 합니다.|  
|사용 가능한 모든 파일을 열거 합니다.|첫 번째 파일을 찾습니다. 호출 [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) FALSE가 반환 될 때까지 합니다.|  
|Gopher 파일을 엽니다.|Gopher 연결을 설정 합니다. 와 gopher 로케이터 만들기 [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) 와 로케이터 찾기 또는 [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator)합니다. 호출 [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)합니다.|  
|Gopher 파일을 읽습니다.|Gopher 파일을 엽니다. 사용 하 여 [CGopherFile](../mfc/reference/cgopherfile-class.md)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 응용 프로그램을 만들기 위한 MFC 클래스](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
