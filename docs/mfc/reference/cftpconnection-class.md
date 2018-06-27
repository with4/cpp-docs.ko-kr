---
title: CFtpConnection 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 303e89cd00091d8427bdb1d6e36c9a85b7aa5100
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952955"
---
# <a name="cftpconnection-class"></a>CFtpConnection 클래스
인터넷 서버에 FTP 연결을 관리 하 고 해당 서버에 파일과 디렉터리의 직접 조작할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|`CFtpConnection` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|FTP 서버에 직접 명령을 보냅니다.|  
|[CFtpConnection::CreateDirectory](#createdirectory)|서버에서 디렉터리를 만듭니다.|  
|[:: Getcurrentdirectory](#getcurrentdirectory)|이 연결에 대 한 현재 디렉터리를 가져옵니다.|  
|[Cftpconnection:: Getcurrentdirectoryasurl](#getcurrentdirectoryasurl)|URL로이 연결에 대 한 현재 디렉터리를 가져옵니다.|  
|[CFtpConnection::GetFile](#getfile)|연결된 된 서버에서 파일을 가져옵니다.|  
|[CFtpConnection::OpenFile](#openfile)|연결된 된 서버에서 파일을 엽니다.|  
|[CFtpConnection::PutFile](#putfile)|서버에서 파일을 배치합니다.|  
|[CFtpConnection::Remove](#remove)|서버에서 파일을 제거 합니다.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|서버에서 지정된 된 디렉터리를 제거합니다.|  
|[CFtpConnection::Rename](#rename)|서버에서 파일을 이름을 바꿉니다.|  
|[Cftpconnection:: Setcurrentdirectory](#setcurrentdirectory)|현재 FTP 디렉터리를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 FTP는 MFC WinInet 클래스에서 인식 하는 세 가지 인터넷 서비스 중 하나입니다.  
  
 으로 FTP 인터넷 서버와 통신 하려면 먼저 만들어야 합니다 인스턴스의 [CInternetSession](../../mfc/reference/cinternetsession-class.md), 다음 만듭니다는 `CFtpConnection` 개체입니다. 만들지 마십시오는 `CFtpConnection` 개체를 직접 호출 하는 대신; [cinternetsession:: Getftpconnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), 만듦는 `CFtpConnection` 개체 하 고 포인터를 반환 합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CFtpConnection` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다. 서비스, HTTP 및 gopher는 클래스를 참조 하십시오. 지원 되 고 다른 두와 통신 하는 방법에 대 한 자세한 내용은 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)합니다.  
  
## <a name="example"></a>예  
  예제를 참조는 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 클래스 개요입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection  
 이 멤버 함수를 생성 하 라고 하는 `CFtpConnection` 개체입니다.  
  
```  
CFtpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CFtpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSession*  
 관련 된 항목에 대 한 포인터 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.  
  
 *hConnected*  
 현재 인터넷 세션의 Windows 핸들입니다.  
  
 *pstrServer*  
 FTP 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *dwContext*  
 작업에 대 한 컨텍스트 식별자입니다. *dwContext* 에서 반환한 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다. 기본값은 1로 설정 그러나 작업에 대 한 특정 컨텍스트 ID를 명시적으로 할당할 수 있습니다. 개체와 수행 하는 작업 컨텍스트 ID와 가진 연결 됩니다.  
  
 *pstrUserName*  
 사용자가 로그인의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 경우 **NULL**, 기본값은 익명입니다.  
  
 *pstrPassword*  
 로그인에 사용할 암호를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 두 *pstrPassword* 및 *pstrUserName* 는 **NULL**, 기본 익명 암호는 사용자의 전자 메일 이름입니다. 경우 *pstrPassword* 은 **NULL** (또는 빈 문자열) 하지만 *pstrUserName* 않습니다 **NULL**, 빈 암호가 사용 됩니다. 다음 표에서 설명의 가능한 네 가지 설정에 대 한 동작 *pstrUserName* 및 *pstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP 서버에 전송 하는 사용자 이름|FTP 서버에 전송 하는 암호|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** 또는 ""|**NULL** 또는 ""|"anonymous"|사용자의 전자 메일 이름|  
|비- **NULL** 문자열|**NULL** 또는 ""|*pstrUserName*|" "|  
|**NULL** 비- **NULL** 문자열|**오류**|**오류**||  
|비- **NULL** 문자열|비- **NULL** 문자열|*pstrUserName*|*pstrPassword*|  
  
 *nPort*  
 서버에서 사용 하는 TCP/IP 포트를 식별 하는 번호입니다.  
  
 *bPassive*  
 이 FTP 세션에 대 한 passive 또는 active 모드를 지정합니다. 경우로 설정 **TRUE**, Win32 API 설정 *dwFlag* 를 **INTERNET_FLAG_PASSIVE**합니다.  
  
### <a name="remarks"></a>설명  
 만들지 마십시오는 `CFtpConnection` 개체를 직접 합니다. 대신, 호출 [cinternetsession:: Getftpconnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), 만듦는 **CFptConnection** 개체입니다.  
  
##  <a name="command"></a>  CFtpConnection::Command  
 FTP 서버에 직접 명령을 보냅니다.  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 *pszCommand*  
 보낼 명령을 포함하는 문자열에 대한 포인터입니다.  
  
 *eResponse*  
 FTP 서버의 응답이 필요한지 여부를 결정합니다. 다음 값 중 하나입니다.  
  
- **CmdRespNone** 응답이 필요 합니다.  
  
- **CmdRespRead** 응답이 필요 합니다.  
  
 *dwFlags*  
 이 함수를 제어하는 플래그를 포함하는 값입니다. 전체 목록을 보려면를 참조 하십시오. [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133)합니다.  
  
 *dwContext*  
 콜백에서 응용 프로그램 컨텍스트를 식별하는 데 사용되는 응용 프로그램 정의 값을 포함하는 값에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) Windows SDK에 설명 된 대로 작동 합니다.  
  
 오류가 발생 하는 경우 MFC 형식의 예외를 throw 하는 [CInternetException](../../mfc/reference/cinternetexception-class.md)합니다.  
  
##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory  
 디렉터리를 만들려면 연결된 된 서버에서이 함수를 호출 합니다.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrDirName*  
 만들려는 디렉터리의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Windows 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `GetCurrentDirectory` 서버에이 연결에 대 한 현재 작업 디렉터리를 확인 하려면. 원격 시스템에 연결 된 있습니다 루트 디렉터리를 가정 하지 마십시오.  
  
 `pstrDirName` 매개 변수 수는 부분적으로 또는 현재 디렉터리에 상대적 정규화 된 파일 이름입니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `CreateDirectory` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="getcurrentdirectory"></a>  :: Getcurrentdirectory  
 현재 디렉터리의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *strDirName*  
 디렉터리의 이름의 받을 문자열에 대 한 참조입니다.  
  
 *pstrDirName*  
 디렉터리의 이름의 받을 문자열에 대 한 포인터입니다.  
  
 *lpdwLen*  
 다음 정보를 포함 하는 DWORD에 대 한 포인터.  
  
|||  
|-|-|  
|항목에|참조 하는 버퍼의 크기 *pstrDirName*합니다.|  
|반환 시|에 저장 된 문자 수 *pstrDirName*합니다. 멤버 함수가 실패 하 고 다음 ERROR_INSUFFICIENT_BUFFER 반환 됩니다 *lpdwLen* 문자열 받기 위해 응용 프로그램을 할당 해야 하는 바이트 수를 포함 합니다.|  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 디렉터리 이름을 가져오려면 URL로 대신 호출 [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)합니다.  
  
 매개 변수 *pstrDirName* 또는 *strDirName* 정규화 된 또는 현재 디렉터리에 상대적 부분적으로 정규화 된 파일 중 하나가 될 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `GetCurrentDirectory` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="getcurrentdirectoryasurl"></a>  Cftpconnection:: Getcurrentdirectoryasurl  
 URL로 현재 디렉터리의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *strDirName*  
 디렉터리의 이름의 받을 문자열에 대 한 참조입니다.  
  
 *pstrDirName*  
 디렉터리의 이름의 받을 문자열에 대 한 포인터입니다.  
  
 *lpdwLen*  
 다음 정보를 포함 하는 DWORD에 대 한 포인터.  
  
|||  
|-|-|  
|항목에|참조 하는 버퍼의 크기 *pstrDirName*합니다.|  
|반환 시|에 저장 된 문자 수 *pstrDirName*합니다. 멤버 함수가 실패 하 고 다음 ERROR_INSUFFICIENT_BUFFER 반환 됩니다 *lpdwLen* 문자열 받기 위해 응용 프로그램을 할당 해야 하는 바이트 수를 포함 합니다.|  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 `GetCurrentDirectoryAsURL` 동일 하 게 동작 [GetCurrentDirectory](#getcurrentdirectory)  
  
 매개 변수 *strDirName* 정규화 된 또는 현재 디렉터리에 상대적 부분적으로 정규화 된 파일 중 하나가 될 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `GetCurrentDirectoryAsURL` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="getfile"></a>  CFtpConnection::GetFile  
 FTP 서버에서 파일을 가져오고 로컬 컴퓨터에 저장 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetFile(
    LPCTSTR pstrRemoteFile,  
    LPCTSTR pstrLocalFile,  
    BOOL bFailIfExists = TRUE,  
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrRemoteFile*  
 FTP 서버에서 검색 하는 파일의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 *pstrLocalFile*  
 로컬 시스템에서 만들 파일의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 *bFailIfExists*  
 파일 이름은 기존 파일에서 이미 사용할 수 있는지 여부를 나타냅니다. 로컬 파일 이름이 이미 존재 하는 경우 및이 매개 변수는 **TRUE**, `GetFile` 실패 합니다. 그렇지 않으면 `GetFile` 파일의 기존 복사본 지워집니다.  
  
 *dwAttributes*  
 파일의 특성을 나타냅니다. 이 다음 FILE_ATTRIBUTE_ * 플래그의 조합 수 있습니다.  
  
-   FILE_ATTRIBUTE_ARCHIVE 파일 보관 파일입니다. 응용 프로그램에 백업 또는 제거 하는 파일을 표시 하려면이 특성을 사용 합니다.  
  
-   파일 또는 디렉터리 FILE_ATTRIBUTE_COMPRESSED 압축 됩니다. 파일을 압축 압축 파일에 데이터를 모두 의미 합니다. 디렉터리의 경우 새로 생성된 된 파일 및 하위 디렉터리에 대 한 default 압축이입니다.  
  
-   FILE_ATTRIBUTE_DIRECTORY 파일 디렉터리입니다.  
  
-   FILE_ATTRIBUTE_NORMAL 파일에 다른 특성 집합이 없습니다. 이 특성은 단독으로 사용 하는 경우에 유효 합니다. 다른 모든 파일 특성 FILE_ATTRIBUTE_NORMAL를 재정의합니다.  
  
-   FILE_ATTRIBUTE_HIDDEN 파일은 숨겨집니다. 것은 원래 디렉터리 목록에 포함 될 수 없습니다.  
  
-   FILE_ATTRIBUTE_READONLY 파일이 읽기 전용입니다. 응용 프로그램 파일을 읽을 수 있지만 쓸 하거나 삭제할 수 없습니다.  
  
-   FILE_ATTRIBUTE_SYSTEM 파일의 일부 또는 운영 체제에서 독점적으로 사용 됩니다.  
  
-   임시 저장소 용 FILE_ATTRIBUTE_TEMPORARY 파일을 사용 중입니다. 응용 프로그램은 반드시 필요한 경우에 파일에 작성 해야 합니다. 대부분의 데이터 파일의 파일은 삭제 곧 때문에 미디어에 플러시되고 있을 하지 않고 메모리에 남아 있습니다.  
  
 *dwFlags*  
 전송이 발생 하는 조건을 지정 합니다. 이 매개 변수 중 하나일 수 있습니다는 *dwFlags* 값에서 설명 [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) Windows sdk에서입니다.  
  
 *dwContext*  
 파일 검색에 대 한 컨텍스트 식별자입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 `GetFile` 모든 FTP 서버에서 파일을 읽고 로컬로 저장 연관 된 오버 헤드 처리 하는 높은 수준의 루틴이입니다. 파일 데이터를 검색 하는 파일 전송을 통해 통제를 해야 하는 등 응용 프로그램 사용 해야 `OpenFile` 및 [cinternetfile:: Read](../../mfc/reference/cinternetfile-class.md#read) 대신 합니다.  
  
 경우 *dwFlags* FILE_TRANSFER_TYPE_ASCII, 파일 데이터의 번역 변환 제어 되며 Windows에 해당 하는 문자 서식 지정 합니다. 기본 전송 모드가 이진, 서버에 저장 된 동일한 형식으로 파일이 다운로드 됩니다.  
  
 둘 다 *pstrRemoteFile* 및 *pstrLocalFile* 정규화 된 또는 현재 디렉터리에 상대적 부분적으로 정규화 된 파일 중 하나가 될 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `GetFile` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
 재정의 *dwContext* 기본적으로 선택한 값으로 컨텍스트 식별자를 설정 합니다. 특정 작업과 연관 된 컨텍스트 식별자는 `CFtpConnection` 하 여 만든 개체의 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업에 대 한 상태에 있습니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="openfile"></a>  CFtpConnection::OpenFile  
 읽기 또는 쓰기에 대 한 FTP 서버에 있는 파일을 열려면이 멤버 함수를 호출 합니다.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrFileName*  
 열 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *dwAccess*  
 파일 액세스 하는 방법을 결정 합니다. GENERIC_READ 또는 GENERIC_WRITE, 중 하나만 될 수 있습니다.  
  
 *dwFlags*  
 후속 전송 발생 하는 조건을 지정 합니다. 이 다음 FTP_TRANSFER_ * 상수 중 하나일 수 있습니다.  
  
-   FTP_TRANSFER_TYPE_ASCII 파일 FTP ASCII (유형: A) 전송 메서드를 사용 하 여 전송 합니다. 변환 컨트롤과 로컬 항목 서식 지정 정보입니다.  
  
-   FTP_TRANSFER_TYPE_BINARY 파일 (유형 1) FTP's 이미지 전송 메서드를 사용 하 여 데이터를 전송 합니다. 파일 전송 데이터과 동일 하 게 변경 하지 않고 있습니다. 이것이 기본 전송 방법입니다.  
  
 *dwContext*  
 파일을 열에 대 한 컨텍스트 식별자입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CInternetFile](../../mfc/reference/cinternetfile-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 `OpenFile` 다음과 같은 경우에 사용 되어야 합니다.  
  
-   응용 프로그램은 로컬 파일에 있는 않습니다 데이터를 전송 하 고 FTP 서버에 파일로 생성 해야 하는 데이터. 한 번 `OpenFile` 응용 프로그램 사용 하 여 파일을 열고 [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) 서버에 FTP 파일 데이터를 보내려고 합니다.  
  
-   응용 프로그램 서버에서 파일을 검색 하 고 디스크에 쓰는 것이 아니라 응용 프로그램 제어에서 사용 중인 메모리에 배치 해야 합니다. 응용 프로그램이 사용 [cinternetfile:: Read](../../mfc/reference/cinternetfile-class.md#read) 를 사용한 후 `OpenFile` 파일을 열 수 있습니다.  
  
-   응용 프로그램 파일을 전송에 대 한 제어에 대 한 상세 수준이 필요합니다. 예를 들어 응용 프로그램이 표시 하려는 경우가 진행률 컨트롤 파일을 다운로드 하는 동안 파일 전송 상태의 진행률을 표시 합니다.  
  
 호출한 후 `OpenFile` 및 호출 될 때까지 `CInternetConnection::Close`, 응용 프로그램에만 호출할 수 있습니다 [cinternetfile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`, 또는 [ Cftpfilefind:: Findfile](../../mfc/reference/cftpfilefind-class.md#findfile)합니다. 같은 FTP 세션에 대 한 다른 FTP 기능에 대 한 호출 실패 하 고 오류 코드 FTP_ETRANSFER_IN_PROGRESS로 설정 됩니다.  
  
 *pstrFileName* 매개 변수 중 하나는 부분적으로 정규화 된 파일 이름이 현재 디렉터리에 대 한 상대 또는 정규화 된 될 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `OpenFile` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
 재정의 *dwContext* 기본적으로 선택한 값으로 컨텍스트 식별자를 설정 합니다. 특정 작업과 연관 된 컨텍스트 식별자는 `CFtpConnection` 하 여 만든 개체의 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업에 대 한 상태에 있습니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="putfile"></a>  CFtpConnection::PutFile  
 FTP 서버에 파일을 저장 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrLocalFile*  
 로컬 시스템에서 보낼 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *pstrRemoteFile*  
 FTP 서버에서 만들 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *dwFlags*  
 파일 전송을 발생 하는 조건을 지정 합니다. 에 설명 된 FTP_TRANSFER_ 상수 중 하나가 될 수 있습니다 [OpenFile](#openfile)합니다.  
  
 *dwContext*  
 파일을 배치에 대 한 컨텍스트 식별자입니다. 참조 **주의** 에 대 한 자세한 내용은 *dwContext*합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 `PutFile` 모든 FTP 서버에 파일을 저장 하는 연관 된 작업을 처리 하는 높은 수준의 루틴이입니다. 응용 프로그램 데이터를 보낼만 하는 파일 전송에 대 한 자세히 제어를 해야 하는 등 사용 해야 [OpenFile](#openfile) 및 [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write)합니다.  
  
 `dwContext` 기본값을 재정의하여 컨텍스트 식별자를 설정한 값으로 설정합니다. 특정 작업과 연관 된 컨텍스트 식별자는 `CFtpConnection` 하 여 만든 개체의 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업에 대 한 상태에 있습니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="remove"></a>  CFtpConnection::Remove  
 연결 된 서버에서 지정된 된 파일을 삭제 하려면이 함수를 호출 합니다.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrFileName*  
 제거할 파일 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 *pstrFileName* 매개 변수 중 하나는 부분적으로 정규화 된 파일 이름이 현재 디렉터리에 대 한 상대 또는 정규화 된 될 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. **제거** 함수는 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory  
 연결된 된 서버에서 지정된 된 디렉터리를 제거 하려면이 함수를 호출 합니다.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrDirName*  
 제거할 디렉터리를 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [GetCurrentDirectory](#getcurrentdirectory) 서버의 현재 작업 디렉터리를 확인 하려면. 원격 시스템에 연결 된 있습니다 루트 디렉터리를 가정 하지 마십시오.  
  
 *pstrDirName* 매개 변수는 현재 디렉터리에 상대적 또는 부분적으로 정규화 된 filename을 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `RemoveDirectory` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="rename"></a>  CFtpConnection::Rename  
 이 연결된 된 서버에 지정된 된 파일 이름을 바꿀 함수를 호출 합니다.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrExisting*  
 이름을 바꿀 파일의 현재 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 *pstrNew*  
 파일의 새 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 *pstrExisting* 및 *pstrNew* 매개 변수 중 하나는 부분적으로 정규화 된 파일 이름이 현재 디렉터리에 대 한 상대 또는 정규화 된 일 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. **이름 바꾸기** 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
##  <a name="setcurrentdirectory"></a>  Cftpconnection:: Setcurrentdirectory  
 FTP 서버에서 다른 디렉터리를 변경 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrDirName*  
 디렉터리의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 *pstrDirName* 매개 변수는 현재 디렉터리에 상대적 또는 부분적으로 정규화 된 filename을 수 있습니다. 백슬래시 (\\) 또는 슬래시 (/) 이름 중 하나에 대 한 디렉터리 구분 기호로 사용할 수 있습니다. `SetCurrentDirectory` 사용 하기 전에 적절 한 문자를 디렉터리 이름 구분 기호를 변환 합니다.  
  
 사용 하 여 [GetCurrentDirectory](#getcurrentdirectory) FTP 서버의 현재 작업 디렉터리를 확인 하려면. 원격 시스템에 연결 된 있습니다 루트 디렉터리를 가정 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession 클래스](../../mfc/reference/cinternetsession-class.md)
