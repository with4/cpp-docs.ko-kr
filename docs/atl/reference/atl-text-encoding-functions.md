---
title: "ATL의 텍스트 인코딩 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
caps.latest.revision: 3
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: 86433bebe3fe84a027d7725525e028d80b67e358
ms.lasthandoff: 02/24/2017

---
# <a name="atl-text-encoding-functions"></a>ATL의 텍스트 인코딩 함수
이러한 함수는 텍스트 인코딩 및 디코딩을 지원 합니다.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.|   
|[AtlGetVersion](#atlgetversion)|사용 중인 ATL 라이브러리의 버전을 가져오려면이 함수를 호출 합니다.  |  
|[AtlHexDecode](#atlhexdecode)|에 대 한 이전 호출에서와 같이&16; 진수 텍스트로 인코딩된 데이터의 문자열을 디코딩합니다 [AtlHexEncode](#atlhexencode)합니다.|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|지정된 길이의&16;진수로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[AtlHexEncode](#atlhexencode)|16진수 텍스트 문자열로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[AtlHexValue](#atlhexvalue)|16진수의 숫자 값을 가져오려면 이 함수를 호출합니다. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|유니코드 문자열을 UTF-8로 변환하려면 이 함수를 호출합니다. |
|[BEncode](#bencode)|"B" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.|
|[BEncodeGetRequiredLength](#beencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[EscapeXML](#escapexml)|XML에서 사용하기에 안전하지 않은 문자를 안전한 문자로 변환하려면 이 함수를 호출합니다.|
|[GetExtendedChars](#getextendedchars)|문자열에서 확장된 문자 수를 가져오려면 이 함수를 호출합니다.|
|[IsExtendedChar](#isextendedchar)|지정한 문자가 확장된 문자(32보다 작거나 126보다 크고 탭, 줄 바꿈 또는 캐리지 리턴이 아님)인지 확인하려면 이 함수를 호출합니다.|
|[QEncode](#qencode)|"Q" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[QPDecode](#qpdecode)|에 대 한 이전 호출에서와 같은 quoted-printable 형식으로 인코딩된 데이터의 문자열을 디코딩합니다 [QPEncode](#qpencode)합니다.|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|지정된 길이의 quoted-printable로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[QPEncode](#qpencode)|quoted-printable 형식으로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|
|[UUDecode](#uudecode)|에 대 한 이전 호출에서와 같이 uuencode 된 데이터의 문자열을 디코딩합니다 [UUEncode](#uuencode)합니다.|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|지정된 길이의 uuencode된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.|
|[UUEncode](#uuencode)|일부 데이터를 uuencode하려면 이 함수를 호출합니다. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.|

## <a name="requirements"></a>요구 사항  
 **헤더:** atlenc.h  
 
## <a name="a-nameatlgethexvaluea-atlgethexvalue"></a><a name="atlgethexvalue"></a>AtlGetHexValue
16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `chIn`  
 16 진수 문자 '0'-'9', 'A'-'F' 또는 'a'-'f'입니다.  
  
### <a name="return-value"></a>반환 값  
 숫자 값으로&16; 진수를 해석 하는 입력된 문자입니다. 예를 들어 0의 값을 반환 하는 '0'을 입력 하 고 'A'의 입력 값이 10 반환 합니다. 입력된 문자는&16; 진수가 없는 경우이 함수는-1을 반환 합니다.  
  
## <a name="a-nameatlgetversiona-atlgetversion"></a><a name="atlgetversion"></a>AtlGetVersion
사용 중인 ATL 라이브러리의 버전을 가져오려면이 함수를 호출 합니다.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>매개 변수  
 `pReserved`  
 예약 된 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `DWORD` 컴파일 또는 실행 여부를 지정 하는 ATL 라이브러리의 버전의 정수 값입니다.  
  
## <a name="example"></a>예제  
 함수는 다음과 같이 호출 되어야 합니다.  
  
 [!code-cpp[NVC_ATL_Utilities #&95;](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

## <a name="a-nameatlhexdecodea-atlhexdecode"></a><a name="atlhexdecode"></a>AtlHexDecode
에 대 한 이전 호출에서와 같이&16; 진수 텍스트로 인코딩된 데이터의 문자열을 디코딩합니다 [AtlHexEncode](#atlhexencode)합니다.  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pSrcData`  
 디코딩할 데이터를 포함 하는 문자열입니다.  
  
 `nSrcLen`  
 문자 길이 `pSrcData`합니다.  
  
 `pbDest`  
 디코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 바이트의 길이 포함 하는 변수에 대 한 포인터 `pbDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트에 필요한 길이 받습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
## <a name="a-nameatlhexdecodegetrequiredlengtha-atlhexdecodegetrequiredlength"></a><a name="atlhexdecodegetrequiredlength"></a>AtlHexDecodeGetRequiredLength
지정된 길이의&16;진수로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩된 문자열에서 문자의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 디코딩된 문자열을 저장할 수 있는 버퍼 필요한 바이트 수가 `nSrcLen` 문자입니다.  
  
## <a name="a-nameatlhexencodea-atlhexencode"></a><a name="atlhexencode"></a>AtlHexEncode
16진수 텍스트 문자열로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 데이터를 인코딩할 수를 포함 하는 버퍼입니다.  
  
 `nSrcLen`  
 데이터를 인코딩할 수의 바이트 길이입니다.  
  
 `szDest`  
 인코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 포인터를 문자에서 길이 포함 하는 변수를 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자 수를 받습니다. 함수가 실패할 경우 변수는 버퍼의 문자에 필요한 길이 받습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 원본 데이터의 각 바이트는 16 진수 문자를 2로 인코딩됩니다.  
  
## <a name="a-nameatlhexencodegetrequiredlengtha-atlhexencodegetrequiredlength"></a><a name="atlhexencodegetrequiredlength"></a>AtlHexEncodeGetRequiredLength
지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩할 데이터의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 `nSrcLen` 바이트입니다.  
  
## <a name="a-nameatlhexvaluea-atlhexvalue"></a><a name="atlhexvalue"></a>AtlHexValue
16진수의 숫자 값을 가져오려면 이 함수를 호출합니다.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `chIn`  
 16 진수 문자 '0'-'9', 'A'-'F' 또는 'a'-'f'입니다.  
  
### <a name="return-value"></a>반환 값  
 숫자 값으로&16; 진수를 해석 하는 입력된 문자입니다. 예를 들어 0의 값을 반환 하는 '0'을 입력 하 고 'A'의 입력 값이 10 반환 합니다. 입력된 문자는&16; 진수가 없는 경우이 함수는-1을 반환 합니다.  
  
## <a name="a-nameatlunicodetoutf8a-atlunicodetoutf8"></a><a name="atlunicodetoutf8"></a>AtlUnicodeToUTF8
유니코드 문자열을 UTF-8로 변환하려면 이 함수를 호출합니다.  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *wszSrc*  
 변환할 유니코드 문자열  
  
 `nSrc`  
 유니코드 문자열의 문자 길이입니다.  
  
 `szDest`  
 변환 된 문자열을 받을 호출자 할당 버퍼입니다.  
  
 `nDest`  
 버퍼의 길이 (바이트)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 변환된 된 문자열에 대 한 문자 수를 반환합니다.  
  
### <a name="remarks"></a>주의  
 변환된 된 문자열에 필요한 버퍼의 크기를 확인 하려면 0을 전달 하는이 함수를 호출 `szDest` 및 `nDest`합니다.  
  
## <a name="a-namebencodea-bencode"></a><a name="bencode"></a>BEncode  
"B" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.  
  
```  
inline BOOL BEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 데이터를 인코딩할 수를 포함 하는 버퍼입니다.  
  
 `nSrcLen`  
 데이터를 인코딩할 수의 바이트 길이입니다.  
  
 `szDest`  
 인코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 포인터를 문자에서 길이 포함 하는 변수를 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자 수를 받습니다. 함수가 실패할 경우 변수는 버퍼의 문자에 필요한 길이 받습니다.  
  
 `pszCharSet`  
 변환에 사용 하도록 설정 하는 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 RFC 2047에 설명 된 "B" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-namebeencodegetrequiredlengtha-bencodegetrequiredlength"></a><a name="beencodegetrequiredlength"></a>BEncodeGetRequiredLength 
지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩할 데이터의 바이트 수입니다.  
  
 `nCharsetLen`  
 문자 변환 하는 데 사용 하 여 집합의 문자 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 `nSrcLen` 바이트입니다.  
  
### <a name="remarks"></a>주의  
 RFC 2047에 설명 된 "B" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameescapexmla-escapexml"></a><a name="escapexml"></a>EscapeXML
XML에서 사용하기에 안전하지 않은 문자를 안전한 문자로 변환하려면 이 함수를 호출합니다.  
  
```  
inline int EscapeXML(  
   const wchar_t * szIn,  
   int nSrcLen,  
   wchar_t * szEsc,  
   int nDestLen,  
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `szIn`  
 변환할 문자열입니다.  
  
 *nSrclen*  
 변환 될 문자열의 문자 길이입니다.  
  
 *szEsc*  
 변환 된 문자열을 받을 호출자 할당 버퍼입니다.  
  
 *nDestLen*  
 호출자 할당 버퍼의 문자 길이입니다.  
  
 `dwFlags`  
 변환을 수행 하는 하는 방법을 설명 하는 플래그입니다. 참조 [ATL_ESC 플래그](http://msdn.microsoft.com/library/daf3aa3c-7498-4d63-9fb6-e05b4815c2b8)합니다.  
  
### <a name="return-value"></a>반환 값  
 변환된 된 문자열의 문자 길이입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 의해 수행 되는 가능한 변환 테이블에 나와 있습니다.  
  
|소스|대상|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="a-namegetextendedcharsa-getextendedchars"></a><a name="getextendedchars"></a>GetExtendedChars
문자열에서 확장된 문자 수를 가져오려면 이 함수를 호출합니다.  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `szSrc`  
 분석할 문자열입니다.  
  
 `nSrcLen`  
 문자에서 문자열의 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 확장 된 문자를 기준으로 하는 문자열 내에 있는 수를 반환 [IsExtendedChar](#isextendedchar)합니다.  
  
## <a name="a-nameisextendedchara-isextendedchar"></a><a name="isextendedchar"></a>IsExtendedChar
지정한 문자가 확장된 문자(32보다 작거나 126보다 크고 탭, 줄 바꿈 또는 캐리지 리턴이 아님)인지 확인하려면 이 함수를 호출합니다.  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 *ch*  
 테스트할 문자  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 문자 연장 되 면 **FALSE** 그렇지 않은 경우.  
  
## <a name="a-nameqencodea-qencode"></a><a name="qencode"></a>QEncode
"Q" 인코딩을 사용하여 일부 데이터를 변환하려면 이 함수를 호출합니다.  
  
```  
inline BOOL QEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet,  
   int* pnNumEncoded = NULL) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 데이터를 인코딩할 수를 포함 하는 버퍼입니다.  
  
 `nSrcLen`  
 데이터를 인코딩할 수의 바이트 길이입니다.  
  
 `szDest`  
 인코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 포인터를 문자에서 길이 포함 하는 변수를 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자 수를 받습니다. 함수가 실패할 경우 변수는 버퍼의 문자에 필요한 길이 받습니다.  
  
 `pszCharSet`  
 변환에 사용 하도록 설정 하는 문자입니다.  
  
 *pnNumEncoded*  
 반환 시 변환 하는 안전 하지 않은 문자 수를 포함 하는 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 RFC 2047에 설명 된 "Q" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqencodegetrequiredlengtha-qencodegetrequiredlength"></a><a name="qencodegetrequiredlength"></a>QEncodeGetRequiredLength 
지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩할 데이터의 바이트 수입니다.  
  
 `nCharsetLen`  
 문자 변환 하는 데 사용 하 여 집합의 문자 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 `nSrcLen` 바이트입니다.  
  
### <a name="remarks"></a>주의  
 RFC 2047에 설명 된 "Q" 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqpdecodea-qpdecode"></a><a name="qpdecode"></a>QPDecode
에 대 한 이전 호출에서와 같은 quoted-printable 형식으로 인코딩된 데이터의 문자열을 디코딩합니다 [QPEncode](#qpencode)합니다.  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pbSrcData`  
 디코딩할 데이터를 포함 하는 버퍼입니다.  
  
 [in] `nSrcLen`  
 바이트 길이 `pbSrcData`합니다.  
  
 [out] `szDest`  
 디코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 [out] `pnDestLen`  
 바이트의 길이 포함 하는 변수에 대 한 포인터 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트에 필요한 길이 받습니다.  
  
 [in] `dwFlags`  
 변환을 수행 하는 하는 방법을 설명 하는 플래그입니다. 참조 [ATLSMTP_QPENCODE 플래그](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`를 반환하고 실패하면 `FALSE`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 RFC 2045에 설명 된 따옴표가 붙은 인쇄 가능한 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpdecodegetrequiredlengtha-qpdecodegetrequiredlength"></a><a name="qpdecodegetrequiredlength"></a>QPDecodeGetRequiredLength
지정된 길이의 quoted-printable로 인코딩된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩된 문자열에서 문자의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 디코딩된 문자열을 저장할 수 있는 버퍼 필요한 바이트 수가 `nSrcLen` 문자입니다.  
  
### <a name="remarks"></a>주의  
 RFC 2045에 설명 된 따옴표가 붙은 인쇄 가능한 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodea-qpencode"></a><a name="qpencode"></a>QPEncode
quoted-printable 형식으로 일부 데이터를 인코딩하려면 이 함수를 호출합니다.  
  
```  
inline BOOL QPEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 데이터를 인코딩할 수를 포함 하는 버퍼입니다.  
  
 `nSrcLen`  
 데이터를 인코딩할 수의 바이트 길이입니다.  
  
 `szDest`  
 인코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 포인터를 문자에서 길이 포함 하는 변수를 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자 수를 받습니다. 함수가 실패할 경우 변수는 버퍼의 문자에 필요한 길이 받습니다.  
  
 `dwFlags`  
 변환을 수행 하는 하는 방법을 설명 하는 플래그입니다. 참조 [ATLSMTP_QPENCODE 플래그](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4)합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 RFC 2045에 설명 된 따옴표가 붙은 인쇄 가능한 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodegetrequiredlengtha-qpencodegetrequiredlength"></a><a name="qpencodegetrequiredlength"></a>QPEncodeGetRequiredLength
지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩할 데이터의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 `nSrcLen` 바이트입니다.  
  
### <a name="remarks"></a>주의  
 RFC 2045에 설명 된 따옴표가 붙은 인쇄 가능한 인코딩 스키마 ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameuudecodea-uudecode"></a><a name="uudecode"></a>UUDecode
에 대 한 이전 호출에서와 같이 uuencode 된 데이터의 문자열을 디코딩합니다 [UUEncode](#uuencode)합니다.  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 디코딩할 데이터를 포함 하는 문자열입니다.  
  
 `nSrcLen`  
 바이트 길이 `pbSrcData`합니다.  
  
 `pbDest`  
 디코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 바이트의 길이 포함 하는 변수에 대 한 포인터 `pbDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 바이트 수를 받습니다. 함수가 실패할 경우 변수 버퍼의 바이트에 필요한 길이 받습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 이 uuencoding 구현에는 POSIX P1003.2b/D11 사양을 따릅니다.  
  
## <a name="a-nameuudecodegetrequiredlengtha-uudecodegetrequiredlength"></a><a name="uudecodegetrequiredlength"></a>UUDecodeGetRequiredLength
지정된 길이의 uuencode된 문자열에서 디코딩된 데이터를 포함할 수 있는 버퍼를 바이트 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩된 문자열에서 문자의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 디코딩된 문자열을 저장할 수 있는 버퍼 필요한 바이트 수가 `nSrcLen` 문자입니다.  
  
### <a name="remarks"></a>주의  
 이 uuencoding 구현에는 POSIX P1003.2b/D11 사양을 따릅니다.  
  
## <a name="a-nameuuencodea-uuencode"></a><a name="uuencode"></a>UUEncode
일부 데이터를 uuencode하려면 이 함수를 호출합니다.  
  
```  
inline BOOL UUEncode(  
   const BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCTSTR lpszFile = _T("file"),  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `pbSrcData`  
 데이터를 인코딩할 수를 포함 하는 버퍼입니다.  
  
 `nSrcLen`  
 데이터를 인코딩할 수의 바이트 길이입니다.  
  
 `szDest`  
 인코딩된 데이터를 받는 호출자 할당 버퍼입니다.  
  
 `pnDestLen`  
 포인터를 문자에서 길이 포함 하는 변수를 `szDest`합니다. 함수가 성공 하면 변수는 버퍼에 쓴 문자 수를 받습니다. 함수가 실패할 경우 변수는 버퍼의 문자에 필요한 길이 받습니다.  
  
 *lpszFile*  
 ATLSMTP_UUENCODE_HEADER에 지정 된 경우 헤더에 추가할 파일 `dwFlags`합니다.  
  
 `dwFlags`  
 이 함수의 동작을 제어 하는 플래그입니다. 참조 [ATLSMTP_UUENCODE 플래그](http://msdn.microsoft.com/library/ecb79b81-b764-4a48-a05c-a9dee6e7bbce)합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 이 uuencoding 구현에는 POSIX P1003.2b/D11 사양을 따릅니다.  
  
## <a name="a-nameuuencodegetrequiredlengtha-uuencodegetrequiredlength"></a><a name="uuencodegetrequiredlength"></a>UUEncodeGetRequiredLength
지정된 크기의 데이터에서 디코딩된 문자열을 포함할 수 있는 버퍼를 문자 크기로 가져오려면 이 함수를 호출합니다.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 `nSrcLen`  
 인코딩할 데이터의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 인코딩된 데이터를 보유할 수 있는 버퍼에 필요한 문자 수가 `nSrcLen` 바이트입니다.  
  
### <a name="remarks"></a>주의  
 이 uuencoding 구현에는 POSIX P1003.2b/D11 사양을 따릅니다.  
  
### <a name="see-also"></a>참고 항목  
 [개념](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM 데스크톱 구성 요소](../../atl/atl-com-desktop-components.md)   
