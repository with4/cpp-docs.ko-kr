---
title: "예외 처리 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a2ded9c49a9f6935a5b268ccbefc4678af184029
ms.lasthandoff: 02/24/2017

---
# <a name="exception-processing"></a>예외 처리
프로그램을 실행 하는 경우 다양 한 비정상적인 상태 및 "예외" 라는 오류가 발생할 수 있습니다. 이러한 메모리, 리소스 할당 오류 및 오류 파일을 찾으려면 부족 해지지 포함 될 수 있습니다.  
  
 Microsoft Foundation Class 라이브러리는 c + +에 대 한 ANSI 표준 위원회에서 제안 된 후와 비슷하게 모델링 하는 예외 처리 체계를 사용 합니다. 비정상적인 상황이 발생할 수 있는 함수를 호출 하기 전에 예외 처리기 설정 되어야 합니다. 함수는 비정상 상태를 발견 하는 경우 예외를 throw 하 고, 예외 처리기로 제어가 전달 됩니다.  
  
 Microsoft Foundation 클래스 라이브러리에 포함 된 여러 매크로 예외 처리기를 설정 합니다. 다양 한 다른 전역 함수가 특수 한 예외를 throw 하 고 프로그램을 종료 하는 데 도움이 되는 필요한 경우. 이러한 매크로 및 전역 함수에는 다음 범주로 구분 됩니다.  
  
- 예외 매크로 예외 처리기를 구성 합니다.  
  
- 함수를 Exception-throwing), 특정 형식의 예외를 생성 하는 합니다.  
  
- 프로그램 종료의 원인이 종료 함수입니다.  
  
 예제 및 자세한 정보에 대 한 문서를 참조 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="exception-macros"></a>예외 매크로  
  
