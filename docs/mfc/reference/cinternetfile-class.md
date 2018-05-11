---
title: CInternetFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60ee6e3d23dc197f7d8114f571bd121f864701d7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cinternetfile-class"></a>CInternetFile 클래스
인터넷 프로토콜을 사용 하는 원격 시스템에서 파일에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="protected-constructors"></a>Protected 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|`CInternetFile` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|모든 경고 및 오류를 무시 합니다. 파일을 닫습니다.|  
|[CInternetFile::Close](#close)|닫습니다는 `CInternetFile` 해당 리소스를 해제 합니다.|  
|[CInternetFile::Flush](#flush)|쓰기 버퍼의 내용을 플러시하고 하면 대상 컴퓨터에 데이터를 메모리에에서 기록 됩니다.|  
|[CInternetFile::GetLength](#getlength)|파일의 크기를 반환합니다.|  
|[Cinternetfile:: Read](#read)|지정 된 바이트 수를 읽습니다.|  
|[CInternetFile::ReadString](#readstring)|문자 스트림을 읽습니다.|  
|[CInternetFile::Seek](#seek)|열려 있는 파일에서 포인터 위치를 변경 합니다.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|데이터를 읽을 버퍼의 크기를 설정 합니다.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|데이터가 기록 될 버퍼의 크기를 설정 합니다.|  
|[CInternetFile::Write](#write)|지정 된 바이트 수를 기록 합니다.|  
|[CInternetFile::WriteString](#writestring)|파일에는 null로 끝나는 문자열을 씁니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|인터넷 핸들에 대 한 캐스팅 연산자입니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|파일에 대 한 핸들입니다.|  
  
## <a name="remarks"></a>설명  
 에 대 한 기본 클래스를 제공는 [CHttpFile](../../mfc/reference/chttpfile-class.md) 및 [CGopherFile](../../mfc/reference/cgopherfile-class.md) 파일 클래스입니다. 만들지 마십시오는 `CInternetFile` 개체를 직접 합니다. 대신, 호출 하 여 클래스의 파생된 클래스 중 하나의 개체를 만들 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 또는 [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)합니다. 만들 수도 있습니다는 `CInternetFile` 호출 하 여 개체 [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)합니다.  
  
 `CInternetFile` 멤버 함수 **열려**, `LockRange`, `UnlockRange`, 및 `Duplicate` 에 대 한 구현 되지 않은 `CInternetFile`합니다. 이러한 함수를 호출 하는 경우는 `CInternetFile` 개체를 얻게 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 방법에 대 한 자세한 내용을 보려면 `CInternetFile` 작동 하는 다른 MFC 인터넷 클래스 문서를 참조 하십시오. [인터넷 WinInet를 사용한 프로그래밍](../../mfc/win32-internet-extensions-wininet.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxinet.h  
  
##  <a name="abort"></a>  CInternetFile::Abort  
 이 개체와 연결 된 파일을 닫고 파일을 읽거나 쓰기 위해 사용할 수 없게 하 게 합니다.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>설명  
 개체를 제거 하기 전에 파일을 닫지 않은 경우 소멸자를 닫습니다.  
  
 예외를 처리 하는 경우 **중단** 에서 다른 [닫기](#close) 같은 두 가지 중요 한 차이점이 있습니다. 첫째, 고 **중단** 함수는 예외를 throw 하지 오류에 오류를 무시 하기 때문에 있습니다. 두 번째, **중단** 없는 **ASSERT** 파일이 열려 있지 않은 되거나 이전에 종결 된 경우.  
  
##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile  
 이 멤버 함수를 호출 하는 경우는 `CInternetFile` 개체가 만들어집니다.  
  
```  
CInternetFile(
    HINTERNET hFile,  
    LPCTSTR pstrFileName,  
    CInternetConnection* pConnection,  
    BOOL bReadMode);

 
CInternetFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrFileName,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext,  
    BOOL bReadMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `hFile`  
 인터넷 파일에 대 한 핸들입니다.  
  
 `pstrFileName`  
 파일 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `pConnection`  
 에 대 한 포인터는 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) 개체입니다.  
  
 *bReadMode*  
 파일이 읽기 전용인 지 여부를 나타냅니다.  
  
 `hSession`  
 인터넷 세션에 대 한 핸들입니다.  
  
 `pstrServer`  
 서버 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
 `dwContext`  
 에 대 한 컨텍스트 식별자는 `CInternetFile` 개체입니다. 참조 [WinInet 기본 사항](../../mfc/wininet-basics.md) 컨텍스트 식별자에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>설명  
 만들지 마십시오는 `CInternetFile` 개체를 직접 합니다. 대신, 호출 하 여 클래스의 파생된 클래스 중 하나의 개체를 만들 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) 또는 [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)합니다. 만들 수도 있습니다는 `CInternetFile` 호출 하 여 개체 [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)합니다.  
  
##  <a name="close"></a>  CInternetFile::Close  
 닫습니다는 `CInternetFile` 하 고 해당 리소스가 해제 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>설명  
 파일을 쓰기 위해 연, 경우에 대 한 암시적 호출 [플러시](#flush) 버퍼링 된 모든 데이터를 호스트에 기록 됩니다. 호출 해야 **닫기** 했으면 파일을 사용 하 여 완료 합니다.  
  
##  <a name="flush"></a>  CInternetFile::Flush  
 쓰기 버퍼의 내용을 플러시를이 멤버 함수를 호출 합니다.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>설명  
 사용 하 여 `Flush` 대상 컴퓨터에 메모리에 모든 데이터는 실제로 기록 하 고 호스트 컴퓨터와 사용자 트랜잭션이 완료 되도록 합니다. `Flush` 에 유효 `CInternetFile` 쓰기용으로 열 개체입니다.  
  
##  <a name="getlength"></a>  CInternetFile::GetLength  
 파일의 크기를 반환합니다.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>  CInternetFile::m_hFile  
 이 개체와 연결 된 파일에 대 한 핸들입니다.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET  
 이 연산자를 사용 하 여 현재 인터넷 세션에 대 한 Windows 핸들을 가져올 수 있습니다.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>  Cinternetfile:: Read  
 `lpvBuf`부터 시작하여 지정된 바이트 수 `nCount`를 지정된 메모리로 읽으려면 이 멤버 함수를 호출합니다.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 파일 데이터를 읽을 메모리 주소에 대한 포인터입니다.  
  
 `nCount`  
 쓸 바이트 수 입니다.  
  
### <a name="return-value"></a>반환 값  
 버퍼로 전송된 바이트 수입니다. 파일의 끝에 도달한 경우 반환 값은 `nCount`보다 작을 수 있습니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 실제로 읽는 바이트 수를 반환합니다(파일의 끝에 도달한 경우 `nCount`보다 작을 수 있음). 이 함수가 throw 하는 파일을 읽는 동안 오류가 발생 하는 경우는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다. 파일의 끝을 지나서 읽는 것은 오류로 간주되지 않으며 예외가 throw되지 않습니다.  
  
 데이터를 모두 검색 하려면 응용 프로그램 계속 호출 해야는 **cinternetfile:: Read** 메서드에서 0을 반환할 때까지 메서드.  
  
##  <a name="readstring"></a>  CInternetFile::ReadString  
 줄 바꿈 문자를 찾을 때까지 문자 스트림을 읽는 데이 함수를 호출 합니다.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstr`  
 읽는 중인 줄을 수신할 문자열에 대 한 포인터입니다.  
  
 `nMax`  
 문자를 읽을 수는 최대 수입니다.  
  
 `rString`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 읽기 줄을 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 검색 된 일반 데이터를 포함 하는 버퍼에 대 한 포인터는 [CInternetFile](../../mfc/reference/cinternetfile-class.md) 개체입니다. 이 메서드에 전달 된 버퍼의 데이터 형식에 상관 없이 데이터 (예를 들어 유니코드로 변환)에 대해 모든 조작을 수행 하지 않습니다, 반환 되는 데이터 구조에 매핑해야 하므로 예상 되는 경우 처럼는 **void\***  형식이 반환 되었습니다.  
  
 **NULL** ; 모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다 경우 나 경우 부울, **FALSE** 경우 모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다.  
  
### <a name="remarks"></a>설명  
 함수에서 참조 되는 메모리에 결과 선을 배치는 `pstr` 매개 변수입니다. 문자 읽기 중지 지정 된 문자의 최대 수에 도달한 경우 `nMax`합니다. 버퍼는 항상 종료 null 문자를 받습니다.  
  
 호출 하는 경우 `ReadString` 먼저 호출 하지 않고 [SetReadBufferSize](#setreadbuffersize), 4, 096 바이트의 버퍼를 받게 됩니다.  
  
##  <a name="seek"></a>  CInternetFile::Seek  
 이전에 연된 파일에서 포인터 위치를 변경 하려면이 함수를 호출 합니다.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>매개 변수  
 `lOffset`  
 파일에서 읽기/쓰기 포인터를 이동 하는 바이트에서 오프셋입니다.  
  
 `nFrom`  
 오프셋에 대 한 상대 참조 합니다. 다음 값 중 하나 여야 합니다.  
  
- **CFile::begin** 파일 포인터를 이동 `lOff` 파일의 시작 부분에서 바이트를 전달 합니다.  
  
- **CFile::current** 파일 포인터를 이동 `lOff` 파일의 현재 위치에서 바이트입니다.  
  
- **CFile::end** 파일 포인터를 이동 `lOff` 파일의 끝에서 바이트입니다. `lOff` 기존 파일을 음수 여야 합니다. 파일의 끝을 지나서 양수 값 검색 됩니다.  
  
### <a name="return-value"></a>반환 값  
 요청 된 위치가 법적; 파일의 시작 부분에서 5 만큼 오프셋 새 바이트 그렇지 않으면 값은 정의 되지 및 [CInternetException](../../mfc/reference/cinternetexception-class.md) 개체가 throw 됩니다.  
  
### <a name="remarks"></a>설명  
 `Seek` 함수를 사용 파일의 내용에 대 한 임의 액세스는 포인터를 이동 하 여 지정된 된 시간 또는 절대입니다. 검색 하는 동안 데이터가 실제로 읽힙니다.  
  
 이때이 멤버 함수에 대 한 호출에만 지원 됩니다와 관련 된 데이터 `CHttpFile` 개체입니다. FTP 또는 gopher 요청에 대해 지원 되지 않습니다. 호출 하는 경우 `Seek` 지원 되지 않는 이러한 서비스 중 하나에 대 한 통과 하 게 다시 있습니다 Win32 오류 코드를 **ERROR_INTERNET_INVALID_OPERATION**합니다.  
  
 파일을 열 때 파일 포인터가 파일의 시작 오프셋 0에서 합니다.  
  
> [!NOTE]
>  사용 하 여 `Seek` 암시적으로 호출 않을 [플러시](#flush)합니다.  
  
### <a name="example"></a>예제  
  기본 클래스 구현에 대 한 예제를 참조 하십시오 ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize  
 사용 하는 임시 읽기 버퍼의 크기를 설정 하려면이 함수를 호출는 `CInternetFile`-파생 된 개체입니다.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *nReadSize*  
 원하는 버퍼 크기(바이트)입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 기본 WinInet Api 아무 버퍼링을 수행 하지, 따라서 응용 프로그램을 효율적으로 데이터를 읽을 수와 관계 없이 데이터를 읽을 수 있는 버퍼 크기를 선택 합니다. 호출할 때마다 경우 [읽기](#read) 일반적으로 큰 aount 포함 됩니다 (예: 4 개 이상의 킬로바이트) 데이터의 필요 하면 버퍼입니다. 그러나 호출 하는 경우 **읽기** 적은 양의 데이터를 가져오려는 사용 하는 경우 또는 [ReadString](#readstring) 읽기 버퍼 응용 프로그램 성능을 개선 한 후 한 번에 개별 줄을 읽을 수 있습니다.  
  
 기본적으로는 `CInternetFile` 개체 읽기에 대 한 버퍼링을 제공 하지 않습니다. 이 함수를 호출 하는 경우에 파일 읽기 액세스를 위해 열린 있는지 확인 해야 합니다.  
  
 언제 든 지 버퍼 크기를 늘릴 수 있지만 버퍼 축소 아무런 효과가 없습니다. 호출 하는 경우 [ReadString](#readstring) 먼저 호출 하지 않고 `SetReadBufferSize`, 4, 096 바이트의 버퍼를 받게 됩니다.  
  
##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize  
 사용 하는 임시 쓰기 버퍼의 크기를 설정 하려면이 함수를 호출는 `CInternetFile`-파생 된 개체입니다.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>매개 변수  
 *nWriteSize*  
 버퍼의 크기(바이트)입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다. Win32 함수 호출이 실패 한 경우 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) 오류의 원인을 확인 하기 위해 호출할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 WinInet Api 버퍼링을 수행 하지 않는 기본 응용 프로그램을 효율적으로 데이터를 쓸 수의 크기에 관계 없이 데이터를 쓸 수 있는 버퍼 크기를 선택 합니다. 호출할 때마다 경우 [작성](#write) 일반적으로 많은 양의 포함 됩니다 (예를 들어, 한 번에 4 개 이상의 킬로바이트) 데이터의 필요 하면 버퍼입니다. 그러나 호출 하는 경우 [쓰기](#write) 쓰기 버퍼 적은 양의 데이터를 작성 하려면 응용 프로그램의 성능이 향상 됩니다.  
  
 기본적으로는 `CInternetFile` 개체 쓰기에 대 한 버퍼링을 제공 하지 않습니다. 이 함수를 호출 하는 경우에 쓰기 액세스를 위해는 파일이 열려 있는지 확인 해야 합니다. 언제 든 지 쓰기 버퍼의 크기를 변경할 수 있지만, 이렇게 할 암시적으로 호출 [플러시](#flush)합니다.  
  
##  <a name="write"></a>  CInternetFile::Write  
 이 멤버 함수는 지정 된 메모리에 쓸 호출 `lpvBuf`, 바이트 수를 지정 된 `nCount`합니다.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 쓸 첫 번째 바이트에 대 한 포인터입니다.  
  
 `nCount`  
 쓸 바이트 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수가 throw 하는 데이터를 작성 하는 동안 오류가 발생 하는 경우는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다.  
  
##  <a name="writestring"></a>  CInternetFile::WriteString  
 이 함수는 관련된 파일에는 null로 끝나는 문자열을 씁니다.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>매개 변수  
 `pstr`  
 쓸 콘텐츠를 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수가 throw 하는 데이터를 작성 하는 동안 오류가 발생 하는 경우는 [CInternetException](../../mfc/reference/cinternetexception-class.md) 오류를 설명 하는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStdioFile 클래스](../../mfc/reference/cstdiofile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CInternetConnection 클래스](../../mfc/reference/cinternetconnection-class.md)
