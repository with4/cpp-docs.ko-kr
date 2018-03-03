---
title: "클래스를 cUrl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb60fcef5fdfd30b4121f5c2277667829772dcd6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="curl-class"></a>CUrl 클래스
이 클래스는 URL을 나타냅니다. 기존 URL을 구문 분석 하는지 여부를 개별적으로 URL의 각 요소를 조작할 수 있습니다 문자열 또는 처음부터 문자열을 작성 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CUrl
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CUrl::CUrl](#curl)|생성자입니다.|  
|[CUrl:: ~ CUrl](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|URL 문자열을 정규 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CUrl::Clear](#clear)|URL 필드 모두 선택 취소 하려면이 메서드를 호출 합니다.|  
|[CUrl::CrackUrl](#crackurl)|암호 해독 하 고 URL의 구문 분석에이 메서드를 호출 합니다.|  
|[CUrl::CreateUrl](#createurl)|URL을 만드는 데이 메서드를 호출 합니다.|  
|[CUrl::GetExtraInfo](#getextrainfo)|추가 정보를 가져오려면이 메서드를 호출 (예: *텍스트* 또는 # *텍스트*) URL에서 합니다.|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|추가 정보의 길이 가져오려면이 메서드를 호출 (같은 *텍스트* 또는 # *텍스트*) URL에서 검색할 수 있습니다.|  
|[CUrl::GetHostName](#gethostname)|URL에서 호스트 이름을 가져오기 위해이 메서드를 호출 합니다.|  
|[CUrl::GetHostNameLength](#gethostnamelength)|호스트 이름의 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPassword](#getpassword)|URL에서 암호를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPasswordLength](#getpasswordlength)|암호의 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetPortNumber](#getportnumber)|ATL_URL_PORT 측면에서 포트 번호를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetScheme](#getscheme)|URL 스키마를 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetSchemeName](#getschemename)|URL 구성표 이름을 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|URL 구성표 이름의 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlLength](#geturllength)|URL 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlPath](#geturlpath)|URL 경로 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|URL 경로 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::GetUserName](#getusername)|URL에서 사용자 이름을 가져오기 위해이 메서드를 호출 합니다.|  
|[CUrl::GetUserNameLength](#getusernamelength)|사용자 이름의 길이 가져오려면이 메서드를 호출 합니다.|  
|[CUrl::SetExtraInfo](#setextrainfo)|추가 정보를 설정 하려면이 메서드를 호출 (예: *텍스트* 또는 # *텍스트*) URL의 합니다.|  
|[CUrl::SetHostName](#sethostname)|호스트 이름을 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetPassword](#setpassword)|암호를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetPortNumber](#setportnumber)|ATL_URL_PORT 측면에서 포트 번호를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetScheme](#setscheme)|URL 스키마를 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetSchemeName](#setschemename)|URL 구성표 이름을 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetUrlPath](#seturlpath)|URL 경로 설정 하려면이 메서드를 호출 합니다.|  
|[CUrl::SetUserName](#setusername)|사용자 이름을 설정 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|지정 된 할당 `CUrl` 개체를 현재 `CUrl` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CUrl`URL 경로 또는 포트 번호 등의 필드를 조작할 수 있습니다. `CUrl`다음 형식의 Url을 인식합니다.  
  
 \<체계 >://\<사용자 이름 >:\<암호 > @\<호스트 이름 >:\<포트 번호 > /\<UrlPath >\<되어 나타날 >  
  
 (일부 필드는 선택 사항입니다.) 예,이 URL을 참조 하십시오.  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl) 다음과 같은 구문 분석:  
  
-   스키마: "http" 또는 [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   사용자 이름: "someone"  
  
-   암호 "password:"  
  
-   호스트 이름: "www.microsoft.com"  
  
-   PortNumber: 80  
  
-   UrlPath: "visualc/stuff.htm"  
  
-   되어 나타날: "#contents"  
  
 UrlPath 필드 (예를 들어) 조작 하려면 사용 [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), 및 [SetUrlPath](#seturlpath)합니다. 사용 하 여 [CreateUrl](#createurl) 전체 URL 문자열을 만듭니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  
  
##  <a name="canonicalize"></a>CUrl::Canonicalize  
 URL 문자열을 정규 형식으로 변환 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 정규화를 제어 하는 플래그입니다. 플래그가 지정 된 경우 ( `dwFlags` = 0), 메서드가 안전 하지 않은 문자와 메타 시퀀스 변환 하는 (같은 \\., \..., 및 \\...) 값이 되도록 이스케이프 시퀀스입니다. `dwFlags`다음 값 중 하나일 수 있습니다.  
  
-   ATL_URL_BROWSER_MODE: 인코딩하거나 후 "#" 문자를 해독 하지 않습니다 또는 "" 고 후 후행 공백만 제거 하지 않습니다 ""입니다. 이 값을 지정 하지 않으면 전체 URL은 인코딩되고 후행 공백은 제거 됩니다.  
  
-   ATL_URL _DECODE: 하는 URL은 구문 분석 전에 이스케이프 시퀀스를 포함 하 여 모든 %XX 시퀀스를 변환 합니다.  
  
-   ATL_URL _ENCODE_PERCENT: 발생 하는 백분율 기호를 인코딩합니다. 기본적으로 백분율 기호는 인코딩되지 않습니다.  
  
-   ATL_URL _ENCODE_SPACES_ONLY: 공간만 인코딩합니다.  
  
-   ATL_URL _NO_ENCODE: 안전 하지 않은 문자를 이스케이프 시퀀스로 변환 하지 않습니다.  
  
-   ATL_URL _NO_META: 메타 시퀀스는 제거 되지 않습니다 (같은 "."및"..") URL에서 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 정규 형식으로 변환에서는 안전 하지 않은 문자와 공백을 이스케이프 시퀀스를 변환 합니다.  
  
##  <a name="clear"></a>CUrl::Clear  
 URL 필드 모두 선택 취소 하려면이 메서드를 호출 합니다.  
  
```
inline void Clear() throw();
```  
  
##  <a name="crackurl"></a>CUrl::CrackUrl  
 암호 해독 하 고 URL의 구문 분석에이 메서드를 호출 합니다.  
  
```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszUrl`  
 URL입니다.  
  
 `dwFlags`  
 모든 이스케이프 문자를 변환 하려면 ATL_URL_DECODE 또는 ATL_URL_ESCAPE 지정 `lpszUrl` 을 구문 분석 한 후 실제 값입니다. (이전 Visual c + + 2005 ATL_URL_DECODE 변환 되어 모든 이스케이프 문자 구문 분석 하기 전에.)  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="createurl"></a>CUrl::CreateUrl  
 이 메서드는 CUrl 개체의 구성 요소 필드에서 URL 문자열을 만듭니다.  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszUrl*  
 전체 URL 문자열을 저장 하는 문자열 버퍼입니다.  
  
 `pdwMaxLength`  
 최대 길이 *lpszUrl* 문자열 버퍼입니다.  
  
 `dwFlags`  
 모든 이스케이프 문자를 변환 하는 ATL_URL_ESCAPE 지정 *lpszUrl* 을 실제 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 다음과 같은 형식을 사용 하 여 전체 URL 문자열을 생성 하기 위해 개별 필드를 추가 합니다.  
  
 **\<체계 >://\<사용자 >:\<전달 > @\<도메인 >:\<포트 >\<경로 >\<추가 >**  
  
 이 메서드를 호출 하는 경우는 `pdwMaxLength` 매개 변수에서 참조 하는 문자열 버퍼의 최대 길이 포함 처음 해야는 *lpszUrl* 매개 변수입니다. 값은 `pdwMaxLength` 매개 변수는 URL 문자열의 실제 길이으로 업데이트 됩니다.  
  
### <a name="example"></a>예  
 이 샘플에 CUrl 개체를 해당 URL 문자열을 검색 하 고 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="curl"></a>CUrl::CUrl  
 생성자입니다.  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `urlThat`  
 `CUrl` URL을 만드는 데 복사할 개체입니다.  
  
##  <a name="dtor"></a>CUrl:: ~ CUrl  
 소멸자입니다.  
  
```
~CUrl() throw();
```  
  
##  <a name="getextrainfo"></a>CUrl::GetExtraInfo  
 추가 정보를 가져오려면이 메서드를 호출 (예: *텍스트* 또는 # *텍스트*) URL에서 합니다.  
  
```
inline LPCTSTR GetExtraInfo() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 추가 정보를 포함 하는 문자열을 반환 합니다.  
  
##  <a name="getextrainfolength"></a>CUrl::GetExtraInfoLength  
 추가 정보의 길이 가져오려면이 메서드를 호출 (같은 *텍스트* 또는 # *텍스트*) URL에서 검색할 수 있습니다.  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 추가 정보를 포함 하는 문자열의 길이 반환 합니다.  
  
##  <a name="gethostname"></a>CUrl::GetHostName  
 URL에서 호스트 이름을 가져오기 위해이 메서드를 호출 합니다.  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 호스트 이름을 반환합니다.  
  
##  <a name="gethostnamelength"></a>CUrl::GetHostNameLength  
 호스트 이름의 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 호스트 이름 길이 반환합니다.  
  
##  <a name="getpassword"></a>CUrl::GetPassword  
 URL에서 암호를 가져오려면이 메서드를 호출 합니다.  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 암호를 반환 합니다.  
  
##  <a name="getpasswordlength"></a>CUrl::GetPasswordLength  
 암호의 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 암호의 길이 반환합니다.  
  
##  <a name="getportnumber"></a>CUrl::GetPortNumber  
 포트 번호를 가져오려면이 메서드를 호출 합니다.  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 포트 번호를 반환합니다.  
  
##  <a name="getscheme"></a>CUrl::GetScheme  
 URL 스키마를 가져오려면이 메서드를 호출 합니다.  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 [ATL_URL_SCHEME](atl-url-scheme-enum.md) URL의 체계를 설명 하는 값입니다.  
  
##  <a name="getschemename"></a>CUrl::GetSchemeName  
 URL 구성표 이름을 가져오려면이 메서드를 호출 합니다.  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 URL 구성표 이름 (예: "http" 또는 "ftp")를 반환합니다.  
  
##  <a name="getschemenamelength"></a>CUrl::GetSchemeNameLength  
 URL 구성표 이름의 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 URL 구성표 이름 길이 반환합니다.  
  
##  <a name="geturllength"></a>CUrl::GetUrlLength  
 URL 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 URL 길이 반환합니다.  
  
##  <a name="geturlpath"></a>CUrl::GetUrlPath  
 URL 경로 가져오려면이 메서드를 호출 합니다.  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 URL 경로 반환합니다.  
  
##  <a name="geturlpathlength"></a>CUrl::GetUrlPathLength  
 URL 경로 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 URL 경로 길이 반환합니다.  
  
##  <a name="getusername"></a>CUrl::GetUserName  
 URL에서 사용자 이름을 가져오기 위해이 메서드를 호출 합니다.  
  
```
inline LPCTSTR GetUserName() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 사용자 이름을 반환합니다.  
  
##  <a name="getusernamelength"></a>CUrl::GetUserNameLength  
 사용자 이름의 길이 가져오려면이 메서드를 호출 합니다.  
  
```
inline DWORD GetUserNameLength() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 사용자 이름 길이 반환합니다.  
  
##  <a name="operator_eq"></a>CUrl::operator =  
 지정 된 할당 `CUrl` 개체를 현재 `CUrl` 개체입니다.  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `urlThat`  
 `CUrl` 현재 개체에 복사할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 개체에 대 한 참조를 반환합니다.  
  
##  <a name="setextrainfo"></a>CUrl::SetExtraInfo  
 추가 정보를 설정 하려면이 메서드를 호출 (예: *텍스트* 또는 # *텍스트*) URL의 합니다.  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszInfo*  
 URL에 포함 되도록 추가 정보가 포함 된 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="sethostname"></a>CUrl::SetHostName  
 호스트 이름을 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszHost`  
 호스트 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="setpassword"></a>CUrl::SetPassword  
 암호를 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszPass*  
 암호입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="setportnumber"></a>CUrl::SetPortNumber  
 포트 번호를 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *nPrt*  
 포트 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="setscheme"></a>CUrl::SetScheme  
 URL 스키마를 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nScheme`  
 중 하나는 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 구성표에 대 한 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 이름으로 구성표를 설정할 수도 있습니다 (참조 [CUrl::SetSchemeName](#setschemename)).  
  
##  <a name="setschemename"></a>CUrl::SetSchemeName  
 URL 구성표 이름을 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszSchm*  
 URL 구성표 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>설명  
 체계를 사용 하 여 설정할 수도 있습니다는 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 상수 (참조 [CUrl::SetScheme](#setscheme)).  
  
##  <a name="seturlpath"></a>CUrl::SetUrlPath  
 URL 경로 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszPath`  
 URL 경로입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
##  <a name="setusername"></a>CUrl::SetUserName  
 사용자 이름을 설정 하려면이 메서드를 호출 합니다.  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszUser*  
 사용자 이름입니다.  
  
### <a name="return-value"></a>반환 값  
 성공할 경우 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../atl/reference/atl-classes.md)
