---
title: "CStdioFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile class
- I/O [MFC], stream
- stream I/O
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
caps.latest.revision: 22
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6b334c2973a2567a8a9bd16a80bd4c3628ced6d2
ms.lasthandoff: 04/01/2017

---
# <a name="cstdiofile-class"></a>CStdioFile 클래스
런타임 함수에서 연 것과 C 런타임 스트림 파일을 나타냅니다 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|생성 된 `CStdioFile` 경로 또는 파일 포인터의 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|오버로드됨. 열기는 기본 사용 하도록 설계 `CStdioFile` 생성자 (재정의 [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|한 줄 텍스트를 읽습니다.|  
|[CStdioFile::Seek](#seek)|현재 파일 포인터를 놓습니다.|  
|[CStdioFile::WriteString](#writestring)|한 줄 텍스트를 씁니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|열려 있는 파일에 대 한 포인터를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 스트림 버퍼링 되는 파일과 텍스트 모드 (기본값) 또는 이진 모드에서 열 수 있습니다.  
  
 텍스트 모드 캐리지 리턴-줄 바꿈 쌍에 대 한 특수 한 처리를 제공합니다. 줄 바꿈 문자를 작성 하는 경우 문자 (0x0A) 텍스트 모드를 `CStdioFile` 개체, 바이트 쌍 (, 0x0D 0x0A) 파일에 보내집니다. 읽을 때, 바이트 쌍 (, 0x0D 0x0A) 0x0A 싱글바이트도 변환 됩니다.  
  
 [CFile](../../mfc/reference/cfile-class.md) 함수 [중복](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), 및 [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) 에 지원 되지 않습니다 `CStdioFile`합니다.  
  
 이러한 함수를 호출 하는 경우는 `CStdioFile`를 얻게 됩니다는 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CStdioFile`, 문서를 참조 [MFC의 파일](../../mfc/files-in-mfc.md) 및 [파일 처리](../../c-runtime-library/file-handling.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="cstdiofile"></a>CStdioFile::CStdioFile  
 `CStdioFile` 개체를 생성하고 초기화합니다.  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>매개 변수  
 `pOpenStream`  
 C 런타임 함수에 대 한 호출에서 반환 된 파일 포인터를 지정 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)합니다.  
  
 `lpszFileName`  
 문자열을 원하는 파일의 경로를 지정 합니다. 상대 또는 절대 경로일 수 있습니다.  
  
 `nOpenFlags`  
 파일 만들기, 파일 공유 및 파일 액세스 모드에 대 한 옵션을 지정 합니다. 비트 OR를 사용 하 여 여러 옵션을 지정할 수 있습니다 ( `|`) 연산자.  
  
 한 파일 액세스 모드 옵션을 지정 해야 합니다. 다른 모드는 선택적입니다. 참조 [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) 모드 옵션 및 기타 플래그 목록은 합니다. Mfc 버전 3.0 이상에서 공유 플래그 허용 됩니다.  
  
 `pTM`  
 CAtlTransactionManager 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 기본 생성자는 파일을 연결 하지 않습니다는 `CStdioFile` 개체입니다. 이 생성자를 사용 하는 경우 사용 해야는 `CStdioFile::Open` 파일을 열에 연결 하는 메서드는 `CStdioFile` 개체입니다.  
  
 단일 매개 변수 생성자에는 열려 있는 파일 스트림을 연결의 `CStdioFile` 개체입니다. 미리 정의 된 입/출력 파일 포인터를 포함 하는 포인터 값을 허용 `stdin`, `stdout`, 또는 `stderr`합니다.  
  
 두 매개 변수 생성자 만듭니다는 `CStdioFile` 개체 하 고 지정된 된 경로와 해당 파일을 엽니다.  
  
 전달 하는 경우 `NULL` 중 하나에 대 한 `pOpenStream` 또는 `lpszFileName`, 생성자를 throw 한 `CInvalidArgException*`합니다.  
  
 생성자를 throw 하는 경우 파일을 열거나 만들 수 없습니다는 `CFileException*`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles # 37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="m_pstream"></a>CStdioFile::m_pStream  
 `m_pStream` C 런타임 함수에서 반환 된 데이터 멤버는 열려 있는 파일에 대 한 포인터 `fopen`합니다.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>주의  
 **NULL** 파일이 열어본 적 되거나 닫힌 경우.  
  
##  <a name="open"></a>CStdioFile::Open  
 오버로드됨. 열기는 기본 사용 하도록 설계 `CStdioFile` 생성자입니다.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CAtlTransactionManager* pTM,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 문자열은 원하는 파일을 경로입니다. 상대 또는 절대 경로일 수 있습니다.  
  
 `nOpenFlags`  
 공유 및 액세스 모드입니다. 파일을 열 때 수행할 동작을 지정 합니다. 비트 OR (|) 연산자를 사용 하 여 옵션을 결합할 수 있습니다. 에 대 한 액세스 권한 및 하나의 공유 옵션은 필수 사항이 고, modeCreate 및 modeNoInherit 모드는 선택적입니다.  
  
 `pError`  
 실패 한 작업의 상태를 수신할 기존 파일 예외 개체에 대 한 포인터입니다.  
  
 `pTM`  
 `CAtlTransactionManager` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="readstring"></a>CStdioFile::ReadString  
 텍스트 데이터의 제한의 버퍼로 읽어 `nMax`연결 된 파일에서-1 문자는 `CStdioFile` 개체입니다.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 사용자가 제공한 버퍼를 null로 끝나는 텍스트 문자열을 받게 됩니다에 대 한 포인터를 지정 합니다.  
  
 `nMax`  
 Null 종결 문자를 세 지 않고 읽기 문자의 최대 수를 지정 합니다.  
  
 `rString`  
 에 대 한 참조는 `CString` 함수에서 반환 된 문자열을 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 텍스트 데이터를 포함 하는 버퍼에 대 한 포인터입니다. **NULL** ; 모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다 아니면 부울, **FALSE** 경우 모든 데이터를 읽지 않고 파일의 끝에 도달 했습니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 줄 바꿈 문자 읽기 중지 됩니다. 보다 적은 경우 if `nMax`-1 문자를 읽은, 줄 바꿈 문자는 버퍼에 저장 됩니다. Null 문자 ('\0')는 두 경우 모두 추가 됩니다.  
  
 [CFile::Read](../../mfc/reference/cfile-class.md#read) 캐리지 리턴-줄 바꿈 쌍에 텍스트 모드 입력 하지만 종료 되지 않는 제공 됩니다.  
  
> [!NOTE]
>  `CString` 이 함수의 버전을 제거는 `'\n'` 있으면;는 `LPTSTR` 버전은 그렇지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles # 38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="seek"></a>CStdioFile::Seek  
 이전에 연된 파일에는 포인터 위치를 변경 합니다.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>매개 변수  
 `lOff`  
 포인터를 이동 하는 바이트 수입니다.  
  
 `nFrom`  
 포인터 이동 모드입니다. 다음 값 중 하나 여야 합니다.  
  
- `CFile::begin`: 파일 포인터를 이동 하는 `lOff` 파일의 시작 부분에서 바이트를 전달 합니다.  
  
- `CFile::current`: 파일 포인터를 이동 하는 `lOff` 파일의 현재 위치에서 바이트입니다.  
  
- `CFile::end`: 파일 포인터를 이동 하는 `lOff` 파일의 끝에서 바이트입니다. `lOff` 파일 되어 있어야 합니다 기존 검색 음수가; 양수 값은 파일의 끝을 지나서 검색 됩니다.  
  
### <a name="return-value"></a>반환 값  
 요청 된 위치가 법률, `Seek` 파일의 시작 부분에서 새 바이트 오프셋을 반환 합니다. 그렇지 않으면 반환 값이 정의 되지 및 `CFileException` 개체가 throw 됩니다.  
  
### <a name="remarks"></a>설명  
 `Seek` 함수를 사용 파일의 내용에 대 한 임의 액세스 포인터 이동 하 여 지정된 된 시간 또는 절대입니다. 검색 하는 동안 데이터가 실제로 읽힙니다. 요청된 된 위치는 파일의 크기 보다 큰 경우 해당 위치에 파일 길이 확장할 수는 있으며 예외가 throw 됩니다.  
  
 파일을 열 때 파일 포인터는 오프셋 0, 파일의 시작 부분에 배치 됩니다.  
  
 이 구현 `Seek` 런타임 라이브러리 (CRT) 기능에 따라 `fseek`합니다. 용도에 몇 가지 제한이 `Seek` 텍스트 모드에서 열린 스트림의에 있습니다. 자세한 내용은 참조 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `Seek` 의 시작 부분에서 1000 바이트 포인터를 이동 하는 `cfile` 파일입니다. `Seek` 호출 이후에 해야 하므로 데이터를 읽지 않습니다 [CStdioFile::ReadString](#readstring) 데이터를 읽을 수 있습니다.  
  
 [!code-cpp[NVC_MFCFiles # 39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="writestring"></a>CStdioFile::WriteString  
 연결 된 파일에는 버퍼에서 데이터를 쓰고는 `CStdioFile` 개체입니다.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 Null로 끝나는 문자열을 포함 하는 버퍼에 대 한 포인터를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 종료 null 문자 ( `\0`) 파일에 기록 되지 않습니다. 이 메서드는 줄 바꿈 문자를 씁니다 `lpsz` 캐리지 리턴/줄 바꿈 쌍으로 파일에 있습니다.  
  
 파일을 사용 하 여 null로 종결 되지 않은 데이터를 작성 하려는 경우 `CStdioFile::Write` 또는 [CFile::Write](../../mfc/reference/cfile-class.md#write)합니다.  
  
 이 메서드에서 throw 한 `CInvalidArgException*` 지정 하는 경우 `NULL` 에 대 한는 `lpsz` 매개 변수입니다.  
  
 이 메서드에서 throw 한 `CFileException*` 파일 시스템 오류에 대 한 응답에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles # 40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFile 클래스](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [CNotSupportedException 클래스](../../mfc/reference/cnotsupportedexception-class.md)

