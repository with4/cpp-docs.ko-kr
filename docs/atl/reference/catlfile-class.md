---
title: CAtlFile 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43ee71aae842ca7100f70af67cd8845d31e39a96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366109"
---
# <a name="catlfile-class"></a>CAtlFile 클래스
이 클래스는 파일 처리 API는 Windows에 대 한 씬 래퍼를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAtlFile : public CHandle
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](#catlfile)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFile::Create](#create)|만들거나 파일을 열이 메서드를 호출 합니다.|  
|[CAtlFile::Flush](#flush)|파일에 대 한 버퍼를 지우고 버퍼링 된 모든 데이터가 파일에 기록 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|파일에 대 한 중복 된 작업의 결과 얻기 위해이 메서드를 호출 합니다.|  
|[CAtlFile::GetPosition](#getposition)|파일에서 현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFile::GetSize](#getsize)|파일의 바이트 크기로 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFile::LockRange](#lockrange)|다른 프로세스에 액세스 하지 못하도록 파일에 영역을 잠그려는이 메서드를 호출 합니다.|  
|[CAtlFile::Read](#read)|파일 포인터에 의해 지정 된 위치에서 시작 하는 파일에서 데이터를 읽는이 메서드를 호출 합니다.|  
|[CAtlFile::Seek](#seek)|파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::SetSize](#setsize)|파일의 크기를 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::UnlockRange](#unlockrange)|파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::Write](#write)|파일 포인터에 의해 지정 된 위치에서 시작 하는 파일로 데이터를 기록 하려면이 메서드를 호출 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|에 대 한 포인터 `CAtlTransactionManager` 개체|  
  
## <a name="remarks"></a>설명  
 파일 처리 요구는 비교적 간단 하지만 MFC 종속성을 포함 하지 않고 Windows api를 사용 하는 것 보다 더 많은 추상화가 필요한 경우에이 클래스를 사용 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlfile.h  
  
##  <a name="catlfile"></a>  CAtlFile::CAtlFile  
 생성자입니다.  
  
```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `file`  
 파일 개체입니다.  
  
 `hFile`  
 파일 핸들입니다.  
  
 `pTM`  
 CAtlTransactionManager 개체에 대한 포인터  
  
### <a name="remarks"></a>설명  
 복사 생성자는 원래에서 파일 핸들의 소유권을 전송 `CAtlFile` 개체를 새로 생성 된 개체입니다.  
  
##  <a name="create"></a>  CAtlFile::Create  
 만들거나 파일을 열이 메서드를 호출 합니다.  
  
```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *szFilename*  
 파일 이름입니다.  
  
 `dwDesiredAccess`  
 원하는 액세스 합니다. 참조 `dwDesiredAccess` 에 [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) in the Windows SDK입니다.  
  
 `dwShareMode`  
 공유 모드입니다. 참조 `dwShareMode` 에 **CreateFile**합니다.  
  
 `dwCreationDisposition`  
 만들기 처리 합니다. 참조 `dwCreationDisposition` 에 **CreateFile**합니다.  
  
 `dwFlagsAndAttributes`  
 플래그 및 특성입니다. 참조 `dwFlagsAndAttributes` 에 **CreateFile**합니다.  
  
 `lpsa`  
 보안 특성입니다. 참조 *lpSecurityAttributes* 에 **CreateFile**합니다.  
  
 `hTemplateFile`  
 템플릿 파일입니다. 참조 `hTemplateFile` 에 **CreateFile**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858) 를 만들거나 파일을 엽니다.  
  
##  <a name="flush"></a>  CAtlFile::Flush  
 파일에 대 한 버퍼를 지우고 버퍼링 된 모든 데이터가 파일에 기록 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439) 버퍼링 된 데이터 파일을 플러시할 수 있습니다.  
  
##  <a name="getoverlappedresult"></a>  CAtlFile::GetOverlappedResult  
 파일에 대 한 중복 된 작업의 결과 얻기 위해이 메서드를 호출 합니다.  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pOverlapped`  
 Overlapped 구조체입니다. 참조 `lpOverlapped` 에 [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) in the Windows SDK입니다.  
  
 *dwBytesTransferred*  
 바이트를 전송 합니다. 참조 *lpNumberOfBytesTransferred* 에서 `GetOverlappedResult`합니다.  
  
 `bWait`  
 대기 옵션입니다. 참조 `bWait` 에서 `GetOverlappedResult`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209) 파일에 대 한 중복 된 작업의 결과를 가져옵니다.  
  
##  <a name="getposition"></a>  CAtlFile::GetPosition  
 현재 파일 포인터 위치를 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 바이트 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) 현재 파일 포인터 위치를 가져올 수 있습니다.  
  
##  <a name="getsize"></a>  CAtlFile::GetSize  
 파일의 바이트 크기로 가져오려면이 메서드를 호출 합니다.  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nLen`  
 파일의 바이트 수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955) 파일의 바이트의 크기를 가져올 수 있습니다.  
  
##  <a name="lockrange"></a>  CAtlFile::LockRange  
 다른 프로세스에 액세스 하지 못하도록 파일에 영역을 잠그려는이 메서드를 호출 합니다.  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 잠금을 시작 해야 하는 파일의 위치입니다.  
  
 `nCount`  
 바이트 범위를 잠글 수의 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [LockFile](http://msdn.microsoft.com/library/windows/desktop/aa365202) 파일에서 영역을 잠그려는 합니다. 파일의 바이트를 잠그면 다른 프로세스에서 해당 바이트에 액세스할 수 없습니다. 파일의 둘 이상의 영역을 잠글 수 있습니다 하지만 겹치는 지역이 없습니다. 허용 됩니다. 사용 하 여 영역, 잠금을 해제 하면 [CAtlFile::UnlockRange](#unlockrange), 바이트 범위 이전에 잠겨 있는 영역와 정확히 일치 해야 합니다. `LockRange` 인접 한 영역을 병합 하지 않습니다. 두 개의 잠긴된 영역을 인접 한 경우 잠금을 해제 해야 각각 별도로 합니다.  
  
##  <a name="m_ptm"></a>  CAtlFile::m_pTM  
 `CAtlTransactionManager` 개체에 대한 포인터입니다.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="read"></a>  CAtlFile::Read  
 파일 포인터에 의해 지정 된 위치에서 시작 하는 파일에서 데이터를 읽는이 메서드를 호출 합니다.  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pBuffer`  
 파일에서 읽은 데이터를 받을 버퍼에 대 한 포인터입니다.  
  
 `nBufSize`  
 버퍼 크기(바이트)입니다.  
  
 `nBytesRead`  
 읽은 바이트 수입니다.  
  
 `pOverlapped`  
 Overlapped 구조체입니다. 참조 `lpOverlapped` 에 [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467) in the Windows SDK입니다.  
  
 `pfnCompletionRoutine`  
 완료 루틴입니다. 참조 *lpCompletionRoutine* 에 [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 처음 세 개의 폼 호출 [ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467), 마지막 [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) 파일에서 데이터를 읽습니다. 사용 하 여 [CAtlFile::Seek](#seek) 파일 포인터를 이동 합니다.  
  
##  <a name="seek"></a>  CAtlFile::Seek  
 파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nOffset`  
 제공한 시작 지점부터 계산한 오프셋 `dwFrom`합니다.  
  
 `dwFrom`  
 시작 지점 (FILE_BEGIN, FILE_CURRENT, 또는 FILE_END)입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) 파일 포인터를 이동 합니다.  
  
##  <a name="setsize"></a>  CAtlFile::SetSize  
 파일의 크기를 설정 하려면이 메서드를 호출 합니다.  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewLen`  
 바이트에 있는 파일의 새 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541) 및 [SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531) 파일의 크기를 설정 합니다. 반환 시, 파일 포인터는 파일의 끝에 배치 됩니다.  
  
##  <a name="unlockrange"></a>  CAtlFile::UnlockRange  
 파일의 영역을 잠금 해제 하려면이 메서드를 호출 합니다.  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 잠금을 시작 해야 하는 파일의 위치입니다.  
  
 `nCount`  
 잠금 해제할 바이트 범위 길이입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 호출 [UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715) 영역 파일의 잠금을 해제 하도록 합니다.  
  
##  <a name="write"></a>  CAtlFile::Write  
 파일 포인터에 의해 지정 된 위치에서 시작 하는 파일로 데이터를 기록 하려면이 메서드를 호출 합니다.  
  
```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pBuffer`  
 데이터 파일에 쓸 수를 포함 하는 버퍼입니다.  
  
 `nBufSize`  
 버퍼에서 전송할 바이트 수입니다.  
  
 `pOverlapped`  
 Overlapped 구조체입니다. 참조 `lpOverlapped` 에 [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747) in the Windows SDK입니다.  
  
 `pfnCompletionRoutine`  
 완료 루틴입니다. 참조 *lpCompletionRoutine* 에 [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) Windows sdk에서입니다.  
  
 `pnBytesWritten`  
 쓸 바이트입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 또는 오류에 `HRESULT` 실패 합니다.  
  
### <a name="remarks"></a>설명  
 처음 세 개의 폼 호출 [WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747), 마지막 호출 [WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748) 데이터 파일에 쓰려고 합니다. 사용 하 여 [CAtlFile::Seek](#seek) 파일 포인터를 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [움직이는 텍스트 샘플](../../visual-cpp-samples.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CHandle 클래스](../../atl/reference/chandle-class.md)
