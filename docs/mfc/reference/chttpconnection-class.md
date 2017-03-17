---
title: "CHttpConnection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- protocols, HTTP
- connecting to servers, HTTP servers
- Internet protocols, HTTP
- HTTP connections
- Internet protocols
- CHttpConnection class
- HTTP servers, connecting to
- connecting to servers
- Internet connections, HTTP
- connections [C++], HTTP
- Internet server, HTTP
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
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
ms.openlocfilehash: 1b02a79cebbd73a05478887115646f0544f0a92d
ms.lasthandoff: 02/24/2017

---
# <a name="chttpconnection-class"></a>CHttpConnection 클래스
HTTP 서버와의 연결을 관리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|
          `CHttpConnection` 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](#openrequest)|HTTP 요청을 엽니다.|  
  
## <a name="remarks"></a>주의  
 HTTP은 MFC WinInet 클래스에서 구현 하는 세 가지 인터넷 서버 프로토콜 중 하나입니다.  
  
 클래스 `CHttpConnection` 생성자 및 하나의 멤버 함수에 포함 된 [OpenRequest](#openrequest), HTTP 프로토콜을 사용 하 여 서버에 대 한 연결을 관리 하 합니다.  
  
 HTTP 서버와 통신할 먼저 만들어야 인스턴스의 [CInternetSession](../../mfc/reference/cinternetsession-class.md), 만들면는 [CHttpConnection](#_mfc_chttpconnection) 개체입니다. 만들 없도록는 `CHttpConnection` 개체를 직접 호출 하는 대신, [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)를 작성 하는 `CHttpConnection` 개체 하 고 포인터를 반환 합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CHttpConnection` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다. 다른 두 가지를 사용 하 여 서버에 연결 하는 방법에 대 한 자세한 내용은 인터넷 프로토콜, gopher 및 FTP 지원에 대 한 참조는 클래스 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 및 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 이 멤버 함수를 생성 하 라고는 `CHttpConnection` 개체입니다.  
  
```  
CHttpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSession`  
 에 대 한 포인터는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다.  
  
 `hConnected`  
 인터넷 연결에 대 한 핸들입니다.  
  
 `pstrServer`  
 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwContext`  
 에 대 한 컨텍스트 식별자는 `CInternetConnection` 개체입니다. 참조 **주의** 에 대 한 자세한 내용은 `dwContext`합니다.  
  
 `nPort`  
 인터넷이이 연결의 포트를 식별 하는 번호입니다.  
  
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
  
 `dwFlags`  
 조합 된 **INTERNET_ FLAG_\* ** 플래그입니다. 표를 참조는 **주의** 섹션 [CHttpConnection::OpenRequest](#openrequest) 에 대 한 설명은 `dwFlags` 값입니다.  
  
### <a name="remarks"></a>주의  
 사용자를 만들지는 `CHttpConnection` 직접. 호출 하 여 개체를 만드는 대신, [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)합니다.  
  
##  <a name="openrequest"></a>CHttpConnection::OpenRequest  
 HTTP 연결을 열려면 이 멤버 함수를 호출합니다.  
  
```  
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

 
CHttpFile* OpenRequest(
    int nVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrVerb`  
 요청에 사용할 동사를 포함하는 문자열에 대한 포인터입니다. `NULL`의 경우 "GET"을 사용합니다.  
  
 `pstrObjectName`  
 지정된 동사의 대상 개체를 포함하는 문자열에 대한 포인터입니다. 일반적으로 파일 이름, 실행 모듈 또는 검색 지정자입니다.  
  
 `pstrReferer`  
 문서의의 주소 (URL)을 지정 하는 문자열에 대 한 포인터 요청의 URL ( `pstrObjectName`)을 받았습니다. `NULL`인 경우 HTTP 헤더가 지정되지 않습니다.  
  
 `dwContext`  
 `OpenRequest` 작업에 대한 컨텍스트 식별자입니다. 자세한 내용은 `dwContext` 설명 부분을 참조하십시오.  
  
 `ppstrAcceptTypes`  
 클라이언트에 허용되는 콘텐츠 형식을 나타내는 문자열에 대한 `LPCTSTR` 포인터의 Null로 끝나는 배열에 대한 포인터입니다. `ppstrAcceptTypes`가 `NULL`인 경우 서버는 클라이언트가 "text/*" 형식의 문서만 허용하여 텍스트 문서만 허용되고 그림이나 기타 이진 파일은 허용되지 않는 것으로 해석합니다. 콘텐츠 형식 첨부 HTTP POST 및 PUT 등 첨부된 정보가 있는 쿼리에 대한 데이터의 형식을 식별하는 CGI 변수 CONTENT_TYPE과 같습니다.  
  
 `pstrVersion`  
 HTTP 버전을 정의하는 문자열에 대한 포인터입니다. `NULL`의 경우 "HTTP/1.0"을 사용합니다.  
  
 `dwFlags`  
 INTERNET_ * FLAG_ 플래그의 조합입니다. 가능한 `dwFlags` 값 목록은 설명 부분을 참조하십시오.  
  
 `nVerb`  
 HTTP 요청 형식과 관련된 숫자입니다. 다음 중 하나일 수 있습니다.  
  
|HTTP 요청 형식|`nVerb` 값|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CHttpFile](../../mfc/reference/chttpfile-class.md) 요청 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 `dwFlags`은 다음 중 하나일 수 있습니다.  
  
|인터넷 플래그|설명|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|캐시가 아니라 원본 서버에서 요청한 파일, 개체 또는 디렉터리 목록을 다운로드합니다.|  
|`INTERNET_FLAG_DONT_CACHE`|반환된 엔터티를 캐시에 추가하지 않습니다.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|반환된 엔터티를 영구 엔터티로 캐시에 추가합니다. 이는 표준 캐시 정리, 일관성 검사 또는 가비지 컬렉션으로 캐시에서 이 항목을 제거할 수 없다는 의미입니다.|  
|`INTERNET_FLAG_SECURE`|보안 트랜잭션 의미 체계를 사용합니다. SSL/PCT 사용으로 변환되며 HTTP 요청에서 의미를 갖습니다.|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|HTTP 에서만 사용, 리디렉션 해야 처리 되지 않도록 자동으로의 지정 [chttpfile:: Sendrequest](../../mfc/reference/chttpfile-class.md#sendrequest)합니다.|  
  
 `dwContext` 기본값을 재정의하여 컨텍스트 식별자를 설정한 값으로 설정합니다. 특정 작업과 연관 된 컨텍스트 식별자는 `CHttpConnection` 개체에서 만든 해당 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 개체입니다. 값이 반환 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 작업에 대 한 상태에 있습니다. 문서를 참조 하십시오 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
 이 함수를 사용할 경우 예외가 throw될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)

