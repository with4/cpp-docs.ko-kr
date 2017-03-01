---
title: "CDaoException 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoException
dev_langs:
- C++
helpviewer_keywords:
- errors [C++], DAO
- CDaoException class
- DAO (Data Access Objects), exceptions
- exceptions, in MFC DAO classes
- Errors collection, DAO
- collections, DAO errors
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d1cb1c6dbe50d383981af03cc97d1977be12a5f6
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoexception-class"></a>CDaoException 클래스
DAO(Data Access Objects)를 기반으로 하는 MFC 데이터베이스 클래스에서 발생하는 예외 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|`CDaoException` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoException::GetErrorCount](#geterrorcount)|데이터베이스 엔진의 오류 컬렉션에 있는 오류 수를 반환합니다.|  
|[CDaoException::GetErrorInfo](#geterrorinfo)|오류 컬렉션에 있는 특정 오류 개체에 대 한 오류 정보를 반환합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|MFC DAO 클래스의 모든 오류에 대 한 확장된 오류 코드를 포함합니다.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|에 대 한 포인터는 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 하나의 DAO 오류 개체에 대 한 정보가 포함 된 개체입니다.|  
|[CDaoException::m_scode](#m_scode)|[SCODE](#m_scode) 오류와 연결 된 값입니다.|  
  
## <a name="remarks"></a>주의  
 클래스는 예외의 원인을 확인 하기 위해 사용할 수 있는 공용 데이터 멤버를 포함 합니다. `CDaoException`개체 생성 되며 DAO 데이터베이스 클래스의 멤버 함수에 의해 throw 됩니다.  
  
> [!NOTE]
>  DAO 데이터베이스 클래스에 연결 ODBC (Open Database)을 기반으로 하는 MFC 데이터베이스 클래스와 구별 됩니다. 모든 DAO 데이터베이스 클래스 이름이 "CDao" 접두사가 있습니다. DAO 클래스의 ODBC 데이터 원본에 액세스할 수 있습니다. 일반적으로 기반으로 DAO MFC 클래스는 ODBC;에 따라 MFC 클래스 보다 더 가능 DAO 기반 클래스를 통해 자신의 데이터베이스 엔진을 통해 ODBC 드라이버를 포함 한 데이터를 액세스할 수 있습니다. DAO 기반 클래스는 또한 DAO를 직접 호출 하지 않고는 클래스를 통해 테이블을 추가 하는 등의 데이터 정의 언어 (DDL) 작업을 지원 합니다. ODBC 클래스에 의해 throw 된 예외에 대 한 자세한 내용은 참조 [잠금을](../../mfc/reference/cdbexception-class.md)합니다.  
  
 예외 개체의 범위 내에서 액세스할 수는 [CATCH](../../mfc/reference/exception-processing.md#catch) 식입니다. Throw 할 수 있습니다 `CDaoException` 사용 하 여 사용자 고유의 코드에서 개체는 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) 전역 함수입니다.  
  
 Mfc에서 모든 DAO 오류 단위로 형식의 예외 `CDaoException`합니다. 이 유형의 예외를 catch 하는 경우 사용할 수 있습니다 `CDaoException` 멤버 함수는 데이터베이스 엔진의 오류 컬렉션에 저장 된 DAO error 개체에서 정보를 검색 합니다. 오류가 발생할 때마다 하나 이상의 오류 개체 Errors 컬렉션에 배치 됩니다. (일반적으로 하나의 오류 개체가 컬렉션에 포함 합니다; 더 여러 오류 개체를 가져올 수 있는 ODBC 데이터 소스를 사용 하는 경우) 다른 DAO 작업에 오류가 발생 하는 경우 Errors 컬렉션의 선택을 취소 하 고 새 오류 개체는 Errors 컬렉션에 배치 됩니다. 오류를 생성 하지 않는 DAO 작업은 Errors 컬렉션에는 효과가 없습니다.  
  
 DAO 오류 코드 DAOERR 파일을 참조 하십시오.&8;. 관련된 정보를 잡을 수 있는 데이터 액세스의 "오류" DAO 도움말 항목을 참조 하십시오.  
  
 일반 또는 정보에서 예외 처리에 대 한 자세한 내용은 `CDaoException` 문서를 참조 하는 개체를 [예외 처리 (MFC)](../../mfc/exception-handling-in-mfc.md) 및 [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다. 두 번째 기사는 DAO의 예외 처리를 보여 주는 예제 코드를 포함 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
##  <a name="a-namecdaoexceptiona--cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDaoException::CDaoException  
 `CDaoException` 개체를 생성합니다.  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>주의  
 일반적으로 프레임 워크는 해당 코드가 예외를 throw 하는 경우 예외 개체를 만듭니다. 대부분의 경우는 예외 개체를 명시적으로 생성 해야 합니다. throw 하려는 경우는 `CDaoException` 사용자 고유의 코드에서 전역 함수를 호출 [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception)합니다.  
  
 DAO MFC 클래스를 캡슐화 하는 DAO 인터페이스 포인터를 통해 직접 호출 하는 경우는 예외 개체를 명시적으로 만들 수도 있습니다. 이 경우 DAO에서 오류 정보를 검색 해야 합니다. 작업 영역 데이터베이스 컬렉션에 DAODatabases 인터페이스를 통해 DAO 메서드를 호출할 때 DAO에서 오류가 발생을 가정 합니다.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>DAO 오류 정보를 검색 하려면  
  
1.  생성 된 `CDaoException` 개체입니다.  
  
2.  예외 개체의 호출 [GetErrorCount](#geterrorcount) 멤버 함수를 데이터베이스 엔진의 오류 컬렉션에 있는 오류 개체의 수를 확인 합니다. (일반적으로 하나만 ODBC 데이터 소스를 사용 하는 제외 합니다.)  
  
3.  예외 개체의 호출 [GetErrorInfo](#geterrorinfo) 멤버 함수는 예외 개체를 통해 컬렉션에서 인덱스에 의해 한 번에 하나의 특정 오류 개체를 검색 합니다. 예외 개체의 한 DAO error 개체에 대 한 프록시 생각 합니다.  
  
4.  현재 검사 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조체 `GetErrorInfo` 에서 반환 된 [m_pErrorInfo](#m_perrorinfo) 데이터 멤버. 해당 멤버는 DAO 오류에 정보를 제공합니다.  
  
5.  ODBC 데이터 원본으로의 경우 3, 4 더 많은 오류 개체에 대 한 필요에 따라 단계를 반복 합니다.  
  
6.  힙에 예외 개체를 생성 한 경우에 사용 하 여 삭제는 **삭제** 작업을 마치면 연산자입니다.  
  
 MFC DAO 클래스에서 오류를 처리 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
##  <a name="a-namegeterrorcounta--cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>CDaoException::GetErrorCount  
 데이터베이스 엔진의 오류 컬렉션에 추가 DAO error 개체의 수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>반환 값  
 데이터베이스 엔진의 오류 컬렉션에 있는 DAO 오류 개체의 수입니다.  
  
### <a name="remarks"></a>주의  
 이 정보는 각 컬렉션에 있는 하나 이상의 DAO 오류 개체를 검색 하는 오류 컬렉션을 반복 하는 데 유용 합니다. 를 검색 하려면 오류 개체 DAO 오류 번호 또는 인덱스에 의해 호출 된 [GetErrorInfo](#geterrorinfo) 멤버 함수입니다.  
  
> [!NOTE]
>  일반적으로 Errors 컬렉션에 하나의 오류 개체가 됩니다. 그러나 ODBC 데이터 원본으로 작업 하는 경우 있을 수 하나 이상 있습니다.  
  
##  <a name="a-namegeterrorinfoa--cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDaoException::GetErrorInfo  
 오류 컬렉션에 있는 특정 오류 개체에 대 한 오류 정보를 반환합니다.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스는 데이터베이스 엔진의 Errors 컬렉션에 있는 인덱스에 의해 조회에 대 한 오류 정보입니다.  
  
### <a name="remarks"></a>주의  
 다음과 같은 유형의 예외에 대 한 정보를 가져오려면이 함수를 호출 합니다.  
  
-   오류 코드  
  
-   소스  
  
-   설명  
  
-   도움말 파일  
  
-   도움말 컨텍스트  
  
 `GetErrorInfo`예외 개체에 정보를 저장 `m_pErrorInfo` 데이터 멤버입니다. 에 대 한 간략 한 설명은 반환 되는 정보를 참조 하십시오. [m_pErrorInfo](#m_perrorinfo)합니다. 형식의 예외를 catch 하는 경우 `CDaoException` MFC throw는 `m_pErrorInfo` 멤버 이미 입력 되어 있습니다. 예외 개체를 호출 해야 직접 DAO 호출 하려는 경우 `GetErrorInfo` 멤버 함수에 맞게 직접 `m_pErrorInfo`합니다. 에 대 한 자세한 내용은 참조는 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조입니다.  
  
 DAO 예외 및 예제 코드에 대 한 내용은 문서를 참조 하십시오. [예외: 데이터베이스 예외](../../mfc/exceptions-database-exceptions.md)합니다.  
  
##  <a name="a-namemnafxdaoerrora--cdaoexceptionmnafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDaoException::m_nAfxDaoError  
 오류 코드를 확장 하는 MFC에 포함 되어 있습니다.  
  
### <a name="remarks"></a>주의  
 이 코드는 MFC DAO 클래스의 특정 구성 요소를 잘못가 있는 경우에 제공 됩니다.  
  
 가능한 값은 다음과 같습니다.  
  
- **NO_AFX_DAO_ERROR** 확장 오류는 MFC 가장 최근 작업에서 발생 하지 않았습니다. 그러나 작업 수 나왔습니다. DAO 또는 OLE에서 다른 오류를 확인 해야 하므로 [m_pErrorInfo](#m_perrorinfo) 및 [m_scode](#m_scode)합니다.  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC Microsoft Jet 데이터베이스 엔진을 초기화 하지 못했습니다. OLE를 초기화 하지 못했을 수 또는 했을 수도 있습니다 하지 DAO 데이터베이스 엔진 개체의 인스턴스를 만들 수 있습니다. 이러한 문제는 일반적으로 잘못 설치 DAO 나 OLE를 제안합니다.  
  
- **AFX_DAO_ERROR_DFX_BIND** DAO 레코드 필드 교환 (DFX) 함수 호출에 사용 되는 주소 없거나 올바르지 않습니다 (주소에 데이터 바인딩하는 사용 되지 않았습니다)입니다. DFX 호출에서 잘못 된 주소를 전달 했습니다 수 또는 dfx 간의 잘못 된 주소가 될 수도 있습니다.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** 쿼리 정의 또는 열린 상태에 포함 되지 않은 테이블 정의 개체를 기반으로 레코드 집합을 열려고 했습니다.  
  
##  <a name="a-namemperrorinfoa--cdaoexceptionmperrorinfo"></a><a name="m_perrorinfo"></a>CDaoException::m_pErrorInfo  
 에 대 한 포인터를 포함 한 `CDaoErrorInfo` DAO 오류 개체를 호출 하 여 마지막으로 검색에 대 한 정보를 제공 하는 구조 [GetErrorInfo](#geterrorinfo)합니다.  
  
### <a name="remarks"></a>주의  
 이 개체에는 다음과 같은 정보가 포함 되어 있습니다.  
  
|CDaoErrorInfo 멤버|정보|의미|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|오류 코드|DAO 오류 코드|  
|`m_strSource`|소스|개체 또는 원래 오류를 생성 하는 응용 프로그램의 이름|  
|`m_strDescription`|설명|오류와 관련 된 설명 문자열|  
|`m_strHelpFile`|도움말 파일|사용자가 문제에 대 한 정보를 가져올 수 있는 Windows 도움말 파일에 대 한 경로|  
|**m_lHelpContext**|도움말 컨텍스트|DAO 도움말 파일의 항목에 대 한 컨텍스트 ID|  
  
 에 포함 된 정보에 대 한 자세한 내용은 `CDaoErrorInfo` 개체, 참조는 [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) 구조입니다.  
  
##  <a name="a-namemscodea--cdaoexceptionmscode"></a><a name="m_scode"></a>CDaoException::m_scode  
 형식의 값이 포함 된 `SCODE` 하는 오류를 설명 합니다.  
  
### <a name="remarks"></a>주의  
 OLE 코드입니다. 거의 모든 경우에 보다 구체적인 MFC 또는 DAO 오류 정보를 다른 때문에이 값을 사용 해야 거의 `CDaoException` 데이터 멤버입니다.  
  
 에 대 한 내용은 `SCODE`, 항목을 참조 [구조의 OLE 오류 코드](http://msdn.microsoft.com/library/windows/desktop/ms690088) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. `SCODE` 데이터 형식에 매핑되는 `HRESULT` 데이터 형식입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CException 클래스](../../mfc/reference/cexception-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CException 클래스](../../mfc/reference/cexception-class.md)

