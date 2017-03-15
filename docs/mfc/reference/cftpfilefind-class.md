---
title: "CFtpFileFind 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpFileFind
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind class
- file searches [C++]
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e84282cc2f22e813ea44318d497c7e32e3280d8
ms.lasthandoff: 02/24/2017

---
# <a name="cftpfilefind-class"></a>CFtpFileFind 클래스
FTP 서버의 인터넷 파일 검색에 유용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|`CFtpFileFind` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Cftpfilefind:: Findfile](#findfile)|FTP 서버에서 파일을 찾습니다.|  
|[Cftpfilefind:: Findnextfile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|  
|[CFtpFileFind::GetFileURL](#getfileurl)|검색된 된 파일의 경로 포함 하는 URL을 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 `CFtpFileFind`검색을 시작 하 고 파일을 찾은 URL 또는 파일에 대 한 기타 설명 정보를 반환 하는 멤버 함수를 포함 합니다.  
  
 인터넷 및 검색 하는 로컬 파일을 포함 하도록 설계 되었으며 다른 MFC 클래스 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및 [CFileFind](../../mfc/reference/cfilefind-class.md)합니다. 와 함께 `CFtpFileFind`, 이러한 클래스 프로토콜 또는 파일 형식 (로컬 컴퓨터 또는 원격 서버) 서버에 관계 없이 특정 파일을 찾으려고 클라이언트에 대 한 완벽 한 메커니즘을 제공 합니다. HTTP 검색에 필요한 파일을 직접 조작을 지원 하지 않기 때문에 HTTP 서버에서 검색을 위한 MFC 클래스 없음 않음을 유의 하십시오.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFtpFileFind` 다른 WinInet 클래스 문서를 참조 하 고 [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 FTP 서버의 현재 디렉터리의 모든 파일을 열거 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCWinInet #&8;](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="a-namecftpfilefinda--cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 이 멤버 함수를 생성 하 라고는 `CFtpFileFind` 개체입니다.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `pConnection`  
 에 대 한 포인터는 `CFtpConnection` 개체입니다. 호출 하 여 FTP 연결을 가져올 수 있습니다 [cinternetsession:: Getftpconnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)합니다.  
  
 `dwContext`  
 에 대 한 컨텍스트 식별자는 `CFtpFileFind` 개체입니다. 참조 **주의** 이 매개 변수에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>주의  
 기본값 `dwContext` MFC를 통해 보내집니다는 `CFtpFileFind` 에서 개체는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 `CFtpFileFind` 개체입니다. 선택한 값으로 컨텍스트 식별자를 설정 하기 위해 기본값을 재정의할 수 있습니다. 컨텍스트 식별자에 반환 됩니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체에 대 한 상태에 있습니다. 문서를 참조 하십시오 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예제  
  이 항목의 앞부분에 나오는 클래스 개요에서 예제를 참조 하십시오.  
  
##  <a name="a-namefindfilea--cftpfilefindfindfile"></a><a name="findfile"></a>Cftpfilefind:: Findfile  
 FTP 파일을 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrName`  
 찾으려는 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다. 경우 **NULL**, 호출 (*) 와일드 카드 검색을 수행 합니다.  
  
 `dwFlags`  
 이 세션을 처리 하는 방법을 설명 하는 플래그입니다. 이러한 플래그 비트 OR 연산자 (|)와 함께 사용할 수 있습니다 되며 다음과 같습니다.  
  
-   INTERNET_FLAG_RELOAD 로컬에 캐시 되는 경우에 네트워크에서 데이터를 가져옵니다. 이것이 기본 플래그입니다.  
  
-   로컬 또는 모든 게이트웨이에 데이터를 캐시 하지 INTERNET_FLAG_DONT_CACHE 않습니다.  
  
-   원시 데이터를 반환 하는 기본값을 재정의 하는 INTERNET_FLAG_RAW_DATA ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) FTP에 대 한 구조).  
  
-   Secure Sockets Layer 또는 PCT. 통신 중에 트랜잭션을 INTERNET_FLAG_SECURE 보호 이 플래그는 HTTP 요청에 적용 됩니다.  
  
-   가능 하다 면 INTERNET_FLAG_EXISTING_CONNECT 새 서버에 대 한 기존 연결을 재사용 **FindFile** 각 요청에 대해 새 세션을 만드는 대신 요청 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 가져오기 오류 정보를 확장 하려면 Win32 함수를 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.  
  
### <a name="remarks"></a>주의  
 호출한 후 **FindFile** 호출할 수 있는 첫 번째 FTP 파일을 검색 하려면 [FindNextFile](#findnextfile) 후속 FTP 파일을 검색 합니다.  
  
### <a name="example"></a>예제  
  이 항목의 이전 예제를 참조 하십시오.  
  
##  <a name="a-namefindnextfilea--cftpfilefindfindnextfile"></a><a name="findnextfile"></a>Cftpfilefind:: Findnextfile  
 에 대 한 호출을 시작한 파일 검색을 계속 하려면이 멤버 함수를 호출 하는 [FindFile](#findfile) 멤버 함수입니다.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>반환 값  
 더 많은 파일; 없으면&0;이 아닌 파일을 찾을 수는 디렉터리에 마지막 않거나 오류가 발생 한 경우&0;입니다. 가져오기 오류 정보를 확장 하려면 Win32 함수를 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다. 찾은 파일 디렉터리에 마지막 파일 이거나 일치 하는 경우에 파일을 찾을 수 있습니다, 경우는 `GetLastError` ERROR_NO_MORE_FILES 함수를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 특성 함수를 호출 하기 전에 최소한 한 번이 함수를 호출 해야 합니다 (참조 [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`Win32 함수를 래핑합니다 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)합니다.  
  
### <a name="example"></a>예제  
  이 항목의 앞부분에 나오는 예제를 참조 하십시오.  
  
##  <a name="a-namegetfileurla--cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 지정된 된 파일의 URL을 가져오고이 멤버 함수를 호출 합니다.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 범용 리소스 Locator (URL)의 경로 파일입니다.  
  
### <a name="remarks"></a>주의  
 `GetFileURL`멤버 함수와 비슷합니다 [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)형식에서 URL을 반환 한다는 점을 제외 하면, `ftp://moose/dir/file.txt`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFileFind 클래스](../../mfc/reference/cfilefind-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)

