---
title: "인터넷 URL 전역 구문 분석 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 3aec259acae2f5e9c9b65ac4e5c898ca57ff3d52
ms.lasthandoff: 02/24/2017

---
# <a name="internet-url-parsing-globals"></a>인터넷 URL 전역 구문 분석
클라이언트가 인터넷 서버에는 쿼리를 보내, 클라이언트에 대 한 정보를 추출 하는 URL 전역 구문 분석 중 하나를 사용할 수 있습니다.  
  
### <a name="internet-url-parsing-globals"></a>인터넷 URL 전역 구문 분석  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|URL 문자열을 구문 분석 하 고 서비스 및 해당 구성 요소의 종류를 반환 합니다.|  
|[AfxParseURLEx](#afxparseurlex)|URL 문자열을 구문 분석 하 고 사용자 이름 및 암호 제공 뿐만 아니라 서비스 및 해당 구성 요소 유형을 반환 합니다.|  
  
##  <a name="a-nameafxparseurla--afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL  
 이 전역는 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrURL*  
 구문 분석할 수에 대 한 URL을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwServiceType`  
 인터넷 서비스의 유형을 나타냅니다. 다음과 같은 값을 사용할 수 있습니다.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 서비스 형식 다음 URL의 첫 번째 세그먼트입니다.  
  
 `strObject`  
 URL에서 참조 하는 개체 (비어 있을 수 있습니다).  
  
 `nPort`  
 있는 경우 URL의 서버 또는 개체 부분에서 확인 했습니다.  
  
### <a name="return-value"></a>반환 값  
 URL 구문 분석 했습니다. 0이 아닌 비어 있거나, 알려진된 인터넷 서비스 형식이 없는 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 URL 문자열을 구문 분석 하 고 서비스 및 해당 구성 요소의 형식을 반환 합니다.  
  
 예를 들어 `AfxParseURL` 형식의 Url을 구문 분석 하 여 **service://server/dir/dir/object.ext:port** 다음과 같이 저장 된 해당 구성 요소를 반환 합니다.  
  
 `strServer`"server" = =  
  
 `strObject`= = "/ dir/dir/object/object.ext"  
  
 `nPort`#port = =  
  
 `dwServiceType`#service = =  
  
> [!NOTE]
>  이 함수를 호출 하려면 프로젝트 AFXINET 포함 해야 합니다.&8;.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxinet.h  
  
##  <a name="a-nameafxparseurlexa--afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx  
 이 전역 함수는 확장 된 버전의 [AfxParseURL](#afxparseurl) 을 사용 하는 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)합니다.  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>매개 변수  
 *pstrURL*  
 구문 분석할 수에 대 한 URL을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwServiceType`  
 인터넷 서비스의 유형을 나타냅니다. 다음과 같은 값을 사용할 수 있습니다.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 서비스 형식 다음 URL의 첫 번째 세그먼트입니다.  
  
 `strObject`  
 URL에서 참조 하는 개체 (비어 있을 수 있습니다).  
  
 `nPort`  
 있는 경우 URL의 서버 또는 개체 부분에서 확인 했습니다.  
  
 *여 strUsername*  
 에 대 한 참조는 `CString` 사용자의 이름을 포함 하는 개체입니다.  
  
 `strPassword`  
 에 대 한 참조는 `CString` 사용자의 암호를 포함 하는 개체입니다.  
  
 `dwFlags`  
 URL 구문 분석 하는 방법을 제어 하는 플래그입니다. 다음 값의 조합일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|**ICU_DECODE**|%XX 이스케이프 시퀀스를 문자로 변환 합니다.|  
|**ICU_NO_ENCODE**|이스케이프 시퀀스를 안전 하지 않은 문자를 변환 하지 않습니다.|  
|**ICU_NO_META**|메타 시퀀스 (예: "\."를 제거 하지 마십시오 및 "\...") URL입니다.|  
|**ICU_ENCODE_SPACES_ONLY**|만 공간을 인코딩하십시오.|  
|**ICU_BROWSER_MODE**|인코딩 또는 '#' 뒤에 문자를 디코딩할 안 함 또는 ', 후 후행 공백을 제거 하지 않는 '. 이 값을 지정 하지 않으면 전체 URL 인코딩 되 고 후행 공백이 제거 됩니다.|  
  
 함수 변환 안전 하지 않은 문자와 메타 시퀀스는 플래그가 없는 MFC 기본값을 사용 하는 경우 (같은 \\., \..., 및 \\...)를 이스케이프 시퀀스를 합니다.  
  
### <a name="return-value"></a>반환 값  
 URL 구문 분석 했습니다. 0이 아닌 비어 있거나, 알려진된 인터넷 서비스 형식이 없는 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 URL 문자열을 구문 분석 하 고 서비스 및 해당 구성 요소와 사용자의 이름 및 암호를 제공 하는 형식을 반환 합니다. 플래그는 어떻게 안전 하지 않은 문자를 나타냅니다 처리 됩니다.  
  
> [!NOTE]
>  이 함수를 호출 하려면 프로젝트 AFXINET 포함 해야 합니다.&8;.  

### <a name="requirements"></a>요구 사항  
  **헤더** afxinet.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

