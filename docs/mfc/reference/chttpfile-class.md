---
title: "CHttpFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
dev_langs:
- C++
helpviewer_keywords:
- HTTP files
- HTTP requests, requesting and reading files
- CHttpFile class
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: b99e87f1cbf8a181cbe1208f3b4008625f82af63
ms.lasthandoff: 04/04/2017

---
# <a name="chttpfile-class"></a>CHttpFile 클래스
HTTP 서버에서 파일을 요청하고 읽는 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|
          `CHttpFile` 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|HTTP 서버에 전송 된 요청에 헤더를 추가 합니다.|  
|[CHttpFile::EndRequest](#endrequest)|사용 하 여 HTTP 서버에 전송 요청을 종료는 [SendRequestEx](#sendrequestex) 멤버 함수입니다.|  
|[CHttpFile::GetFileURL](#getfileurl)|지정된 된 파일에 대 한 URL을 가져옵니다.|  
|[CHttpFile::GetObject](#getobject)|요청에서 HTTP 서버로 동사의 대상 개체를 가져옵니다.|  
|[CHttpFile::GetVerb](#getverb)|HTTP 서버에 대 한 요청에서 사용 된 동사를 가져옵니다.|  
|[CHttpFile::QueryInfo](#queryinfo)|HTTP 서버에서 요청 또는 응답 헤더를 반환합니다.|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|HTTP 요청에 연결 된 상태 코드를 검색 하 고 제공 된 배치 `dwStatusCode` 매개 변수입니다.|  
|[Chttpfile:: Sendrequest](#sendrequest)|HTTP 서버에 요청을 보냅니다.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|사용 하 여 HTTP 서버에 요청을 보냅니다는 [쓰기](../../mfc/reference/cinternetfile-class.md#write) 또는 [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) 방식의 `CInternetFile`합니다.|  
  
## <a name="remarks"></a>설명  
 HTTP 서버에서 데이터를 읽은 인터넷 세션을 만들어야 합니다 인스턴스의 `CHttpFile`합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CHttpFile` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders  
 하나를 추가 하려면이 함수를 호출 하거나 HTTP 요청에 더 많은 HTTP 요청 헤더를 처리 합니다.  
  
```  
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,  
    int dwHeadersLen = -1);

 
BOOL AddRequestHeaders(
    CString& str,  
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrHeaders`  
 머리글 또는 요청에 추가할 헤더를 포함 하는 문자열에 대 한 포인터입니다. 각 헤더는 CR/LF 쌍으로 종료 해야 합니다.  
  
 `dwFlags`  
 새 헤더의 의미 체계를 수정합니다. 다음 중 하나일 수 있습니다.  
  
- `HTTP_ADDREQ_FLAG_COALESCE`후속 헤더를 발견 한 첫 번째 헤더를 추가 하는 플래그를 사용 하 여 이름이 같은 헤더를 병합 합니다. 예를 들어 "Accept: 텍스트 / *" 다음 "Accept: 오디오 /\*" 단일 헤더의 형성에 "수락: 텍스트 /\*, 오디오 /\*" 합니다. 호출 응용 프로그램을 결합 하거나 별도 헤더와 함께 전송 된 요청에서 받은 데이터에 대해 화합 구성표를 확인 합니다.  
  
- `HTTP_ADDREQ_FLAG_REPLACE`제거를 수행 하 고 대체 현재 헤더에 추가 합니다. 현재 헤더를 제거 하는 헤더 이름이 사용 됩니다 하 고 새 헤더를 추가 하는 전체 값이 사용 됩니다. 헤더 값이 비어 헤더 발견 되는 경우 제거 됩니다. 그렇지 않으면 비어 있는 경우 헤더 값 대체 됩니다.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`아직 없는 경우에 헤더를 추가 합니다. 있는 경우 오류가 반환 됩니다.  
  
- `HTTP_ADDREQ_FLAG_ADD`With REPLACE를 사용 합니다. 존재 하지 않는 경우에 헤더를 추가 합니다.  
  
 `dwHeadersLen`  
 길이 문자의 `pstrHeaders`합니다. -1l를 다음 이것이 `pstrHeaders` 0으로 끝나는 것으로 간주 됩니다 길이 계산 됩니다.  
  
 `str`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 요청 헤더 또는 추가할 헤더를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 `AddRequestHeaders`HTTP 요청 핸들을 추가, 자유 형식 헤더를 추가합니다. 것은 사용 하기 위해 HTTP 서버에 전송 된 정확한 요청을 세부적된으로 제어 해야 하는 정교한 클라이언트에서.  
  
> [!NOTE]
>  응용 프로그램에서 여러 헤더를 전달할 수 `pstrHeaders` 또는 `str` 에 대 한 프로그램 `AddRequestHeaders` 사용 하 여 호출 `HTTP_ADDREQ_FLAG_ADD` 또는 `HTTP_ADDREQ_FLAG_ADD_IF_NEW`합니다. 응용 프로그램을 제거 하거나 사용 하 여 헤더 바꾸기 시도 **HTTP_ADDREQ_FLAG_REMOVE** 또는 `HTTP_ADDREQ_FLAG_REPLACE`, 하나의 헤더를 제공할 수 있습니다 `lpszHeaders`합니다.  
  
##  <a name="chttpfile"></a>CHttpFile::CHttpFile  
 이 멤버 함수를 생성 하 라고 하는 `CHttpFile` 개체입니다.  
  
```  
CHttpFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrObject,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrVerb,  
    DWORD_PTR dwContext);

 
CHttpFile(
    HINTERNET hFile,  
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObject,  
    CHttpConnection* pConnection);
```  
  
### <a name="parameters"></a>매개 변수  
 `hFile`  
 인터넷 파일에 대 한 핸들입니다.  
  
 `hSession`  
 인터넷 세션에 대 한 핸들입니다.  
  
 *pstrObject*  
 포함 하는 문자열에 대 한 포인터는 `CHttpFile` 개체입니다.  
  
 `pstrServer`  
 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `pstrVerb`  
 요청을 보낼 때 사용 되는 메서드를 포함 하는 문자열에 대 한 포인터입니다. Can be **POST**, **HEAD**, or `GET`.  
  
 dwContext  
 에 대 한 컨텍스트 식별자는 `CHttpFile` 개체입니다. 참조 **주의** 이 매개 변수에 대 한 자세한 내용은 합니다.  
  
 `pConnection`  
 에 대 한 포인터는 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 생성 되지 않습니다는 `CHttpFile` 개체를 직접 호출 하는 대신; [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) 대신 합니다.  
  
 에 대 한 기본값 `dwContext` MFC 인증에서 전송 되는 `CHttpFile` 에서 개체는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 `CHttpFile` 개체입니다. 호출 하는 경우 `CInternetSession::OpenURL` 또는 `CHttpConnection` 생성 하는 `CHttpFile` 개체 컨텍스트 식별자의 값으로 설정 하기 위해 기본값을 재정의할 수 있습니다. 컨텍스트 식별자는 되돌아갑니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 하 합니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="endrequest"></a>CHttpFile::EndRequest  
 이 멤버 함수를 사용 하 여 HTTP 서버에 전송 요청을 끝냅니다 호출는 [SendRequestEx](#sendrequestex) 멤버 함수입니다.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 작업을 설명 하는 플래그입니다. 목록이 적절 한 플래그에 대 한 참조 [하며](http://msdn.microsoft.com/library/windows/desktop/aa384230) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpBuffIn`  
 초기화 된에 대 한 포인터 [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) 하는 작업에 사용 되는 입력된 버퍼에 설명 합니다.  
  
 `dwContext`  
 `CHttpFile` 작업에 대한 컨텍스트 식별자입니다. 이 매개 변수에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출이 실패 한 경우 throw 되는 검사 하 여 오류의 원인을 결정 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 기본값 `dwContext` MFC 인증에서 전송 되는 `CHttpFile` 에서 개체는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 `CHttpFile` 개체입니다. 호출 하는 경우 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 생성 하는 `CHttpFile` 개체 컨텍스트 식별자의 값으로 설정 하기 위해 기본값을 재정의할 수 있습니다. 컨텍스트 식별자는 되돌아갑니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 하 합니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="getfileurl"></a>CHttpFile::GetFileURL  
 URL로 HTTP 파일의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 이 파일과 관련 된 리소스를 참조 하는 URL을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 성공적으로 호출 후에 사용 하 여 [SendRequest](#sendrequest) 또는 `CHttpFile` 성공적으로 하 여 만든 개체 [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
##  <a name="getobject"></a>CHttpFile::GetObject  
 이 연결 되는 개체의 이름을 가져오려면이 함수를 호출 `CHttpFile`합니다.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체의 이름을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 성공적으로 호출 후에 사용 하 여 [SendRequest](#sendrequest) 또는 `CHttpFile` 성공적으로 하 여 만든 개체 [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
##  <a name="getverb"></a>CHttpFile::GetVerb  
 이 연결 된 HTTP 동사 (또는 메서드)을 얻으려고이 함수를 호출 `CHttpFile`합니다.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) HTTP 동사 (또는 메서드)의 이름을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 성공적으로 호출 후에 사용 하 여 [SendRequest](#sendrequest) 또는 `CHttpFile` 성공적으로 하 여 만든 개체 [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
##  <a name="queryinfo"></a>CHttpFile::QueryInfo  
 응답을 반환 하거나 HTTP 요청에서 헤더를 요청 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    LPVOID lpvBuffer,  
    LPDWORD lpdwBufferLength,  
    LPDWORD lpdwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    CString& str,  
    LPDWORD dwIndex = NULL) const;  
  
BOOL QueryInfo(
    DWORD dwInfoLevel,  
    SYSTEMTIME* pSysTime,  
    LPDWORD dwIndex = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwInfoLevel`  
 쿼리 및 요청 된 정보 유형을 지정 하는 다음 플래그 특성의 조합:  
  
- **HTTP_QUERY_CUSTOM** 헤더 이름을 찾아에이 값을 반환 `lpvBuffer` 출력 합니다. **HTTP_QUERY_CUSTOM** 헤더를 찾을 수 없으면 어설션을 발생 시킵니다.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** 일반적으로 응답 헤더를 쿼리 하는 응용 프로그램 이지만이 플래그를 사용 하 여 응용 프로그램 요청 헤더를 쿼리할 수도 있습니다.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** 이 플래그 값은 "마지막으로 수정한 시간,"와 같은 날짜/시간 문자열을 해당 헤더에 대 한 표준 Win32 헤더 값을 반환 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조 응용 프로그램 데이터를 구문 분석에 필요 하지 않습니다. 사용 하려는이 플래그를 사용 하는 경우는 `SYSTEMTIME` 함수를 재정의 합니다.  
  
- **HTTP_QUERY_FLAG_NUMBER** 이 상태 코드와 같은 숫자 값을 갖는 해당 헤더에 대 한이 플래그는 32 비트 숫자 데이터를 반환 합니다.  
  
 참조는 **주의** 가능한 값 목록에 대 한 섹션.  
  
 `lpvBuffer`  
 정보를 받는 버퍼에 대 한 포인터입니다.  
  
 `lpdwBufferLength`  
 입력 시이 문자 또는 바이트 수의 데이터 버퍼의 길이 포함 하는 값을 가리킵니다. 참조는 **주의** 대 한 자세한 내용은이 매개 변수에 대 한 섹션.  
  
 `lpdwIndex`  
 0부터 시작 헤더 인덱스에 대 한 포인터입니다. 수 **NULL**합니다. 이 플래그를 사용 하 여 동일한 이름 가진 여러 헤더를 열거 합니다. 입력 시 `lpdwIndex` 반환할 지정된 된 헤더의 인덱스를 나타냅니다. 출력에서는 `lpdwIndex` 다음 헤더의 인덱스를 나타냅니다. 다음 인덱스를 찾을 수 없는 경우 **ERROR_HTTP_HEADER_NOT_FOUND** 반환 됩니다.  
  
 `str`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 반환 된 정보를 받는 개체입니다.  
  
 `dwIndex`  
 인덱스 값입니다. `lpdwIndex`을 참조하세요.  
  
 *pSysTime*  
 Win32에 대 한 포인터 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 성공적으로 호출 후에 사용 하 여 [SendRequest](#sendrequest) 또는 `CHttpFile` 성공적으로 하 여 만든 개체 [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
 다음과 같은 유형의 데이터를 검색할 수 있습니다 `QueryInfo`:  
  
-   문자열 (기본값)  
  
- `SYSTEMTIME`(에 대 한 "데이터:" "Expires:" 등, 헤더)  
  
- `DWORD`(에 대 한 **STATUS_CODE**, **CONTENT_LENGTH**등.)  
  
 문자열 버퍼에 기록 되 고 멤버 함수가 성공 하면 때 `lpdwBufferLength` 문자 수 값-1에서 종료에 대 한 문자열의 길이 포함 **NULL** 문자입니다.  
  
 가능한 `dwInfoLevel` 값 같습니다.  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>CHttpFile::QueryInfoStatusCode  
 이 HTTP 요청에 연결 된 상태 코드를 가져오는 함수를 호출 하 고 제공 된에 배치할 `dwStatusCode` 매개 변수입니다.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStatusCode`  
 상태 코드에 대 한 참조입니다. 상태 코드는 요청 된 이벤트의 성공 여부를 나타냅니다. 참조 **주의** 상태 코드 설명 선택 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 성공적으로 호출 후에 사용 하 여 [SendRequest](#sendrequest) 또는 `CHttpFile` 성공적으로 하 여 만든 개체 [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
 HTTP 상태 코드는 요청의 성공 여부를 나타내는 그룹에 속합니다. 다음 표에서 상태 코드 그룹 및 가장 일반적인 HTTP 상태 코드를 간략하게 설명합니다.  
  
|그룹화|의미|  
|-----------|-------------|  
|200-299|성공|  
|300-399|정보|  
|400-499|요청 오류|  
|500-599|서버 오류|  
  
 일반적인 HTTP 상태 코드:  
  
|상태 코드|의미|  
|-----------------|-------------|  
|200|URL을 찾음, 전송 수행|  
|400|인식할 수 없는 요청|  
|404|요청 URL을 찾을 수 없습니다.|  
|405|서버가 요청 된 메서드를 지원 하지 않습니다.|  
|500|알 수 없는 서버 오류|  
|503|서버 용량에 도달 함|  
  
##  <a name="sendrequest"></a>Chttpfile:: Sendrequest  
 HTTP 서버에 요청을 보내려고이 멤버 함수를 호출 합니다.  
  
```  
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLen = 0,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);

 
BOOL SendRequest(
    CString& strHeaders,  
    LPVOID lpOptional = NULL,  
    DWORD dwOptionalLen = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrHeaders`  
 보낼 헤더의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwHeadersLen`  
 로 식별 되는 헤더의 길이가 `pstrHeaders`합니다.  
  
 `lpOptional`  
 요청 헤더 직후 보낼 모든 선택적 데이터입니다. 이 일반적으로 사용에 대 한 **POST** 및 **배치** 작업 합니다. 이 수 **NULL** 보낼 선택적 데이터가 없는 경우.  
  
 *dwOptionalLen*  
 `lpOptional`의 길이입니다.  
  
 `strHeaders`  
 보내는 요청에 대 한 헤더의 이름을 포함 하는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 호출이 실패 한 경우 throw 되는 검사 하 여 오류의 원인을 결정 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체입니다.  
  
##  <a name="sendrequestex"></a>CHttpFile::SendRequestEx  
 HTTP 서버에 요청을 보내려고이 멤버 함수를 호출 합니다.  
  
```  
BOOL SendRequestEx(
    DWORD dwTotalLen,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);

 
BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,  
    LPINTERNET_BUFFERS lpBuffOut,  
    DWORD dwFlags = HSR_INITIATE,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTotalLen*  
 요청에서 보낼 바이트 수입니다.  
  
 `dwFlags`  
 작업을 설명 하는 플래그입니다. 목록이 적절 한 플래그에 대 한 참조 [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwContext`  
 `CHttpFile` 작업에 대한 컨텍스트 식별자입니다. 이 매개 변수에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `lpBuffIn`  
 초기화 된에 대 한 포인터 [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) 하는 작업에 사용 되는 입력된 버퍼에 설명 합니다.  
  
 *lpBuffOut*  
 초기화 된에 대 한 포인터 **INTERNET_BUFFERS** 하는 작업에 사용 되는 출력 버퍼에 설명 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닙니다. 호출이 실패 한 경우 throw 되는 검사 하 여 오류의 원인을 결정 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 데이터를 보내도록 응용 프로그램을 사용 하면는 [쓰기](../../mfc/reference/cinternetfile-class.md#write) 및 [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) 방식의 `CInternetFile`합니다. 이 함수의 재정의 호출 하기 전에 보낼 데이터의 길이 알고 있어야 합니다. 첫 번째 재정의 사용 하면 전송 하려는 데이터의 길이 지정할 수 있습니다. 에 대 한 포인터를 허용 하는 두 번째 재정의 **INTERNET_BUFFERS** 버퍼를 매우 자세히 설명 하기 위해 사용할 수 있는 구조입니다.  
  
 콘텐츠 파일에 기록 된 후 호출 [EndRequest](#endrequest) 작업을 종료 합니다.  
  
 에 대 한 기본값 `dwContext` MFC 인증에서 전송 되는 `CHttpFile` 에서 개체는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 `CHttpFile` 개체입니다. 호출 하는 경우 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) 또는 [CHttpConnection](../../mfc/reference/chttpconnection-class.md) 생성 하는 `CHttpFile` 개체 컨텍스트 식별자의 값으로 설정 하기 위해 기본값을 재정의할 수 있습니다. 컨텍스트 식별자는 되돌아갑니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 하 합니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예제  
 이 코드 조각은 MFCISAPI 이라는 DLL에 문자열의 내용을 보냅니다. 로컬 호스트 서버에 대 한 DLL입니다. 이 예에서는를 한 번만 호출을 사용 하는 동안 `WriteString`, 여러 번 호출을 사용 하 여 블록에서 데이터를 보내도록 허용 됩니다.  
  
 [!code-cpp[NVC_MFCWinInet # 9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection 클래스](../../mfc/reference/chttpconnection-class.md)

