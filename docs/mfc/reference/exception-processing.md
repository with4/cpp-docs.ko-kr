---
title: "예외 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros, exception handling
- DAO (Data Access Objects), exceptions
- OLE exceptions, MFC functions
- exceptions, processing
- exception macros
- termination functions, MFC
- MFC, exceptions
- exceptions, MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: fc136efaa6312edf3edfa8420411eda73e1c2468
ms.contentlocale: ko-kr
ms.lasthandoff: 04/04/2017

---
# <a name="exception-processing"></a>예외 처리
프로그램이 실행 될 때 다양 한 비정상적인 상태 및 "예외" 라는 오류가 발생할 수 있습니다. 이러한 메모리, 리소스 할당 오류와 파일을 찾을 수는 실패의 부족 포함 될 수 있습니다.  
  
 Microsoft Foundation Class 라이브러리는 c + +에 대 한 ANSI 표준 위원회에서 제안한 하나 후 밀접 하 게 모델링 되는 예외 처리 체계를 사용 합니다. 에 비정상적인 상황이 발생할 수 있는 함수를 호출 하기 전에 예외 처리기를 설정 해야 합니다. 함수는 비정상 상태를 발견 하는 경우 예외를 throw 하 고 예외 처리기로 제어가 전달 됩니다.  
  
 Microsoft Foundation Class 라이브러리에 포함 된 여러 매크로 예외 처리기를 설정 합니다. 다양 한 다른 전역 함수가 필요한 경우 특수 한 예외를 throw 하 고 프로그램을 종료 하려면 도움말 합니다. 이러한 매크로 및 전역 함수는 다음 범주에 속합니다.  
  
- 예외 매크로 예외 처리기를 구성 합니다.  
  
- 함수 Exception-throwing), 특정 형식의 예외를 생성 하는 합니다.  
  
- 프로그램 종료의 원인이 종료 함수입니다.  
  
 예제 및 자세한 정보에 대 한 문서를 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="exception-macros"></a>예외 매크로  
  
