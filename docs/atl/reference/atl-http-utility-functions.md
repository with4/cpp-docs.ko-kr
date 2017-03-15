---
title: "ATL HTTP 유틸리티 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: dd8b3a279148e2a5b72d96724c329e49cd5d3e5f
ms.lasthandoff: 02/24/2017

---
# <a name="atl-http-utility-functions"></a>ATL HTTP 유틸리티 함수

이러한 함수는 Url의 조작을 지원 합니다.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|안전 하지 않은 문자와 공백을 이스케이프 시퀀스로 변환 하는 URL을 canonicalizes 합니다.|  
|[AtlCombineUrl](#atlcombineurl)|기본 URL과 상대 URL을 단일 정규 URL로 결합합니다.|  
|[AtlEscapeUrl](#atlescapeurl)|모든 안전 하지 않은 문자를 이스케이프 시퀀스로 변환 합니다.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|특정 인터넷 프로토콜 또는 체계와 관련 된 기본 포트 번호를 가져옵니다.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|URL에 사용 하기에 안전 인지를 결정 합니다.|  
|[AtlUnescapeUrl](#atlunescapeurl)|이스케이프 된 문자를 원래 값으로 다시 변환 합니다.|  
|[RGBToHtml](#rgbtohtml)|변환 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값을 색 값에 해당 하는 HTML 텍스트로 합니다.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항  
 **헤더:** atlutil.h  

## <a name="a-nameatlcanonicalizeurla-atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl
안전하지 않은 문자와 공백을 이스케이프 시퀀스로 변환하는 등 URL을 정식화하려면 이 함수를 호출합니다.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `szUrl`  
 정식화 될 URL입니다.  
  
 `szCanonicalized`  
 정규화 된 URL을 수신 하도록 호출자 할당 버퍼입니다.  
  
 `pdwMaxLength`  
 포인터를 문자에서 길이 포함 하는 변수를 `szCanonicalized`합니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하지 않고 버퍼에 기록 된 문자 수를 받습니다. 함수가 실패할 경우 변수는 종료 null 문자에 대 한 공간을 포함 하는 버퍼의 바이트에 필요한 길이 받습니다.  
  
 `dwFlags`  
 이 함수의 동작을 제어 하는 플래그입니다. 참조 [ATL_URL 플래그](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 현재 버전의 처럼 동작 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) 하지만 WinInet 또는 Internet Explorer를 설치할 필요 하지 않습니다.  
  
### <a name="see-also"></a>참고 항목  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="a-nameatlcombineurla-atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl
 기본 URL과 상대 URL을 단일 정규 URL로 결합하려면 이 함수를 호출합니다.  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *szBaseUrl*  
 기본 URL입니다.  
  
 *szRelativeUrl*  
 기본 URL 기준으로 URL입니다.  
  
 `szBuffer`  
 정규화 된 URL을 수신 하도록 호출자 할당 버퍼입니다.  
  
 `pdwMaxLength`  
 포인터를 문자에서 길이 포함 하는 변수를 `szBuffer`합니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하지 않고 버퍼에 기록 된 문자 수를 받습니다. 함수가 실패할 경우 변수는 종료 null 문자에 대 한 공간을 포함 하는 버퍼의 바이트에 필요한 길이 받습니다.  
  
 `dwFlags`  
 이 함수의 동작을 제어 하는 플래그입니다. 참조 [ATL_URL 플래그](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 현재 버전의 처럼 동작 [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) 하지만 WinInet 또는 Internet Explorer를 설치할 필요 하지 않습니다.  
  
## <a name="a-nameatlescapeurla-atlescapeurl"></a><a name="atlescapeurl"></a>AtlEscapeUrl
 모든 안전하지 않은 문자를 이스케이프 시퀀스로 변환하려면 이 함수를 호출합니다.  
  
```    
inline BOOL AtlEscapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
   
inline BOOL AtlEscapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszStringIn`  
 변환할 URL입니다.  
  
 `lpszStringOut`  
 변환 된 URL을 쓸 호출자 할당 버퍼입니다.  
  
 `pdwStrLen`  
 DWORD 변수에 대 한 포인터입니다. 함수가 성공 하면 `pdwStrLen` null 종결 문자를 포함 하지 않고는 버퍼에 기록 된 문자 수를 받습니다. 함수가 실패할 경우 변수는 종료 null 문자에 대 한 공간을 포함 하는 버퍼의 바이트에 필요한 길이 받습니다. 이 방법의 와이드 문자 버전을 사용 하면 `pdwStrLen` 요구 하는 문자, 바이트 수가 아니라의 수를 받습니다.  
  
 `dwMaxLength`  
 버퍼의 크기 `lpszStringOut`합니다.  
  
 `dwFlags`  
 이 함수의 동작을 제어 하는 플래그입니다. 참조 [ATL_URL 플래그](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7)합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
## <a name="atlgetdefaulturlport"></a> 
 특정 인터넷 프로토콜 또는 체계와 관련된 기본 포트 번호를 가져오려면 이 함수를 호출합니다.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 구성표 포트 번호를 가져올를 식별 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port) 또는 연결 된 지정 된 체계 ATL_URL_INVALID_PORT_NUMBER 구성표 인식 되지 않는 경우.  

## <a name="a-nameatlisunsafeurlchara-atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 URL에서 문자를 안전하게 사용할 수 있는지 확인하려면 이 함수를 호출합니다.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `chIn`  
 안전을 위해 테스트할 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 는 입력된 문자를 안전 하 고, 없으면 **FALSE** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 문자를 Url에 사용할 수는이 함수를 사용 하 여 테스트할 수 및 사용 하 여 변환 [AtlCanonicalizeUrl](#atlcanonicalizeurl)합니다.  
  
## <a name="a-nameatlunescapeurla-atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl
 이스케이프된 문자를 원래 값으로 다시 변환하려면 이 함수를 호출합니다.  
  
```    
inline BOOL AtlUnescapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  

inline BOOL AtlUnescapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszStringIn`  
 변환할 URL입니다.  
  
 `lpszStringOut`  
 변환 된 URL을 쓸 호출자 할당 버퍼입니다.  
  
 `pdwStrLen`  
 DWORD 변수에 대 한 포인터입니다. 함수가 성공 하면 변수는 null 종결 문자를 포함 하지 않고 버퍼에 기록 된 문자 수를 받습니다. 함수가 실패할 경우 변수는 종료 null 문자에 대 한 공간을 포함 하는 버퍼의 바이트에 필요한 길이 받습니다.  
  
 `dwMaxLength`  
 버퍼의 크기 `lpszStringOut`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 적용 하 여 변환 프로세스를 반대로 [AtlEscapeUrl](#atlescapeurl)합니다.  
  
## <a name="a-namergbtohtmla-rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml
변환 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값을 색 값에 해당 하는 HTML 텍스트로 합니다.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 RGB 색상 값입니다.  
  
 `pbOut`  
 HTML 색 값에 대 한 텍스트를 받을 호출자 할당 버퍼입니다. 버퍼 공간이 있어야 8 자 이상 null 종결자에 대 한 공간을 포함 하 여에 대 한).  
  
 *nBuffer*  
 (Null 종결자에 대 한 공간 포함)는 버퍼의 바이트 크기입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 HTML 색상 값은 2 자리를 사용 하 여 각 색의 빨강, 녹색 및 파랑 구성 요소에는 6 자리 16 진수 값 뒤에 파운드 기호 (예를 들어 #FFFFFF는 흰색).  
  
## <a name="a-namesystemtimetohttpdatea-systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
시스템 시간을 HTTP 헤더에서 사용하기에 적합한 형식의 문자열로 변환하려면 이 함수를 호출합니다.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>매개 변수  
 `st`  
 HTTP 서식 문자열로 달성 해야 할 시스템 시간입니다.  
  
 *strTime*  
 RFC 2616에 정의 된 날짜 시간 HTTP 수신 하는 문자열 변수에 대 한 참조 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) 및 RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>참고 항목  
 [개념](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)   


