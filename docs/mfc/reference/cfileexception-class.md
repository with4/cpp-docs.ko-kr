---
title: "CFileException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileException
dev_langs:
- C++
helpviewer_keywords:
- CFile class, exceptions of
- exceptions, file type
- CFileException class
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
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
ms.openlocfilehash: d9064ae66f0dcd0e9f0dce0eedd8e38353f9da06
ms.lasthandoff: 02/24/2017

---
# <a name="cfileexception-class"></a>CFileException 클래스
파일 관련 예외 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|`CFileException` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|반환 될 런타임 오류 번호에 해당 하는 코드입니다.|  
|[CFileException::GetErrorMessage](#geterrormessage)|예외를 설명 하는 메시지를 검색 합니다.|  
|[CFileException::OsErrorToException](#oserrortoexception)|운영 체제 오류 코드에 해당 하는 이유 코드를 반환 합니다.|  
|[CFileException::ThrowErrno](#throwerrno)|런타임 오류 번호에 따라 파일 예외를 throw 합니다.|  
|[CFileException::ThrowOsError](#throwoserror)|운영 체제 오류 번호에 따라 파일 예외를 throw 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CFileException::m_cause](#m_cause)|예외 원인에 해당 하는 이식 가능한 코드를 포함 합니다.|  
|[CFileException::m_lOsError](#m_loserror)|관련된 운영 체제 오류 번호가 있습니다.|  
|[CFileException::m_strFileName](#m_strfilename)|이 예외에 대 한 파일의 이름을 포함합니다.|  
  
## <a name="remarks"></a>주의  
 `CFileException` 클래스는 이식 가능한 이유 코드 및 운영 체제별 오류 번호를 보유 하는 공용 데이터 멤버를 포함 합니다. 클래스는 또한 파일 예외를 throw 하 고 운영 체제 오류와 C 런타임 오류에 대 한 원인은 코드를 반환 하기 위한 정적 멤버 함수를 제공 합니다.  
  
 `CFileException`개체를 생성 하 고 throw `CFile` 멤버 함수 및 파생 된 클래스의 멤버 함수입니다. 범위 내에서 이러한 개체를 액세스할 수는 **CATCH** 식입니다. 이식성을 위하여 원인 코드에만 사용 하 여 예외에 대 한 이유를 가져옵니다. 예외에 대 한 자세한 내용은 문서를 참조 하십시오. [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="a-namecfileexceptiona--cfileexceptioncfileexception"></a><a name="cfileexception"></a>CFileException::CFileException  
 생성 된 `CFileException` 원인 코드와 운영 체제 코드 개체에 저장 하는 개체입니다.  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `cause`  
 예외에 대 한 이유를 나타내는 열거 형식 변수입니다. 참조 [CFileException::m_cause](#m_cause) 가능한 값 목록은 합니다.  
  
 `lOsError`  
 운영 체제별 이유는 사용 가능한 경우는 예외입니다. `lOsError` 보다 자세한 정보를 제공 하는 매개 변수 `cause` 않습니다.  
  
 `lpszArchiveName`  
 이름을 포함 하는 문자열을 가리키는 `CFile` 예외를 발생 시킨 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 생성자를 직접 사용 하지 않고 대신 전역 함수를 호출 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)합니다.  
  
> [!NOTE]
>  변수 `lOsError` 에 적용 됩니다 `CFile` 및 `CStdioFile` 개체입니다. `CMemFile` 클래스는이 오류 코드를 처리 하지 않습니다.  
  
##  <a name="a-nameerrnotoexceptiona--cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>CFileException::ErrnoToException  
 에 지정 된 런타임 라이브러리 오류 값으로 변환 된 `CFileException` 오류 값을 열거 합니다.  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrno`  
 ERRNO 런타임 포함 파일에 정의 된 정수 오류 코드입니다.&8;.  
  
### <a name="return-value"></a>반환 값  
 지정 된 런타임 라이브러리 오류 값에 해당 하는 열거형된 값입니다.  
  
### <a name="remarks"></a>주의  
 참조 [CFileException::m_cause](#m_cause) 가능한 목록에 대 한 열거 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles #&26;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="a-namegeterrormessagea--cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>CFileException::GetErrorMessage  
 예외를 설명 하는 텍스트를 검색 합니다.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in, out] `lpszError`  
 오류 메시지를 수신 하는 버퍼에 대 한 포인터입니다.  
  
 [in] `nMaxError`  
 지정 된 버퍼에 저장할 수는 문자의 최대 수입니다. 여기에 null 종결 문자 포함 됩니다.  
  
 [in, out] `pnHelpContext`  
 도움말 컨텍스트 ID를 수신 하는 부호 없는 정수에 대 한 포인터 경우 `NULL`, ID가 없습니다. 반환 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 버퍼가 너무 작아서 오류 메시지가 잘립니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 `CFileException::GetErrorMessage`합니다.  
  
 [!code-cpp[NVC_MFCExceptions #&22;](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="a-namemcausea--cfileexceptionmcause"></a><a name="m_cause"></a>CFileException::m_cause  
 `CFileException` 열거형 형식으로 정의되는 값을 포함합니다.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버는 `int` 형식의 공용 변수입니다. 아래에 열거자와 해당 의미가 나와 있습니다.  
  
- `CFileException::none`0: 오류가 발생 하지 않았습니다.  
  
- `CFileException::genericException`1: 지정 되지 않은 오류가 발생 했습니다.  
  
- `CFileException::fileNotFound`2: 파일을 찾을 수 없습니다.  
  
- `CFileException::badPath`3: 전체 또는 경로의 일부가 올바르지 않습니다.  
  
- `CFileException::tooManyOpenFiles`4: 열려 있는 파일의 허용 된 수를 초과 했습니다.  
  
- `CFileException::accessDenied`5: 파일에 액세스할 수 없습니다.  
  
- `CFileException::invalidFile`6: 잘못 된 파일 핸들을 사용 하려고 했습니다.  
  
- `CFileException::removeCurrentDir`7: 현재 작업 디렉터리를 제거할 수 없습니다.  
  
- `CFileException::directoryFull`8: 디렉터리 항목이 더 이상 있습니다.  
  
- `CFileException::badSeek`9: 파일 포인터를 설정 하는 동안 오류가 발생 했습니다.  
  
- `CFileException::hardIO`10: 하드웨어 오류가 발생 했습니다.  
  
- `CFileException::sharingViolation`11: 공유 합니다. EXE가 로드 되지 또는 공유 영역이 잠겼습니다.  
  
- `CFileException::lockViolation`12: 이미 잠겨 있는 영역을 잠그려고 시도 했습니다.  
  
- `CFileException::diskFull`14: 디스크가 꽉 차지 합니다.  
  
- `CFileException::endOfFile`15: 파일의 끝에 도달 했습니다.  
  
    > [!NOTE]
    >  이러한 `CFileException` 원인 열거자는 `CArchiveException` 원인 열거자와는 다릅니다.  
  
    > [!NOTE]
    > `CArchiveException::generic`은 사용되지 않습니다. 대신 `genericException`를 사용하십시오. 응용 프로그램에서 `generic`을 사용하며 /clr을 사용하여 빌드한 경우 발생하는 구문 오류는 해독하기가 쉽지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles #&30;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="a-namemloserrora--cfileexceptionmloserror"></a><a name="m_loserror"></a>CFileException::m_lOsError  
 이 예외에 대 한 운영 체제 오류 코드를 포함합니다.  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>주의  
 오류 코드 목록에 대 한 운영 체제 기술 설명서를 참조 하십시오. 이 데이터 멤버는 형식의 공용 변수 **긴**합니다.  
  
##  <a name="a-namemstrfilenamea--cfileexceptionmstrfilename"></a><a name="m_strfilename"></a>CFileException::m_strFileName  
 이 예외 상태에 대 한 파일의 이름을 포함합니다.  
  
```  
CString m_strFileName;  
```  
  
##  <a name="a-nameoserrortoexceptiona--cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>CFileException::OsErrorToException  
 에 해당 하는 열거자를 반환 된 특정 `lOsError` 값입니다. 오류 코드를 알 수 없는 경우 함수는 반환 **CFileException::generic**합니다.  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>매개 변수  
 `lOsError`  
 운영 체제 시스템-관련 오류 코드입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 운영 체제 오류 값에 해당 하는 열거형된 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles #&27;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="a-namethrowerrnoa--cfileexceptionthrowerrno"></a><a name="throwerrno"></a>CFileException::ThrowErrno  
 생성 한 `CFileException` 개체에 해당 하는 지정 된 `nErrno` 값, 예외를 throw 합니다.  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nErrno`  
 ERRNO 런타임 포함 파일에 정의 된 정수 오류 코드입니다.&8;.  
  
 `lpszFileName`  
 파일의 이름을 포함 하는 문자열에 대 한 포인터를 발생 시킨 예외를 사용할 수 있는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles #&28;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="a-namethrowoserrora--cfileexceptionthrowoserror"></a><a name="throwoserror"></a>CFileException::ThrowOsError  
 Throw는 `CFileException` 에 해당 하는 지정 된 `lOsError` 값입니다. 오류 코드를 알 수 없는 경우 다음으로 코딩 된 예외를 throw 하는 함수 **CFileException::generic**합니다.  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lOsError`  
 운영 체제 시스템-관련 오류 코드입니다.  
  
 `lpszFileName`  
 파일의 이름을 포함 하는 문자열에 대 한 포인터를 발생 시킨 예외를 사용할 수 있는 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCFiles #&29;](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [예외 처리](../../mfc/reference/exception-processing.md)




