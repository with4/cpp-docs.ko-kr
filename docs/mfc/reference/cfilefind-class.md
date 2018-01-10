---
title: "CFileFind 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs: C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e890e59896d1f69264ab479168385cf2a05d9fb7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cfilefind-class"></a>CFileFind 클래스
로컬 파일 검색을 수행 하 고는 기본 클래스에 대 한 [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) 및 [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), 인터넷 파일 검색을 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|`CFileFind` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileFind::Close](#close)|검색 요청을 종결 합니다.|  
|[CFileFind::FindFile](#findfile)|지정 된 파일 이름에 대 한 디렉터리를 검색합니다.|  
|[CFileFind::FindNextFile](#findnextfile)|파일 검색에 대 한 이전 호출에서 계속 [FindFile](#findfile)합니다.|  
|[CFileFind::GetCreationTime](#getcreationtime)|파일을 만든 시간을 가져옵니다.|  
|[CFileFind::GetFileName](#getfilename)|찾은 파일의 확장명을 포함 하는 이름을 가져옵니다.|  
|[CFileFind::GetFilePath](#getfilepath)|검색된 된 파일의 전체 경로 가져옵니다.|  
|[CFileFind::GetFileTitle](#getfiletitle)|검색된 된 파일의 제목을 가져옵니다. 제목에는 확장명은 포함 되지 않습니다.|  
|[CFileFind::GetFileURL](#getfileurl)|검색된 된 파일의 파일 경로 포함 하 여 URL을 가져옵니다.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|파일에 마지막으로 액세스 하는 시간을 가져옵니다.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|파일이 마지막 변경 되 고 저장 된 시간을 가져옵니다.|  
|[CFileFind::GetLength](#getlength)|찾은 파일을 바이트에서의 길이 가져옵니다.|  
|[CFileFind::GetRoot](#getroot)|검색된 된 파일의 루트 디렉터리를 가져옵니다.|  
|[CFileFind::IsArchived](#isarchived)|찾은 파일을 보관 하는 경우를 결정 합니다.|  
|[CFileFind::IsCompressed](#iscompressed)|찾은 파일을 압축 하는 경우를 결정 합니다.|  
|[CFileFind::IsDirectory](#isdirectory)|검색된 된 파일 디렉터리 인지 여부를 확인 합니다.|  
|[CFileFind::IsDots](#isdots)|검색된 된 파일의 이름을 이름 인지 여부를 결정 "."또는"..", 실제 디렉터리 했음을 나타냅니다.|  
|[CFileFind::IsHidden](#ishidden)|찾은 파일 숨겨져 있는지 확인 합니다.|  
|[CFileFind::IsNormal](#isnormal)|찾은 파일 정상 인지 여부를 확인 (즉, 다른 특성이 없는).|  
|[CFileFind::IsReadOnly](#isreadonly)|읽기 전용으로 검색된 된 파일 인지 여부를 확인 합니다.|  
|[CFileFind::IsSystem](#issystem)|검색된 된 파일 시스템 파일 인지 여부를 확인 합니다.|  
|[CFileFind::IsTemporary](#istemporary)|찾은 파일을 임시 인지 여부를 확인 합니다.|  
|[CFileFind::MatchesMask](#matchesmask)|파일을 검색 하려는 파일 특성을 나타냅니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|현재 검색 핸들로 지정한 파일을 닫습니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|`CAtlTransactionManager` 개체에 대한 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 `CFileFind`검색을 시작 하 고 파일을 찾은 제목, 이름 또는 파일의 경로 반환 하는 멤버 함수를 포함 합니다. 인터넷 검색, 멤버 함수에 대 한 [GetFileURL](#getfileurl) 파일의 URL을 반환 합니다.  
  
 `CFileFind`다른 두 개의 MFC 클래스에 대 한 기본 클래스 검색 하도록 특정 서버 유형을: `CGopherFileFind` gopher 서버도 작동 하 고 `CFtpFileFind` FTP 서버와 특히 작동 합니다. 함께 이러한 세 클래스는 서버 프로토콜, 파일 형식 또는 위치에 관계 없이 로컬 시스템 또는 원격 서버에서 파일을 찾으려면 클라이언트에 대 한 완벽 한 메커니즘을 제공 합니다.  
  
 다음 코드는 각 파일의 이름을 인쇄 현재 디렉터리의 모든 파일을 열거 합니다.  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 이 코드 예제를 단순하게 유지 하기 위해 c + + 표준 라이브러리는 사용 `cout` 클래스입니다. `cout` 줄을 호출 하 여 대체할 수 있습니다 `CListBox::AddString`, 예를 들어 그래픽 사용자 인터페이스를 사용 하 여 프로그램에 있습니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CFileFind` 다른 WinInet 클래스 문서를 참조 하 고 [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cfilefind"></a>CFileFind::CFileFind  
 이 멤버 함수를 호출 하는 경우는 `CFileFind` 개체가 만들어집니다.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTM`  
 CAtlTransactionManager 개체에 대한 포인터  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="close"></a>CFileFind::Close  
 검색 종료 컨텍스트를 다시 설정 하 고 모든 리소스를 해제 하려면이 멤버 함수를 호출 합니다.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>설명  
 호출한 후 **닫기**, 새 필요가 없습니다 `CFileFind` 호출 하기 전에 인스턴스 [FindFile](#findfile) 새 검색을 시작 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="closecontext"></a>CFileFind::CloseContext  
 현재 검색 핸들로 지정한 파일을 닫습니다.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>설명  
 검색 핸들의 현재 값으로 지정 된 파일을 닫습니다. 기본 동작을 변경 하려면이 함수를 재정의 합니다.  
  
 호출 해야 합니다는 [FindFile](#findfile) 또는 [FindNextFile](#findnextfile) 함수를 한 번 이상 유효한 검색 핸들을 가져올 수 있습니다. **FindFile** 및 `FindNextFile` 함수 이름이 지정 된 이름과 일치 하는 파일을 찾으려면 검색 핸들을 사용 합니다.  
  
##  <a name="findfile"></a>CFileFind::FindFile  
 파일 검색을 열려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstrName`  
 찾으려는 파일의 이름을 포함 하는 문자열에 대 한 포인터입니다. 전달 하는 경우 **NULL** 에 대 한 `pstrName`, **FindFile** 는 와일드 카드 (*.\*) 검색 합니다.  
  
 *dwUnused*  
 확인 하기 위해 예약 된 **FindFile** 파생된 클래스와 함께 다형 합니다. 0 이어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 가져올 확장 오류 정보를 Win32 함수 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.  
  
### <a name="remarks"></a>설명  
 호출한 후 **FindFile** 파일 검색을 시작 하려면 [FindNextFile](#findnextfile) 후속 파일을 검색 합니다. 호출 해야 `FindNextFile` 멤버 함수는 다음 특성 중 하나를 호출 하기 전에 한 번 이상:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem이](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::IsDirectory](#isdirectory)합니다.  
  
##  <a name="findnextfile"></a>CFileFind::FindNextFile  
 이전 호출에서 파일 검색을 계속 하려면이 함수를 호출 [FindFile](#findfile)합니다.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>반환 값  
 더 많은 파일이; 있을 경우 0이 아닌 파일을 찾을 수는 디렉터리에 마지막 않거나 오류가 발생 한 경우 0입니다. 가져올 확장 오류 정보를 Win32 함수 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다. 찾은 파일은 디렉터리에 마지막 파일 또는 일치 하는 경우 파일을 찾을 수, 하는 경우는 `GetLastError` ERROR_NO_MORE_FILES 함수를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 `FindNextFile` 멤버 함수는 다음 특성 중 하나를 호출 하기 전에 한 번 이상:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem이](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile`Win32 함수를 래핑합니다 [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428)합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::IsDirectory](#isdirectory)합니다.  
  
##  <a name="getcreationtime"></a>CFileFind::GetCreationTime  
 에 지정 된 파일을 만든 시간을 가져옵니다.이 함수를 호출 합니다.  
  
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
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetCreationTime`경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetCreationTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="getfilename"></a>CFileFind::GetFileName  
 검색된 된 파일의 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 가장 최근에 발견 파일의 이름입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) GetFileName 호출 하기 전에 한 번 이상.  
  
 `GetFileName`3 가지 `CFileFind` 특정 형식의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에서는 세 개의 및 달라 지도록 설명 합니다.  
  
- `GetFileName`확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 이름을 반환 `myfile.txt`합니다.  
  
- [GetFilePath](#getfilepath) 파일에 대 한 전체 경로 반환 합니다. 예를 들어 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 경로 반환 `c:\myhtml\myfile.txt`합니다.  
  
- [GetFileTitle](#getfiletitle) 파일 확장명 제외 하 고 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 제목 반환 `myfile`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>CFileFind::GetFilePath  
 지정된 된 파일의 전체 경로를 가져오지이 멤버 함수를 호출 합니다.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 지정된 된 파일의 경로입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFilePath`합니다.  
  
 `GetFilePath`3 가지 `CFileFind` 특정 형식의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에서는 세 개의 및 달라 지도록 설명 합니다.  
  
- [GetFileName](#getfilename) 확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 이름을 반환 `myfile.txt`합니다.  
  
- `GetFilePath`파일에 대 한 전체 경로 반환합니다. 예를 들어 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 경로 반환 `c:\myhtml\myfile.txt`합니다.  
  
- [GetFileTitle](#getfiletitle) 파일 확장명 제외 하 고 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 제목 반환 `myfile`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="getfiletitle"></a>CFileFind::GetFileTitle  
 이 멤버 함수는 발견된 된 파일의 제목을 가져옵니다를 호출 합니다.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 파일의 제목입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFileTitle`합니다.  
  
 `GetFileTitle`3 가지 `CFileFind` 특정 형식의 파일 이름 반환 하는 멤버 함수입니다. 다음 목록에서는 세 개의 및 달라 지도록 설명 합니다.  
  
- [GetFileName](#getfilename) 확장명을 포함 하는 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileName` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 이름을 반환 `myfile.txt`합니다.  
  
- [GetFilePath](#getfilepath) 파일에 대 한 전체 경로 반환 합니다. 예를 들어 호출 `GetFilePath` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 경로 반환 `c:\myhtml\myfile.txt`합니다.  
  
- `GetFileTitle`파일 확장명의 파일 이름을 반환 합니다. 예를 들어 호출 `GetFileTitle` 파일에 대 한 사용자 메시지를 생성 하 `c:\myhtml\myfile.txt` 파일 제목 반환 `myfile`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="getfileurl"></a>CFileFind::GetFileURL  
 지정된 된 URL을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>반환 값  
 전체 URL입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetFileURL`합니다.  
  
 `GetFileURL`멤버 함수에 유사한 [GetFilePath](#getfilepath)URL 형태로 반환 되는 점을 제외 하 고, `file://path`합니다. 예를 들어 호출 `GetFileURL` 에 대 한 전체 URL을 가져올 `myfile.txt` URL 반환 `file://c:\myhtml\myfile.txt`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime  
 에 지정된 된 파일에 마지막으로 액세스 하는 시간을 가져옵니다.이 함수를 호출 합니다.  
  
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
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetLastAccessTime`경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastAccessTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="getlastwritetime"></a>CFileFind::GetLastWriteTime  
 이 파일을 변경한 마지막 시간 가져온 함수를 호출 합니다.  
  
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
 성공 하면 0이 아닌 실패 한 경우 0입니다. `GetLastWriteTime`경우에 0이 반환 [FindNextFile](#findnextfile) 이 호출한 적 `CFileFind` 개체입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLastWriteTime`합니다.  
  
> [!NOTE]
>  일부 파일 시스템이이 함수에서 반환 된 타임 스탬프를 구현 하려면 동일한 의미 체계를 사용 합니다. 이 함수는 기본 파일 시스템 또는 서버에서 시간 특성을 유지 지원 하지 않으면 다른 타임 스탬프 함수에서 반환 되는 동일한 값을 반환할 수 있습니다. 참조는 [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) 시간 형식에 대 한 정보에 대 한 구조입니다. 일부 운영 체제에 반환 된 시간이 영역 로컬 컴퓨터에이 파일은 된 시간입니다. Win32 참조 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API에 대 한 자세한 내용은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="getlength"></a>CFileFind::GetLength  
 이 바이트에서 찾은 파일의 길이를 가져오는 함수를 호출 합니다.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 찾은 파일을 바이트에서의 길이입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetLength`합니다.  
  
 `GetLength`Win32 구조를 사용 하 여 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 을 가져오고 파일 크기의 값을 바이트 단위로 반환 합니다.  
  
> [!NOTE]
>  MFC 7.0부터 `GetLength` 64 비트 정수 형식을 지원 합니다. 이전에이 최신 버전의 라이브러리를 사용 하 여 작성 하는 기존 코드 잘림 경고가 발생할 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>CFileFind::GetRoot  
 이 검색된 된 파일의 루트를 가져올 함수를 호출 합니다.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>반환 값  
 활성 검색의 루트입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `GetRoot`합니다.  
  
 이 멤버 함수에 드라이브 지정자 및 검색을 시작 하는 데 사용 하는 경로 이름을 반환 합니다. 예를 들어 호출 [FindFile](#findfile) 와 `*.dat` 으로 인해 `GetRoot` 빈 문자열을 반환 합니다. 같은 경로 전달 `c:\windows\system\*.dll`을 **FindFile** 결과 `GetRoot` 반환 `c:\windows\system\`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetFileName](#getfilename)합니다.  
  
##  <a name="isarchived"></a>CFileFind::IsArchived  
 찾은 파일을 보관 하는 경우를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 백업 또는 FILE_ATTRIBUTE_ARCHIVE에서 식별 된 파일 특성을 함께 제거 하는 보관 파일을 표시 하는 응용 프로그램의 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsArchived`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="iscompressed"></a>CFileFind::IsCompressed  
 찾은 파일을 압축 하는 경우를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 압축된 된 파일은 FILE_ATTRIBUTE_COMPRESSED 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 파일의 경우이 특성의 모든 파일에 데이터 압축 되었음을 의미 합니다. 디렉터리의 경우이 특성 압축 새로 생성된 된 파일 및 하위 디렉터리에 대 한 기본 임을 나타냅니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsCompressed`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="isdirectory"></a>CFileFind::IsDirectory  
 검색된 된 파일 디렉터리 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 디렉터리에 파일이 FILE_ATTRIBUTE_DIRECTORY에서 식별 된 파일 특성으로 표시 됩니다는 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDirectory`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
 이 작은 프로그램 재귀 C:\ 드라이브에 모든 디렉터리와 디렉터리의 이름을 출력 합니다.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>CFileFind::IsDots  
 파일을 통해 반복 하는 동안 현재 디렉터리와 부모 디렉터리 표식에 대 한 테스트 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>반환 값  
 찾은 파일의 이름이 경우 0이 아닌 "."또는"..", 실제 디렉터리는 발견된 된 파일 임을 나타냅니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsDots`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::IsDirectory](#isdirectory)합니다.  
  
##  <a name="ishidden"></a>CFileFind::IsHidden  
 찾은 파일 숨겨져 있는지 확인 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 숨겨진된 파일을 FILE_ATTRIBUTE_HIDDEN로 표시 된에서 식별 된 파일 특성은 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 숨겨진된 파일 일반 디렉터리 목록에 포함 되지 않습니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsHidden`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="isnormal"></a>CFileFind::IsNormal  
 검색된 된 파일에 일반 파일 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 식별 된 FILE_ATTRIBUTE_NORMAL으로 표시 된 파일, 파일 특성은 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 일반 파일에 다른 특성 집합이 없습니다. 이 특성을 재정의 하는 다른 모든 파일 특성입니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsNormal`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="isreadonly"></a>CFileFind::IsReadOnly  
 찾은 파일은 읽기 전용 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 읽기 전용 파일은 FILE_ATTRIBUTE_READONLY 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 응용 프로그램이 이러한 파일을 읽을 수 있지만 쓸 하거나 삭제할 수는 없습니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsReadOnly`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="issystem"></a>CFileFind::IsSystem  
 검색된 된 파일 시스템 파일 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 시스템 파일은 FILE_ATTRIBUTE_SYSTEM, 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 시스템 파일의 일부 이거나 단독으로, 운영 체제에서 사용 됩니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsSystem`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="istemporary"></a>CFileFind::IsTemporary  
 임시 파일을 찾은 파일 인지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 임시 파일은 FILE_ATTRIBUTE_TEMPORARY 기본적으로, 파일 특성에서 식별 된 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 구조입니다. 임시 파일은 임시 저장에 사용 됩니다. 응용 프로그램은 반드시 필요한 경우에 파일에 작성 해야 합니다. 대부분의 데이터 파일의 파일은 삭제 곧 때문에 미디어에 플러시되고 있을 하지 않고 메모리에 남아 있습니다.  
  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `IsTemporary`합니다.  
  
 멤버 함수를 참조 하십시오. [MatchesMask](#matchesmask) 파일 특성의 전체 목록은 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CFileFind::GetLength](#getlength)합니다.  
  
##  <a name="m_ptm"></a>CFileFind::m_pTM  
 `CAtlTransactionManager` 개체에 대한 포인터입니다.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="matchesmask"></a>CFileFind::MatchesMask  
 검색된 된 파일의 파일 특성을 테스트 하려면이 함수를 호출 합니다.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwMask`  
 식별 된 하나 이상의 파일 특성을 지정 된 [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) 검색된 된 파일에 대 한 구조입니다. 여러 특성을 검색 하려면 비트 OR (&#124;)을 사용 하 여 연산자입니다. 다음 특성의 조합이 되어도:  
  
-   FILE_ATTRIBUTE_ARCHIVE 파일 보관 파일입니다. 응용 프로그램에 백업 또는 제거 하는 파일을 표시 하려면이 특성을 사용 합니다.  
  
-   파일 또는 디렉터리 FILE_ATTRIBUTE_COMPRESSED 압축 됩니다. 파일을 압축 파일에 데이터를 모두 의미 합니다. 디렉터리의 경우 새로 생성된 된 파일 및 하위 디렉터리에 대 한 기본 압축 임을 의미 합니다.  
  
-   FILE_ATTRIBUTE_DIRECTORY 파일 디렉터리입니다.  
  
-   FILE_ATTRIBUTE_NORMAL 파일에 다른 특성 집합이 없습니다. 이 특성은 단독으로 사용 하는 경우에 유효 합니다. 이 특성을 재정의 하는 다른 모든 파일 특성입니다.  
  
-   FILE_ATTRIBUTE_HIDDEN 파일은 숨겨집니다. 것은 원래 디렉터리 목록에 포함 될 수 없습니다.  
  
-   FILE_ATTRIBUTE_READONLY 파일이 읽기 전용입니다. 응용 프로그램 파일을 읽을 수 있지만 쓸 하거나 삭제할 수 없습니다.  
  
-   FILE_ATTRIBUTE_SYSTEM 파일의 일부 또는 운영 체제에서 독점적으로 사용 됩니다.  
  
-   임시 저장소 용 FILE_ATTRIBUTE_TEMPORARY 파일을 사용 중입니다. 응용 프로그램은 반드시 필요한 경우에 파일에 작성 해야 합니다. 대부분의 데이터 파일의 파일은 삭제 곧 때문에 미디어에 플러시되고 있을 하지 않고 메모리에 남아 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. 가져올 확장 오류 정보를 Win32 함수 호출 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)합니다.  
  
### <a name="remarks"></a>설명  
 호출 해야 [FindNextFile](#findnextfile) 호출 하기 전에 한 번 이상 `MatchesMask`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind 클래스](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind 클래스](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile 클래스](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile 클래스](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile 클래스](../../mfc/reference/chttpfile-class.md)
