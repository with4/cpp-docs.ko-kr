---
title: "CException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CException
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class, base class
- CException class
- exceptions, classes for
- CInternetException class, base class
- macros, exception handling
- CNotSupportedException class, base class
- CFileException class, base class
- CDBException class, base class
- CArchiveException class, base class
- CUserException class
- CDaoException class, base class
- CMemoryException class, base class
- COleException class, base class
- CResourceException class, base class
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4cbb69ff79a1b201260d83b1bd568b63519a33b5
ms.lasthandoff: 02/24/2017

---
# <a name="cexception-class"></a>CException 클래스
MFC 라이브러리의 모든 예외에 대한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CException::CException](#cexception)|`CException` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CException::Delete](#delete)|삭제는 `CException` 개체입니다.|  
|[CException::ReportError](#reporterror)|메시지 상자에 오류 메시지가 사용자에 게 보고합니다.|  
  
## <a name="remarks"></a>주의  
 때문에 `CException` 클래스는 추상 기본 클래스를 만들 수 없습니다 `CException` 개체는 파생 된 클래스의 개체를 만들어야 합니다. 직접 작성 해야 할 경우 `CException`-스타일 클래스 모델로 위에 나열 된 파생된 클래스 중 하나를 사용 합니다. 파생 된 클래스도 사용 하는지 확인 `IMPLEMENT_DYNAMIC`합니다.  
  
 파생된 클래스 및 해당 설명을 보려면 아래에 나와 있습니다.  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|한 리소스에 중요 한 MFC 예외의 기본 클래스|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|잘못 된 인수 예외 상태|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|메모리 부족 예외|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|지원 되지 않는 작업에 대 한 요청|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|보관 파일 관련 예외|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|파일 관련 예외|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows 리소스를 찾을 수 없거나 불가|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE 예외|  
|[잠금](../../mfc/reference/cdbexception-class.md)|데이터베이스 예외 (즉,: MFC 데이터베이스 클래스 개방형 데이터베이스 연결에 따라 발생 하는 예외 조건)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|OLE 디스패치 (자동화) 예외|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|리소스를 찾을 수 없음을 나타냅니다 예외|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|데이터 액세스 개체 예외 (즉,: DAO 클래스에 대 한 발생 하는 예외 조건)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|인터넷 예외 (즉,: 인터넷 클래스에 대해 발생 하는 예외 조건).|  
  
 이러한 예외는 사용 하기 위한 것은 [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [시도](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), 및 [end_catch](exception-processing.md#end_catch) 매크로입니다. 예외에 대 한 자세한 내용은 참조 하십시오. [예외 처리](exception-processing.md), 문서를 참조 하거나 [예외 처리 (MFC)](../exception-handling-in-mfc.md)합니다.  
  
 특정 예외를 catch 하려면 적절 한 파생된 클래스를 사용 합니다. 잡다한 종류의 예외를 사용 `CException`를 사용 하 여 [CObject::IsKindOf](cobject-class.md#iskindof) 사이에서 구별을 `CException`-파생 된 클래스입니다. `CObject::IsKindOf` 으로 선언 된 클래스에 대해서만 작동은 [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) 동적 형식 검사의 이점을 얻으려면 매크로입니다. 모든 `CException`-만드는 파생된 클래스를 사용 하 여는 `IMPLEMENT_DYNAMIC` 매크로 너무 합니다.  
  
 호출 하 여 사용자에 게 예외에 대 한 세부 정보를 보고할 수 [GetErrorMessage](cfileexception-class.md#geterrormessage) 또는 [ReportError](#reporterror), 두 개의 멤버 함수 중 하나에서 작동 하는 `CException`의 파생 클래스입니다.  
  
 매크로 중 하나에서 예외가 포착 되는 경우는 `CException` 삭제 하지 않을 사용자가 직접; 개체는 자동으로 삭제 됩니다. 사용 하 여 예외가 포착 되는 경우는 **catch** 키워드를 자동으로 삭제 되지 않습니다. 문서를 참조 하십시오 [예외 처리 (MFC)](../exception-handling-in-mfc.md) 예외 개체를 삭제 하는 경우에 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](cobject-class.md)  
  
 `CException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
  
##  <a name="a-namecexceptiona--cexceptioncexception"></a><a name="cexception"></a>CException::CException  
 이 멤버 함수를 생성 한 `CException` 개체입니다.  
  
```  
explicit CException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 *b_AutoDelete*  
 지정 **TRUE** 하는 경우에 대 한 메모리는 `CException` 힙에 할당 된 개체입니다. 이 인해는 `CException` 삭제할 때 개체는 **삭제** 멤버 함수가 호출 되어 예외를 삭제 합니다. 지정 **FALSE** 경우는 `CException` 개체가 스택에 이거나 전역 개체입니다. 이 경우에 `CException` 개체는 되지 삭제는 **삭제** 멤버 함수를 호출 합니다.  
  
### <a name="remarks"></a>주의  
 되지 일반적으로이 생성자를 직접 호출 해야 합니다. 인스턴스를 만들어야 한다는 예외를 throw 하는 함수는 `CException`-파생 클래스와 MFC 중 하나를 사용 해야 함수 같은 throw 되거나 해당 생성자를 호출 [AfxThrowFileException](exception-processing.md#afxthrowfileexception), 미리 정의 된 형식을 throw 하 합니다. 이 설명서는 완전성을 위해서만 제공 됩니다.  
  
##  <a name="a-namedeletea--cexceptiondelete"></a><a name="delete"></a>CException::Delete  
 확인 하는 경우는이 함수는 **CException** 힙에서 개체가 만들어진 하 고 그럴 경우 호출 하는 **삭제** 개체에 연산자.  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>주의  
 삭제 하는 경우는 **CException** 개체를 사용 하 여는 **삭제** 멤버 함수는 예외를 삭제 합니다. 사용 하지 않는 **삭제** 연산자를 직접 때문에 `CException` 개체는 전역 개체 이거나 스택에 만든 합니다.  
  
 개체를 생성 하는 경우 개체 삭제 되어야 할지 여부를 지정할 수 있습니다. 자세한 내용은 참조 [CException::CException](#cexception)합니다.  
  
 호출 하기만 하면 **삭제** 는 c + +를 사용 하는 경우 **시도**- **catch** 메커니즘입니다. MFC 매크로 사용 하는 경우 **시도** 및 **CATCH**을 이러한 매크로 자동으로이 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 ```cpp  
 CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the 
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}   
 ```
  
##  <a name="a-namereporterrora--cexceptionreporterror"></a><a name="reporterror"></a>CException::ReportError  
 사용자에 게 메시지 상자에 보고서 오류 텍스트에이 멤버 함수를 호출 합니다.  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nType`  
 메시지 상자의 스타일을 지정합니다. 조합이 적용 된 [메시지 상자 스타일](message-box-styles.md) 상자에 있습니다. 이 매개 변수를 지정 하지 않으면 기본값은 **MB_OK**합니다.  
  
 *nMessageID*  
 예외 개체에 오류 메시지가 없는 경우 표시할 메시지를의 리소스 ID (문자열 항목)를 지정 합니다. 0 인 경우, 메시지 "오류 메시지가 없으면 사용할 수 있는"가 표시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `AfxMessageBox` 값, 메시지 상자를 표시할 메모리가 충분 하지 않은 경우에 그렇지 않으면 0입니다. 참조 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) 가능한 반환 값입니다.  
  
### <a name="example"></a>예제  
 다음은 사용의 예 `CException::ReportError`합니다. 다른 예에 대 한 예제를 참조 하십시오. [CATCH](exception-processing.md#catch)합니다.  
  
```cpp  
CFile fileInput;
CFileException ex;

// try to open a file for reading.  
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>참고 항목  
 [CObject 클래스](cobject-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)   
 [예외 처리](exception-processing.md)   
 [I: 나만의 사용자 지정 예외 클래스를 만드는 방법](http://go.microsoft.com/fwlink/linkid=128045)