|||  
|-|-|  
|[시도](#try)|예외 처리를 위해 코드 블록을 지정합니다.|  
|[CATCH](#catch)|앞에서 예외를 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[CATCH_ALL](#catch_all)|앞에서 모든 예외를 catch 하는 것에 대 한 코드 블록을 지정 **시도** 블록입니다.|  
|[AND_CATCH](#and_catch)|앞에서 추가 예외 유형을 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[AND_CATCH_ALL](#and_catch_all)|앞에서 throw 된 다른 모든 추가 예외 형식을 catch 하기 위한 코드 블록을 지정 **시도** 블록입니다.|  
|[END_CATCH](#end_catch)|마지막 종료 **CATCH** 또는 `AND_CATCH` 코드 블록입니다.|  
|[END_CATCH_ALL](#end_catch_all)|마지막 종료 `CATCH_ALL` 코드 블록입니다.|  
|[THROW](#throw)|지정 된 예외를 throw합니다.|  
|[THROW_LAST](#throw_last)|현재 처리 된 다음 외부 처리기에 예외를 throw합니다.|  
  
### <a name="exception-throwing-functions"></a>예외 Throw 함수  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|아카이브 예외를 throw합니다.|  
|[AfxThrowFileException](#afxthrowfileexception)|파일 예외를 throw합니다.|  
|[AfxThrowMemoryException](#afxthrowmemoryexception)|메모리 예외를 throw합니다.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|지원 되지 않는 예외를 throw합니다.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Windows 리소스를 찾을 수 없다는 예외를 throw합니다.|  
|[AfxThrowUserException](#afxthrowuserexception)|사용자가 시작한 프로그램 작업 중에 예외가 throw 됩니다.|  
  
 MFC는 OLE 예외에 대 한 구체적으로 예외를 throw 할 두 가지 기능을 제공합니다.  
  
### <a name="ole-exception-functions"></a>OLE 예외 함수  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|OLE 자동화 함수 내에서 예외를 throw합니다.|  
|[AfxThrowOleException](#afxthrowoleexception)|OLE 예외를 throw 합니다.|  
  
 데이터베이스 예외를 지원 하기 위해 데이터베이스 클래스에서 두 개의 예외 클래스를 제공 `CDBException` 및 `CDaoException`, 및 예외 형식을 지원 하기 위해 전역 함수:  
  
### <a name="dao-exception-functions"></a>DAO 예외 함수  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Throw는 [CDaoException](../../mfc/reference/cdaoexception-class.md) 사용자 고유의 코드에서.|  
|[AfxThrowDBException](#afxthrowdbexception)|Throw는 [잠금을](../../mfc/reference/cdbexception-class.md) 사용자 고유의 코드에서.|  
  
 MFC는 다음과 같은 종료 함수를 제공합니다.  
  
### <a name="termination-functions"></a>종료 함수  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|호출 시 오류가 응용 프로그램을 종료 하 발생 합니다.|  
  
##  <a name="a-nametrya--try"></a><a name="try"></a>시도  
 설정 하는 **시도** 블록입니다.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>주의  
 A **시도** 블록 예외를 throw 할 수 있는 코드 블록을 식별 합니다. 다음에서 처리 되는 이러한 예외 **CATCH** 및 `AND_CATCH` 블록입니다. 재귀는 허용: 외부에 예외를 전달할 수 있습니다 **시도** 블록을 무시 하거나 사용 하 여는 `THROW_LAST` 매크로입니다. 종료는 **시도** 블록는 `END_CATCH` 또는 `END_CATCH_ALL` 매크로입니다.  
  
 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  

### <a name="requirements"></a>요구 사항
헤더: afx.h

##  <a name="a-namecatcha--catch"></a><a name="catch"></a>CATCH  
 앞에서 throw 된 첫 번째 예외 형식을 catch 하는 코드 블록을 정의 **시도** 블록입니다.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_class*  
 테스트 하기 위해 예외 유형을 지정 합니다. 표준 예외 클래스의 목록이 참조 클래스 [CException](../../mfc/reference/cexception-class.md)합니다.  
  
 *exception_object_pointer_name*  
 매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용 하 여 내에서 예외 개체에 액세스 하는 **CATCH** 블록입니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. `THROW_LAST` 매크로를 호출하여 다음 외부 예외 프레임으로 처리를 이동합니다. 종료는 **시도** 블록는 `END_CATCH` 매크로입니다.  
  
 경우 *exception_class* 는 클래스 `CException`, 모든 예외 형식을 발생 합니다. 사용할 수는 [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) 멤버 함수는 특정 예외가 throw 되었는지 확인 합니다. 좋은 방법이 몇 가지 종류의 예외를 catch 하는 순차를 사용 하 여 `AND_CATCH` 문을 각각 다른 예외 형식입니다.  
  
 예외 개체 포인터는 매크로 의해 생성 됩니다. 직접 선언할 필요가 없습니다.  
  
> [!NOTE]
>  **CATCH** 블록은 중괄호로 구분 된 c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다. 이 적용 됩니다 *exception_object_pointer_name*합니다.  
  
 예외에 대 한 자세한 내용은 및 **CATCH** 매크로 문서를 참조 하십시오 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCExceptions #&26;](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="a-namecatchalla--catchall"></a><a name="catch_all"></a>CATCH_ALL  
 앞에서 throw 되는 모든 예외 형식을 catch 하는 코드 블록 정의 **시도** 블록입니다.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer_name*  
 매크로에 의해 생성되는 예외-개체 포인터에 대한 이름을 지정합니다. 포인터 이름을 사용해서 `CATCH_ALL` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. `THROW_LAST` 매크로를 호출하여 다음 외부 예외 프레임으로 처리를 이동합니다. 사용 하는 경우 `CATCH_ALL`, 끝의 **시도** 블록는 `END_CATCH_ALL` 매크로입니다.  
  
> [!NOTE]
>  `CATCH_ALL` 블록은 중괄호로 구분된 C++ 범위로 정의됩니다. 이 범위에서 변수를 선언하면 해당 범위 내에서만 액세스할 수 있습니다.  
  
 예외에 대 한 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  

##  <a name="a-nameandcatcha--andcatch"></a><a name="and_catch"></a>AND_CATCH  
 블록의 코드 앞에서 throw 하는 추가 예외 형식을 정의 **시도** 블록입니다.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_class*  
 테스트 하기 위해 예외 유형을 지정 합니다. 표준 예외 클래스의 목록이 참조 클래스 [CException](../../mfc/reference/cexception-class.md)합니다.  
  
 *exception_object_pointer_name*  
 매크로 의해 생성 되는 예외-개체 포인터에 대 한 이름입니다. 포인터 이름을 사용해서 `AND_CATCH` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 사용 하는 **CATCH** 한 예외 형식을 catch 하는 매크로 `AND_CATCH` 각 후속 형식을 catch 하는 매크로입니다. 종료는 **시도** 블록는 `END_CATCH` 매크로입니다.  
  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. 호출의 `THROW_LAST` 내에서 매크로 `AND_CATCH` 다음 외부 예외 프레임으로 처리 하는 shift를 차단 합니다. `AND_CATCH`앞의 끝을 표시 **CATCH** 또는 `AND_CATCH` 블록입니다.  
  
> [!NOTE]
>  `AND_CATCH` 블록 (중괄호 구분 된) c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언 하는 경우 해당 범위 내 에서만 액세스할 수 있는지를 기억 합니다. 에 마찬가지는 *exception_object_pointer_name* 변수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
##  <a name="a-nameandcatchalla--andcatchall"></a><a name="and_catch_all"></a>AND_CATCH_ALL  
 블록의 코드 앞에서 throw 하는 추가 예외 형식을 정의 **시도** 블록입니다.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer_name*  
 매크로 의해 생성 되는 예외-개체 포인터에 대 한 이름입니다. 포인터 이름을 사용해서 `AND_CATCH_ALL` 블록 내에서 예외 개체에 액세스할 수 있습니다. 이 변수는 자동으로 선언됩니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여는 **CATCH** 한 예외 형식을 catch 하는 매크로 `AND_CATCH_ALL` 다른 모든 후속 형식을 catch 하는 매크로입니다. 사용 하는 경우 `AND_CATCH_ALL`, 끝의 **시도** 블록는 `END_CATCH_ALL` 매크로입니다.  
  
 예외 처리 코드는 필요한 경우 예외 개체를 확인하여 예외의 특정 원인에 대한 추가 정보를 가져올 수 있습니다. 호출의 `THROW_LAST` 내에서 매크로 `AND_CATCH_ALL` 다음 외부 예외 프레임으로 처리 하는 shift를 차단 합니다. `AND_CATCH_ALL`앞의 끝을 표시 **CATCH** 또는 `AND_CATCH_ALL` 블록입니다.  
  
> [!NOTE]
>  `AND_CATCH_ALL` 블록 (중괄호로 구분 된) c + + 범위로 정의 됩니다. 이 범위에서 변수를 선언 하는 경우 해당 범위 내 에서만 액세스할 수 있는지를 기억 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameendcatcha--endcatch"></a><a name="end_catch"></a>END_CATCH  
 마지막의 끝을 표시 **CATCH** 또는 `AND_CATCH` 블록입니다.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>주의  
 대 한 자세한 내용은 `END_CATCH` 매크로 문서를 참조 하십시오 [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameendcatchalla--endcatchall"></a><a name="end_catch_all"></a>END_CATCH_ALL  
 마지막의 끝을 표시 `CATCH_ALL` 또는 `AND_CATCH_ALL` 블록입니다.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-namethrowa--throw-mfc"></a><a name="throw"></a>THROW (MFC)  
 지정된 된 예외를 throw합니다.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>매개 변수  
 *exception_object_pointer*  
 파생 된 예외 개체를 가리키는 `CException`합니다.  
  
### <a name="remarks"></a>주의  
 **THROW** 인터럽트 프로그램 실행, 연결 된 컨트롤을 전달 **CATCH** 프로그램에서 차단 합니다. 제공 하지 않은 경우는 **CATCH** 블록을 다음 컨트롤 출력에 오류 메시지 및 종료 하는 Microsoft Foundation Class 라이브러리 모듈에 전달 됩니다.  
  
 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-namethrowlasta--throwlast"></a><a name="throw_last"></a>THROW_LAST  
 다음 예외를 다시 throw 외부 **CATCH** 블록입니다.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하면 로컬에서 생성된 된 예외를 throw 수 있습니다. 방금 발생 하는 예외를 throw 하려는 경우 일반적으로 범위를 벗어납니다 하 고 삭제할 수 있습니다. 와 `THROW_LAST`, 다음 예외를 올바르게 전달 **CATCH** 처리기입니다.  
  
 자세한 내용은 문서를 참조 하십시오. [예외](../../mfc/exception-handling-in-mfc.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [cfile:: Abort](../../mfc/reference/cfile-class.md#abort)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowarchiveexceptiona--afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 아카이브 예외를 throw합니다.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>매개 변수  
 `cause`  
 예외에 대 한 이유를 나타내는 정수를 지정 합니다. 가능한 값 목록은 참조 하십시오. [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause)합니다.  
  
 `lpszArchiveName`  
 이름을 포함 하는 문자열을 가리키는 `CArchive` (가능한 경우) 예외를 발생 시킨 개체입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowfileexceptiona--afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException  
 파일 예외를 throw합니다.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `cause`  
 예외에 대 한 이유를 나타내는 정수를 지정 합니다. 가능한 값 목록은 참조 하십시오. [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause)합니다.  
  
 `lOsError`  
 (있는 경우) 운영 체제 오류 번호를 포함 하는 예외에 대 한 이유를 나타내는 합니다. 오류 코드 목록에 대 한 운영 체제 설명서를 참조 하십시오.  
  
 `lpszFileName`  
 (있는 경우) 예외를 발생 시킨 파일의 이름을 포함 하는 문자열을 가리킵니다.  
  
### <a name="remarks"></a>주의  
 운영 체제 오류 코드를 기반으로 원인을 책임이 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowmemoryexceptiona--afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 메모리 예외를 throw합니다.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>주의  
 하는 경우이 함수를 호출 합니다. 기본 시스템 메모리 할당자에 대 한 호출 (예: `malloc` 및 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 함수) 실패 합니다. 에 대해 호출할 필요가 없습니다 **새** 때문에 **새** 에서 예외를 throw 메모리 자동으로 메모리 할당이 실패 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrownotsupportedexceptiona--afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 결과 지원 되지 않는 기능에 대 한 요청 되는 예외를 throw 합니다.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowresourceexceptiona--afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 리소스 예외를 throw합니다.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 Windows 리소스를 로드할 수 없는 경우에 호출 됩니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowuserexceptiona--afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException  
 최종 사용자 작업을 중지 하도록 예외가 throw 됩니다.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 한 직후 호출 `AfxMessageBox` 사용자에 게 오류를 보고 했습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowoledispatchexceptiona--afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
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
 응용 프로그램에 특정 오류 코드입니다.  
  
 `lpszDescription`  
 오류 설명 합니다.  
  
 `nDescriptionID`  
 일반 텍스트 오류 설명에 대 한 리소스 ID입니다.  
  
 `nHelpID`  
 응용 프로그램의 도움말에 대 한 도움말 컨텍스트 (합니다. HLP) 파일입니다.  
  
### <a name="remarks"></a>주의  
 (Microsoft Visual Basic 또는 다른 OLE 자동화 클라이언트 응용 프로그램) 구동 응용 프로그램에서이 함수에 제공 되는 정보를 표시할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCExceptions #&25;](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxthrowoleexceptiona--afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException  
 형식의 개체를 만듭니다 `COleException` 예외를 throw 합니다.  
  
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
 사용 하는 버전은 `HRESULT` 인수는 결과 코드를 해당로 변환 하는 대로 `SCODE`합니다. 대 한 자세한 내용은 `HRESULT` 및 `SCODE`, 참조 [COM 오류 코드 구조](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdao.h  
  
##  <a name="a-nameafxthrowdaoexceptiona--afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 형식의 예외를 throw 하려면이 함수를 호출 [CDaoException](../../mfc/reference/cdaoexception-class.md) 사용자 고유의 코드에서.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>매개 변수  
 `nAfxDaoError`  
 오류 코드를 확장 하는 DAO를 나타내는 정수 값을 있는 수는 값 중 하나 아래에 나열 [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror)합니다.  
  
 *scode*  
 OLE 오류 코드를 사용 하 여 형식의 DAO에서 `SCODE`합니다. 내용은 [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode)합니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크는 또한 호출 `AfxThrowDaoException`합니다. 호출에서 매개 변수 중 하나 또는 둘 모두를 전달할 수 있습니다. 예를 들어 중 하나를 높이려는 경우 오류에 정의 **CDaoException::nAfxDaoError** 에 대 한 중요 하지 않지만 *scode* 매개 변수를 전달에서 올바른 코드를는 `nAfxDaoError` 매개 변수 기본값을 적용 하 고 *scode*.  
  
 MFC DAO 클래스와 관련 된 예외에 대 한 정보를 보려면 클래스 `CDaoException` 이 책 목록과 문서에 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdb.h  
  
##  <a name="a-nameafxthrowdbexceptiona--afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException  
 형식의 예외를 throw 하려면이 함수를 호출 `CDBException` 사용자 고유의 코드에서.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>매개 변수  
 `nRetCode`  
 형식의 값 **RETCODE**, throw 된 예외를 발생 시킨 오류의 유형을 정의 합니다.  
  
 `pdb`  
 에 대 한 포인터는 `CDatabase` 예외와 연관 된 데이터 원본 연결을 나타내는 개체입니다.  
  
 `hstmt`  
 ODBC **HSTMT** 예외와 연관 된 문 핸들을 지정 하는 핸들입니다.  
  
### <a name="remarks"></a>주의  
 프레임 워크 호출 `AfxThrowDBException` ODBC을 받을 때 **RETCODE** ODBC API 호출에서 함수를 해석 하는 **RETCODE** expectable 오류가 아닌 예외 상황으로 합니다. 예를 들어, 디스크 읽기 오류 때문에 데이터 액세스 작업이 실패할 수 있습니다.  
  
 에 대 한 내용은 **RETCODE** 의 8 장, "검색 상태 및 오류 정보를"를 참조 하는 ODBC에 정의 된 값은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이러한 코드에 대 한 MFC 확장에 대 한 내용은 클래스 참조 [잠금을](../../mfc/reference/cdbexception-class.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afx.h  
  
##  <a name="a-nameafxaborta--afxabort"></a><a name="afxabort"></a>AfxAbort  
 MFC에서 제공 하는 기본 종료 함수입니다.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>주의  
 `AfxAbort`내부적으로 MFC 멤버 함수에 의해 경우 라고 처리할 수 없는 확인할 수 없는 예외와 같은 심각한 오류가 발생 합니다. 호출할 수 있습니다 `AfxAbort` 복구할 수 없는 치명적인 오류가 발생 하는 경우에 드문 경우에서입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CATCH](#catch)합니다.  

### <a name="requirements"></a>요구 사항  
  **헤더** afx.h   
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)