|||  
|-|-|  
|[시도](#try)|예외 처리를 위해 코드 블록을 지정합니다.|  
|[CATCH](#catch)|앞에서 예외를 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[CATCH_ALL](#catch_all)|앞에서 모든 예외를 catch 하는 코드 블록을 지정 **시도** 블록입니다.|  
|[AND_CATCH](#and_catch)|앞에서 추가 예외 유형을 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[AND_CATCH_ALL](#and_catch_all)|앞에서 throw 된 다른 모든 추가 예외 형식을 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[END_CATCH](#end_catch)|마지막 종료 **CATCH** 또는 `AND_CATCH` 코드 블록입니다.|  
|[END_CATCH_ALL](#end_catch_all)|마지막 종료 `CATCH_ALL` 코드 블록입니다.|  
|[THROW](#throw)|지정 된 예외를 throw합니다.|  
|[THROW_LAST](#throw_last)|다음 외부 처리기를 현재 처리 된 예외를 throw합니다.|  
  
### <a name="exception-throwing-functions"></a>예외 Throw 함수  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|아카이브 예외를 throw합니다.|  
|[AfxThrowFileException](#afxthrowfileexception)|파일 예외를 throw합니다.|  
|[AfxThrowInvalidArgException](#afxthrowinvalidargexception)|잘못 된 인수 예외를 throw합니다.|
|[AfxThrowMemoryException](#afxthrowmemoryexception)|메모리 예외가 throw 됩니다.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|지원 되지 않는 예외를 throw합니다.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows 리소스를 찾을 수 없다는 예외를 throw 합니다.|  
|[AfxThrowUserException](#afxthrowuserexception)|사용자가 시작한 프로그램 작업에서 예외를 throw 합니다.|  
  
 MFC는 OLE 예외에 대 한 구체적으로 두 개의 예외 throw 함수를 제공합니다.  
  
### <a name="ole-exception-functions"></a>OLE 예외 함수  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE 자동화 함수 내에서 예외가 throw 됩니다.|  
|[AfxThrowOleException](#afxthrowoleexception)|OLE 예외를 throw 합니다.|  
  
 데이터베이스 예외를 지원 하려면 데이터베이스 클래스는 두 개의 예외 클래스를 제공 `CDBException` 및 `CDaoException`, 예외 형식을 지원 하기 위해 전역 함수 및:  
  
### <a name="dao-exception-functions"></a>DAO 예외 함수  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|throw 한 [CDaoException](../../mfc/reference/cdaoexception-class.md) 사용자 고유의 코드에서.|  
|[AfxThrowDBException](#afxthrowdbexception)|throw 한 [잠금을](../../mfc/reference/cdbexception-class.md) 사용자 고유의 코드에서.|  
  
 MFC는 다음과 같은 종료 함수를 제공합니다.  
  
### <a name="termination-functions"></a>종료 함수  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|호출 시 오류가 응용 프로그램을 종료 하 발생 합니다.|  
  
##  <a name="try"></a>시도  
 설정 된 **시도** 블록입니다.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>주의  
 A **시도** 블록 예외를 throw 할 수 있는 코드 블록을 식별 합니다. 다음에서 처리 되는 이러한 예외 **CATCH** 및 `AND_CATCH` 블록입니다. 재귀 ï ´ ù: 예외 외부에 전달할 수 있습니다 **시도** 을 무시 하거나 사용 하 여 블록에서 `THROW_LAST` 매크로입니다. 종료는 **시도** 블록와 함께 `END_CATCH` 또는 `END_CATCH_ALL` 매크로입니다.  
  
 자세한 내용은 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  

### <a name="requirements"></a>요구 사항
헤더: afx.h

##  <a name="catch"></a>CATCH  
 이전에 throw 되는 첫 번째 예외 형식을 catch 하는 코드 블록을 정의 **시도** 블록입니다.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_class*  
 테스트 하기 위해 예외 유형을 지정 합니다. 목록이 표준 예외 클래스에 대 한 클래스를 참조 하십시오. [CException](../../mfc/reference/cexception-class.md)합니다.  
  
 *exception_object_pointer_name*  
 매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용 하 여 내에서 예외 개체에 액세스 하는 **CATCH** 블록입니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. `THROW_LAST` 매크로를 호출하여 다음 외부 예외 프레임으로 처리를 이동합니다. 종료는 **시도** 블록와 함께 `END_CATCH` 매크로입니다.  
  
 경우 *exception_class* 클래스 `CException`, 다음 예외 형식 모두 발견 됩니다. 사용할 수는 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 멤버 함수를 특정 예외 throw 되었는지 확인 합니다. 여러 종류의 예외를 catch 하에 더 좋은 방법은 순차적 사용 하는 것 `AND_CATCH` 각각 다른 예외 형식을 문입니다.  
  
 예외 개체 포인터는 매크로 의해 생성 됩니다. 직접 선언할 필요가 없습니다.  
  
> [!NOTE]
>  **CATCH** 블록은 중괄호로 구분 된 c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다. 이 적용 됩니다. *exception_object_pointer_name*합니다.  
  
 예외에 대 한 자세한 내용은 및 **CATCH** 매크로 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCExceptions # 26](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="catch_all"></a>CATCH_ALL  
 정의 따르면 이전에 throw 되는 모든 예외 형식을 catch 하는 코드 블록이 **시도** 블록입니다.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer_name*  
 매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용해서 `CATCH_ALL` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>설명  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. `THROW_LAST` 매크로를 호출하여 다음 외부 예외 프레임으로 처리를 이동합니다. 사용 하는 경우 `CATCH_ALL`, 최종의 **시도** 블록와 함께 `END_CATCH_ALL` 매크로입니다.  
  
> [!NOTE]
>  `CATCH_ALL` 블록은 중괄호로 구분된 C++ 범위로 정의됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다.  
  
 예외에 대 한 자세한 내용은 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  

##  <a name="and_catch"></a>AND_CATCH  
 앞에서 발생 하는 추가 예외 형식을 catch 하기 위한 코드 블록을 정의 **시도** 블록입니다.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_class*  
 테스트 하기 위해 예외 유형을 지정 합니다. 목록이 표준 예외 클래스에 대 한 클래스를 참조 하십시오. [CException](../../mfc/reference/cexception-class.md)합니다.  
  
 *exception_object_pointer_name*  
 매크로 의해 생성 되는 예외-개체 포인터에 대 한 이름입니다. 포인터 이름을 사용해서 `AND_CATCH` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여는 **CATCH** 매크로를 하나의 예외 형식을 catch 하면 `AND_CATCH` 각 후속 형식을 catch 하는 매크로입니다. 종료는 **시도** 블록와 함께 `END_CATCH` 매크로입니다.  
  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. 호출 된 `THROW_LAST` 내에서 매크로 `AND_CATCH` 다음 외부 예외 프레임으로 처리 하는 shift를 차단 합니다. `AND_CATCH`앞의 끝을 표시 **CATCH** 또는 `AND_CATCH` 블록입니다.  
  
> [!NOTE]
>  `AND_CATCH` 블록 (중괄호로 구분)을 c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언 하는 경우 해당 범위 내 에서만 액세스할 수 있는지를 기억 합니다. 이 적용 됩니다.는 *exception_object_pointer_name* 변수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
##  <a name="and_catch_all"></a>AND_CATCH_ALL  
 앞에서 발생 하는 추가 예외 형식을 catch 하기 위한 코드 블록을 정의 **시도** 블록입니다.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer_name*  
 매크로 의해 생성 되는 예외-개체 포인터에 대 한 이름입니다. 포인터 이름을 사용해서 `AND_CATCH_ALL` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여는 **CATCH** 매크로를 하나의 예외 형식을 catch 하면 `AND_CATCH_ALL` 매크로를 다른 모든 후속 형식을 catch 합니다. 사용 하는 경우 `AND_CATCH_ALL`, 최종의 **시도** 블록와 함께 `END_CATCH_ALL` 매크로입니다.  
  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. 호출 된 `THROW_LAST` 내에서 매크로 `AND_CATCH_ALL` 다음 외부 예외 프레임으로 처리 하는 shift를 차단 합니다. `AND_CATCH_ALL`앞의 끝을 표시 **CATCH** 또는 `AND_CATCH_ALL` 블록입니다.  
  
> [!NOTE]
>  `AND_CATCH_ALL` 블록 (중괄호로 구분)을 c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언 하는 경우 해당 범위 내 에서만 액세스할 수 있는지를 기억 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="end_catch"></a>END_CATCH  
 마지막의 끝을 표시 **CATCH** 또는 `AND_CATCH` 블록입니다.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>설명  
 대 한 자세한 내용은 `END_CATCH` 매크로 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="end_catch_all"></a>END_CATCH_ALL  
 마지막의 끝을 표시 `CATCH_ALL` 또는 `AND_CATCH_ALL` 블록입니다.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="throw"></a>THROW (MFC)  
 지정된 된 예외를 throw합니다.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer*  
 파생 된 예외 개체를 가리킵니다 `CException`합니다.  
  
### <a name="remarks"></a>설명  
 **THROW** 인터럽트 프로그램 실행, 연결 된 컨트롤을 전달 **CATCH** 프로그램에서 차단 합니다. 제공 되지 않은 경우는 **CATCH** 차단 컨트롤이 인쇄는 오류 메시지 및 종료 하는 Microsoft Foundation Class 라이브러리 모듈에 전달 합니다.  
  
 자세한 내용은 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="throw_last"></a>THROW_LAST  
 다음 예외를 다시 throw 외부 **CATCH** 블록입니다.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하면 로컬에서 만든된 예외를 throw 수 있습니다. 방금 따라잡을 예외를 throw 하려는 경우 일반적으로 범위를 벗어납니다 하 고 삭제할 수 있습니다. 와 `THROW_LAST`, 다음 예외를 올바르게 전달 **CATCH** 처리기입니다.  
  
 자세한 내용은 문서 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 아카이브 예외를 throw합니다.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>매개 변수  
 `cause`  
 예외에 대 한 이유를 나타내는 정수를 지정 합니다. 목록이 가능한 값에 대 한 참조 [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)합니다.  
  
 `lpszArchiveName`  
 이름을 포함 하는 문자열을 가리키는 `CArchive` (있는 경우) 예외를 발생 시킨 개체입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowfileexception"></a>AfxThrowFileException  
 파일 예외를 throw합니다.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `cause`  
 예외에 대 한 이유를 나타내는 정수를 지정 합니다. 목록이 가능한 값에 대 한 참조 [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause)합니다.  
  
 `lOsError`  
 (있는 경우) 운영 체제 오류 번호가 예외의 원인을 설명 하는 합니다. 오류 코드 목록에 대 한 운영 체제 설명서를 참조 하십시오.  
  
 `lpszFileName`  
 (있는 경우) 예외를 발생 시킨 파일의 이름을 포함 하는 문자열을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 운영 체제 오류 코드에 따라 원인을 책임이 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  

## <a name="afxthrowinvalidargexception"></a>AfxThrowInvalidArgException
잘못 된 인수 예외를 throw합니다.  
   
### <a name="syntax"></a>구문    
```
void AfxThrowInvalidArgException( );  
```  
   
### <a name="remarks"></a>설명  
 이 함수는 잘못 된 인수가 사용 될 때 호출 됩니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afx.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [CInvalidArgException 클래스](cinvalidargexception-class.md)   
 [THROW](#throw)
  
  
##  <a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 메모리 예외가 throw 됩니다.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>설명  
 경우이 함수를 호출 기본 시스템 메모리 할당자에 대 한 호출 (같은 `malloc` 및 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 함수)에 실패 합니다. 에 대 한 호출을 위해 불필요 **새** 때문에 **새** 에서 예외를 throw 메모리 자동으로 메모리 할당에 실패 하는 경우.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 지원 되지 않는 기능을 요청한 결과인 예외를 throw 합니다.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 리소스 예외를 throw합니다.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 Windows 리소스를 로드할 수 없는 경우 호출 됩니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowuserexception"></a>AfxThrowUserException  
 최종 사용자 작업을 중지 하도록 예외가 throw 됩니다.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 한 직후 호출 `AfxMessageBox` 사용자에 게 오류를 보고 했습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 이 함수를 사용 하 여 OLE 자동화 함수 내에서 예외를 throw 합니다.  
  
```   
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,  
    LPCSTR lpszDescription,  
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,  
    UINT nDescriptionID,  
    UINT nHelpID = -1); 
```  
  
### <a name="parameters"></a>매개 변수  
 `wCode`  
 응용 프로그램에 오류 코드입니다.  
  
 `lpszDescription`  
 오류의 설명입니다.  
  
 `nDescriptionID`  
 일반 언어로 된 오류 설명에 대 한 리소스 ID입니다.  
  
 `nHelpID`  
 응용 프로그램의 도움말에 대 한 도움말 컨텍스트 (합니다. HLP) 파일입니다.  
  
### <a name="remarks"></a>설명  
 (Microsoft Visual Basic 또는 다른 OLE 자동화 클라이언트 응용 프로그램) 구동 응용 프로그램에서이 함수에 제공 된 정보를 표시할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCExceptions # 25](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxthrowoleexception"></a>AfxThrowOleException  
 형식의 개체를 만듭니다. `COleException` 예외를 throw 합니다.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>매개 변수  
 `sc`  
 예외에 대 한 이유를 나타내는 OLE 상태 코드입니다.  
  
 `hr`  
 예외에 대 한 이유를 나타내는 결과 코드에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 사용 하는 버전은 `HRESULT` 인수로 해당 결과 코드를 해당로 변환 하는 대로 `SCODE`합니다. 대 한 자세한 내용은 `HRESULT` 및 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 형식의 예외를 throw 하려면이 함수를 호출 [CDaoException](../../mfc/reference/cdaoexception-class.md) 사용자 고유의 코드에서.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>매개 변수  
 `nAfxDaoError`  
 확장 된 오류 코드는 DAO를 나타내는 정수 값을는 나열 될 수 있습니다는 값 중 하나에서 [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)합니다.  
  
 *scode*  
 OLE 오류 코드 유형의 DAO에서 `SCODE`합니다. 자세한 내용은 참조 [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크에서 호출 또한 `AfxThrowDaoException`합니다. 호출에서 매개 변수 중 하나 또는 둘 모두를 전달할 수 있습니다. 에 오류 정보에서 정의 된 발생 중 하나를 하려는 경우 예를 들어 **CDaoException::nAfxDaoError** 에 대 한 중요 하지 않은 있지만 *scode* 매개 변수를 전달에 올바른 코드는 `nAfxDaoError` 매개 변수에 대 한 기본값을 그대로 및 *scode*합니다.  
  
 MFC DAO 클래스와 관련 된 예외에 대 한 내용은 클래스를 참조 하십시오. `CDaoException` 이 책 목록과 문서에서 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdb.h  
  
##  <a name="afxthrowdbexception"></a>AfxThrowDBException  
 형식의 예외를 throw 하려면이 함수를 호출 `CDBException` 사용자 고유의 코드에서.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 형식의 값 **RETCODE**, 오류를 throw 한 예외를 발생 시킨 유형을 정의 합니다.  
  
 `pdb`  
 에 대 한 포인터는 `CDatabase` 예외와 관련 된 데이터 원본 연결을 나타내는 개체입니다.  
  
 `hstmt`  
 ODBC **HSTMT** 예외와 관련 된 문 핸들을 지정 하는 핸들입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크를 호출 하 여 `AfxThrowDBException` ODBC를 받을 때 **RETCODE** ODBC API 호출에서 함수를 해석 하는 **RETCODE** expectable 오류가 아닌 예외 상황을 합니다. 예를 들어, 디스크 읽기 오류 때문에 데이터 액세스 작업이 실패할 수 있습니다.  
  
 에 대 한 내용은 **RETCODE** ODBC에 정의 된 값의 8 장, "검색 상태 및 오류 정보를" 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이러한 코드에 대 한 MFC 확장에 대 한 내용은 클래스를 참조 하십시오. [잠금을](../../mfc/reference/cdbexception-class.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="afxabort"></a>AfxAbort  
 MFC에서 제공 하는 기본 종료 함수  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>주의  
 `AfxAbort`내부적으로 호출 MFC 멤버 함수에 의해 확인할 수 없는 예외가 처리할 수 없는 등의 심각한 오류가 있을 때. 호출할 수 있습니다 `AfxAbort` 복구할 수 없는 치명적인 오류가 발생 하는 경우에 드문 경우에서입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afx.h   
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)

