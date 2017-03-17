---
title: "CGopherConnection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- Internet server, gopher
- connecting to servers, gopher servers
- protocols, gopher
- services, gopher
- CGopherConnection class
- gopher protocol
- gopher server
- connecting to servers
- Internet connections, gopher
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6267dd226e87e5bf64faa7225e49d9a99af93e3e
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherconnection-class"></a>CGopherConnection 클래스
Gopher 인터넷 서버 연결을 관리합니다.  
  
> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 해당 멤버 사용이 중단 된 Windows XP 플랫폼에서 작동 하지 않습니다 하지만 계속 이전 플랫폼에서 작동 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|`CGopherConnection` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|만듭니다는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) gopher 서버에서 파일을 찾을 개체입니다.|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher 개체에 대 한 특성 정보를 검색합니다.|  
|[CGopherConnection::OpenFile](#openfile)|Gopher 파일을 엽니다.|  
  
## <a name="remarks"></a>주의  
 Gopher 서비스 MFC WinInet 클래스에서 인식 하는 세 가지 인터넷 서비스 중 하나입니다.  
  
 클래스 `CGopherConnection` 생성자 및 gopher 서비스를 관리 하는 세 개의 추가 멤버 함수만 포함: [OpenFile](#openfile), [CreateLocator](#createlocator), 및 [GetAttribute](#getattribute)합니다.  
  
 Gopher 인터넷 서버와 통신할 먼저 만들어야 인스턴스의 [CInternetSession](../../mfc/reference/cinternetsession-class.md), 다음 호출 [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), 만드는 `CGopherConnection` 개체 하 고 포인터를 반환 합니다. 만들 없도록는 `CGopherConnection` 개체에 직접.  
  
 방법에 대 한 자세한 내용을 보려면 `CGopherConnection` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다. 지원 되는 인터넷 서비스를 다른 두 개를 사용 하는 방법에 대 한 자세한 내용은, FTP 및 HTTP 참조 클래스 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 및 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cgopherconnection"></a>CGopherConnection::CGopherConnection  
 이 멤버 함수를 생성 하 라고는 `CGopherConnection` 개체입니다.  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSession`  
 관련 된 항목에 대 한 포인터 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.  
  
 `hConnected`  
 현재 인터넷 세션의 Windows 핸들입니다.  
  
 `pstrServer`  
 FTP 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwContext`  
 작업에 대 한 컨텍스트 식별자입니다. `dwContext`반환 된 작업의 상태 정보를 식별 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)합니다. 기본값은 1;로 설정 그러나 작업에 대 한 특정 컨텍스트 ID를 명시적으로 지정할 수 있습니다. 개체와는 모든 작업 해당 컨텍스트 ID와 가진 연결 됩니다.  
  
 `pstrUserName`  
 사용자가 로그인의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 경우 **NULL**, 기본값은 익명입니다.  
  
 `pstrPassword`  
 로그인에 사용할 암호를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 모두 `pstrPassword` 및 `pstrUserName` 는 **NULL**, 기본 익명 암호는 사용자의 전자 메일 이름입니다. 경우 `pstrPassword` 는 **NULL** (또는 빈 문자열) 하지만 `pstrUserName` 없는 **NULL**, 빈 암호가 사용 됩니다. 다음 표에서 설명의 네 가지 가능한 설정에 대 한 동작 `pstrUserName` 및 `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP 서버에 전송 하는 사용자 이름|FTP 서버에 전송 되는 암호|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** 또는 ""|**NULL** 또는 ""|"익명"|사용자의 전자 메일 이름|  
|비- **NULL** 문자열|**NULL** 또는 ""|`pstrUserName`|" "|  
|**NULL** 비 **NULL** 문자열|**오류**|**오류**||  
|비- **NULL** 문자열|비- **NULL** 문자열|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 서버에서 사용 하 여 TCP/IP 포트를 식별 하는 번호입니다.  
  
### <a name="remarks"></a>주의  
 만들 없도록는 `CGopherConnection` 직접. 대신, 호출 [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)를 작성 하는 `CGopherConnection` 개체 하 고 포인터를 반환 합니다.  
  
##  <a name="createlocator"></a>CGopherConnection::CreateLocator  
 이를 찾거나 gopher 서버에서 파일을 식별할 gopher 로케이터를 만드는 함수를 호출 합니다.  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrDisplayString`  
 Gopher 문서 또는 검색할 디렉터리의 이름을 포함 하는 문자열에 대 한 포인터입니다. 하는 경우는 `pstrDisplayString` 매개 변수는 **NULL**, gopher 서버에 대 한 기본 디렉터리 반환 됩니다.  
  
 `pstrSelectorString`  
 항목을 검색 하기 위해 gopher 서버에 전송 해야 하는 선택기 문자열에 대 한 포인터입니다. `pstrSelectorString`수 **NULL**합니다.  
  
 *dwGopherType*  
 이 지정 하는지 여부를 `pstrSelectorString` 디렉터리 또는 문서를 참조 및 gopher 또는 gopher + 요청 인지 합니다. 구조에 대 한 특성을 참조 하십시오 [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `pstrLocator`  
 열려는 파일을 식별 하는 문자열에 대 한 포인터입니다. 이 문자열에 대 한 호출에서 반환 되는 일반적으로 [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator)합니다.  
  
 *pstrServerName*  
 Gopher 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `nPort`  
 인터넷이이 연결의 포트를 식별 하는 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 정적 버전의 멤버 함수는 정적이 아닌 버전에는 연결 개체에서 서버 이름을 사용 하는 동안 서버를 지정 해야 합니다.  
  
 Gopher 서버에서 정보를 검색 하기 위해 응용 프로그램 gopher 로케이터를 먼저 가져온 해야 합니다. 불투명 토큰으로 응용 프로그램 로케이터를 후 처리 해야 합니다 (즉, 응용 프로그램 수 로케이터를 사용 하지만 직접 조작 하거나 비교). 응용 프로그램에 대 한 호출에 대 한 로케이터를 사용 하는 일반적으로 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) 정보의 특정 부분을 검색 하려면 멤버 함수입니다.  
  
##  <a name="getattribute"></a>CGopherConnection::GetAttribute  
 Gopher 서버에서 항목에 대 한 특정 특성 정보를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>매개 변수  
 `refLocator`  
 에 대 한 참조는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
 *strRequestedAttributes*  
 요청된 된 특성의 이름을 지정 하는 공백으로 구분 된 문자열입니다.  
  
 `strResult`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 로케이터 유형을 수신입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
##  <a name="openfile"></a>CGopherConnection::OpenFile  
 Gopher 서버에서 파일을 열려면이 멤버 함수를 호출 합니다.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `refLocator`  
 에 대 한 참조는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
 `dwFlags`  
 INTERNET_FLAG_ 플래그의 조합입니다. 참조 [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) INTERNET_FLAG_ 대 한 자세한 내용은\* 플래그입니다.  
  
 `pstrView`  
 파일 보기 문자열에 대 한 포인터입니다. 파일의 여러 뷰는 서버에 존재 하는 경우이 매개 변수를 열려면 파일 보기를 지정 합니다. 경우 `pstrView` 는 **NULL**를 기본 파일 보기를 사용 합니다.  
  
 `dwContext`  
 열려는 파일에 대 한 컨텍스트 ID입니다. 참조 **주의** 에 대 한 자세한 내용은 `dwContext`합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CGopherFile](../../mfc/reference/cgopherfile-class.md) 개체를 열 수입니다.  
  
### <a name="remarks"></a>주의  
 `dwContext` 기본값을 재정의하여 컨텍스트 식별자를 설정한 값으로 설정합니다. 특정 작업과 연관 된 컨텍스트 식별자는 `CGopherConnection` 개체에서 만든 해당 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업에 대 한 상태에 있습니다. 문서를 참조 하십시오 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpConnection 클래스](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator 클래스](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession 클래스](../../mfc/reference/cinternetsession-class.md)

