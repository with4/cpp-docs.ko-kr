---
title: CGopherFileFind 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 584644963a647c5b458407b2d777f91014b40fad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind 클래스
Gopher 서버의 인터넷 파일 검색에 유용합니다.  
  
> [!NOTE]
>  클래스 `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` 및 해당 멤버 사용이 중단 된 Windows XP 플랫폼에서 작동 하지 않음 되었지만 이전 버전의 플랫폼에서 실행 되도록 계속 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|`CGopherFileFind` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|Gopher 서버에서 파일을 찾습니다.|  
|[CGopherFileFind::FindNextFile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|지정 된 파일을 만든 시간을 가져옵니다.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|지정된 된 파일에 마지막으로 액세스 한 시간을 가져옵니다.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|지정된 된 파일에 마지막으로 쓴 시간을 가져옵니다.|  
|[CGopherFileFind::GetLength](#getlength)|찾은 파일을 바이트에서의 길이 가져옵니다.|  
|[CGopherFileFind::GetLocator](#getlocator)|가져오기는 `CGopherLocator` 개체입니다.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Gopher 화면 이름을 가져옵니다.|  
|[CGopherFileFind::IsDots](#isdots)|파일을 통해 반복 하는 동안 현재 디렉터리와 부모 디렉터리 표식에 대 한 테스트 합니다.|  
  
## <a name="remarks"></a>설명  
 `CGopherFileFind` 검색을 시작 하 고 파일을 찾은 파일의 URL을 반환 하는 멤버 함수를 포함 합니다.  
  
 다른 MFC 클래스에 인터넷 및 검색 하는 로컬 파일이 포함 되어 디자인 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) 및 [CFileFind](../../mfc/reference/cfilefind-class.md)합니다. 와 함께 `CGopherFileFind`, 서버 프로토콜, 파일 형식 또는 위치 (로컬 컴퓨터 또는 원격 서버입니다.)에 관계 없이 특정 파일을 찾을 수 사용자에 대 한 완벽 한 메커니즘을 제공 하는 이러한 클래스 HTTP 검색에 필요한 파일을 직접 조작을 지원 하지 않기 때문에 HTTP 서버에 대 한 검색에 대 한 없는 MFC 클래스 있다는 것을 참고 합니다.  
  
> [!NOTE]
> `CGopherFileFind` 기본 클래스의 다음 멤버 함수를 지원 하지 않는 [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 또한와 함께 사용할 경우 `CGopherFileFind`, `CFileFind` 멤버 함수 [IsDots](../../mfc/reference/cfilefind-class.md#isdots) 항상 **FALSE**합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CGopherFileFind` 다른 WinInet 클래스 문서를 참조 하 고 [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind  
 이 멤버 함수를 생성 하 라고 하는 `CGopherFileFind` 개체입니다.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>매개 변수  
 `pConnection`  
 에 대 한 포인터는 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) 개체입니다.  
  
 `dwContext`  
 작업에 대 한 컨텍스트 식별자입니다. 참조 **주의** 에 대 한 자세한 내용은 `dwContext`합니다.  
  
### <a name="remarks"></a>설명  
 에 대 한 기본값 `dwContext` MFC 인증에서 전송 되는 `CGopherFileFind` 에서 개체는 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 만든 개체는 `CGopherFileFind` 개체입니다. 생성할 때는 `CGopherFileFind` 개체 컨텍스트 식별자의 값으로 설정 하기 위해 기본값을 재정의할 수 있습니다. 컨텍스트 식별자는 되돌아갑니다 [cinternetsession:: Onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) 식별 되는 개체의 상태를 제공 하 합니다. 문서 참조 [인터넷 첫 번째 단계: WinInet](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
##  <a name="findfile"></a>  CGopherFileFind::FindFile  
 Gopher 파일을 찾기 위해이 함수를 호출 합니다.  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>매개 변수  
 `refLocator`  
 에 대 한 참조는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체입니다.  
  
 *pstrString*  
 파일 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwFlags`  
 이 세션을 처리 하는 방법을 설명 하는 플래그입니다. 유효한 플래그는:  
  
-   INTERNET_FLAG_RELOAD 로컬로 캐시 된 경우에 원격 서버에서 데이터를 가져옵니다.  
  
-   로컬 또는 게이트웨이 모두에서 데이터를 캐시 하지 INTERNET_FLAG_DONT_CACHE 않습니다.  
  
-   Secure Sockets Layer 또는 PCT. 통신 중에 보안 트랜잭션을 INTERNET_FLAG_SECURE 요청 이 플래그는 HTTP 요청에 적용할 수 있습니다.  
  
-   가능 하다 면 INTERNET_FLAG_USE_EXISTING에 새 서버에 대 한 기존 연결을 다시 사용 **FindFile** 각 요청에 대 한 새 세션을 만드는 대신 요청 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 가져올 확장 오류 정보를 Win32 함수 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.  
  
### <a name="remarks"></a>설명  
 호출한 후 **FindFile** 개체를 가져와 첫 번째 gopher를 호출할 수 있습니다 [FindNextFile](#findnextfile) 후속 gopher 파일을 검색 합니다.  
  
##  <a name="findnextfile"></a>  CGopherFileFind::FindNextFile  
 에 대 한 호출을 시작한 파일 검색을 계속 하려면이 함수를 호출 [CGopherFileFind::FindFile](#findfile)합니다.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>반환 값  
 더 많은 파일이; 있을 경우 0이 아닌 파일을 찾을 수는 디렉터리에 마지막 않거나 오류가 발생 한 경우 0입니다. 가져올 확장 오류 정보를 Win32 함수 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다. 찾은 파일은 디렉터리에 마지막 파일 또는 일치 하는 경우 파일을 찾을 수, 하는 경우는 `GetLastError` ERROR_NO_MORE_FILES 함수를 반환 합니다.  
  
##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime  
 현재 파일에 대 한 생성 시간을 가져옵니다.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pTimeStamp`  
 에 대 한 포인터는 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 파일을 만든 시간을 포함 하는 구조입니다.  
  
 `refTime`  
 에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetCreationTime` 경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetCreationTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime  
 지정된 된 파일에 마지막으로 액세스 한 시간을 가져옵니다.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `refTime`  
 에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.  
  
 `pTimeStamp`  
 에 대 한 포인터는 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 파일에 마지막으로 액세스 한 시간을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetLastAccessTime` 경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastAccessTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime  
 파일을 변경한 마지막 시간을 가져옵니다.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pTimeStamp`  
 에 대 한 포인터는 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 파일에 마지막으로 쓴 시간을 포함 하는 구조입니다.  
  
 `refTime`  
 에 대 한 참조는 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetLastWriteTime` 경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CGopherFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastWriteTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에서 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
##  <a name="getlength"></a>  CGopherFileFind::GetLength  
 검색된 된 파일의 바이트의 길이 가져오려면이 함수를 호출 합니다.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 검색된 된 파일의 길이 (바이트)를 합니다.  
  
### <a name="remarks"></a>설명  
 `GetLength` Win32 구조를 사용 하 여 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 값을 가져올 파일의 크기 (바이트)에서입니다.  
  
> [!NOTE]
>  MFC 7.0부터 `GetLength` 64 비트 정수 형식을 지원 합니다. 라이브러리의이 최신 버전으로 작성 된 기존 코드 잘림 경고가 발생할 수 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (기본 클래스 구현)입니다.  
  
##  <a name="getlocator"></a>  CGopherFileFind::GetLocator  
 멤버 가져오려면이 함수를 호출 하는 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) 개체를 [FindFile](#findfile) gopher 파일을 찾기 위해 사용 합니다.  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `CGopherLocator` 개체입니다.  
  
##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName  
 Gopher 화면의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Gopher 화면의 이름입니다.  
  
##  <a name="isdots"></a>  CGopherFileFind::IsDots  
 파일을 통해 반복 하는 동안 현재 디렉터리와 부모 디렉터리 표식에 대 한 테스트 합니다.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>반환 값  
 찾은 파일의 이름이 경우 0이 아닌 "."또는"..", 실제 디렉터리는 발견된 된 파일 임을 나타냅니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDots`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFileFind 클래스](../../mfc/reference/cfilefind-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind 클래스](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind 클래스](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
