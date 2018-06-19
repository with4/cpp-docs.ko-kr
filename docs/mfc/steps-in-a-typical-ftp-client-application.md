---
title: 일반적인 FTP 클라이언트 응용 프로그램의 단계를 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98f5a21bd5fa20a40123ce442959125ea62c60d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381126"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>일반적인 FTP 클라이언트 응용 프로그램의 단계
일반적인 FTP 클라이언트 응용 프로그램을 만듭니다는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 및 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 개체입니다. MFC WinInet 클래스 이러한 실제로 프록시 유형 설정; 제어 하 고 하지 않으므로 참고 IIS는 다음 작업을 수행 하지 않습니다.  
  
 또한, 다음 기술 자료 문서를 참조 하십시오.  
  
-   방법: FTP WinInet API를 사용 하 여 CERN 기반 프록시 사용 (문서 ID: Q166961)  
  
-   샘플: FTP CERN 기반 암호로 보호 된 프록시 (문서 ID: Q216214)  
  
-   인터넷 서비스 관리자가 설치 된 프록시 서비스 표시 수 없다 (문서 ID: Q216802)  
  
 다음 표에서 일반적인 FTP 클라이언트 응용 프로그램에서 수행할 수는 단계를 보여 줍니다.  
  
|목표|수행할 작업|효과|  
|---------------|----------------------|-------------|  
|FTP 세션을 시작합니다.|만들기는 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|WinInet을 초기화하고 서버에 연결합니다.|  
|FTP 서버에 연결합니다.|사용 하 여 [cinternetsession:: Getftpconnection](../mfc/reference/cinternetsession-class.md#getftpconnection)합니다.|반환 된 [CFtpConnection](../mfc/reference/cftpconnection-class.md) 개체입니다.|  
|서버의 새로운 FTP 디렉터리로 변경합니다.|사용 하 여 [cftpconnection:: Setcurrentdirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)합니다.|서버에서 현재 연결된 디렉터리를 변경합니다.|  
|FTP 디렉터리에서 첫 번째 파일을 찾습니다.|사용 하 여 [cftpfilefind:: Findfile](../mfc/reference/cftpfilefind-class.md#findfile)합니다.|첫 번째 파일을 찾습니다. 파일이 발견되지 않으면 FALSE를 반환합니다.|  
|FTP 디렉터리에서 다음 파일을 찾습니다.|사용 하 여 [cftpfilefind:: Findnextfile](../mfc/reference/cftpfilefind-class.md#findnextfile)합니다.|다음 파일을 찾습니다. 파일을 찾을 수 없으면 FALSE를 반환합니다.|  
|로 찾은 파일을 열고 **FindFile** 또는 `FindNextFile` 읽기 또는 쓰기에 대 한 합니다.|사용 하 여 [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile), 파일 이름을 사용 하 여 반환한 [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) 또는 [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)합니다.|읽기 또는 쓰기에 대 한 서버에서 파일을 엽니다. 반환 된 [CInternetFile](../mfc/reference/cinternetfile-class.md) 개체입니다.|  
|읽거나 파일에 씁니다.|사용 하 여 [cinternetfile:: Read](../mfc/reference/cinternetfile-class.md#read) 또는 [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write)합니다.|읽거나 바이트, 사용자가 제공 하는 버퍼를 사용 하 여 지정 된 수를 씁니다.|  
|예외 처리|사용 하 여 [CInternetException](../mfc/reference/cinternetexception-class.md) 클래스입니다.|모든 공용 인터넷 예외 형식을 처리합니다.|  
|FTP 세션을 종료합니다.|삭제 된 [CInternetSession](../mfc/reference/cinternetsession-class.md) 개체입니다.|열린 파일 핸들 및 연결을 자동으로 정리합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Win32 인터넷 확장명 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [인터넷 클라이언트 클래스에 대 한 필수 구성 요소](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet 클래스를 사용하여 인터넷 클라이언트 응용 프로그램 작성](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
