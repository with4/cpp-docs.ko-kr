---
title: "CDBVariant 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class
- Variant data types, ODBC
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
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
ms.openlocfilehash: 930115ce4fe673e82a447ab1d90c260fe2b941d6
ms.lasthandoff: 02/24/2017

---
# <a name="cdbvariant-class"></a>CDBVariant 클래스
MFC ODBC 클래스의 variant 데이터 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|`CDBVariant` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|지웁니다는 `CDBVariant` 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|현재 저장 된 값의 데이터 형식을 포함합니다. `DWORD`를 입력합니다.|  
  
### <a name="public-union-members"></a>공용 공용 구조체 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|형식의 값이 포함 된 **BOOL**합니다.|  
|[CDBVariant::m_chVal](#m_chval)|형식의 값이 포함 된 `unsigned char`합니다.|  
|[CDBVariant::m_dblVal](#m_dblval)|형식의 값이 포함 된 **이중**합니다.|  
|[CDBVariant::m_fltVal](#m_fltval)|형식의 값이 포함 된 **float**합니다.|  
|[CDBVariant::m_iVal](#m_ival)|형식의 값이 포함 된 **짧은**합니다.|  
|[CDBVariant::m_lVal](#m_lval)|형식의 값이 포함 된 **긴**합니다.|  
|[CDBVariant::m_pbinary](#m_pbinary)|형식의 개체에 대 한 포인터 `CLongBinary`합니다.|  
|[CDBVariant::m_pdate](#m_pdate)|형식의 개체에 대 한 포인터 **TIMESTAMP_STRUCT**합니다.|  
|[CDBVariant::m_pstring](#m_pstring)|형식의 개체에 대 한 포인터 `CString`합니다.|  
|[CDBVariant::m_pstringA](#m_pstringa)|ASCII에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|  
|[CDBVariant::m_pstringW](#m_pstringw)|한 차원에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `CDBVariant`기본 클래스는 없습니다.  
  
 `CDBVariant`유사한 [COleVariant](../../mfc/reference/colevariant-class.md); 그러나 `CDBVariant` OLE를 사용 하지 않습니다. `CDBVariant`값의 데이터 형식에 대 한 걱정 없이 값을 저장할 수 있습니다. `CDBVariant`데이터 형식의 공용 구조체에 저장 된 현재 값을 추적 합니다.  
  
 클래스 [CRecordset](../../mfc/reference/crecordset-class.md) 활용 `CDBVariant` 의 세 멤버 함수가 개체: `GetFieldValue`, `GetBookmark`, 및 `SetBookmark`합니다. 예를 들어 `GetFieldValue` 동적으로 열에에서 데이터를 가져올 수 있습니다. 런타임 시 데이터 형식의 열을 알 수 있습니다 `GetFieldValue` 사용 하는 `CDBVariant` 열 데이터를 저장할 개체입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDBVariant`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdb.h  
  
##  <a name="cdbvariant"></a>CDBVariant::CDBVariant  
 NULL 만듭니다 `CDBVariant` 개체입니다.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>주의  
 설정의 [m_dwType](#m_dwtype) 데이터 멤버를 **DBVT_NULL**합니다.  
  
##  <a name="clear"></a>CDBVariant::Clear  
 이 멤버 함수를 지우려면 호출는 `CDBVariant` 개체입니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 하는 경우의 값은 [m_dwType](#m_dwtype) 데이터 멤버는 **DBVT_DATE**, **DBVT_STRING**, 또는 **DBVT_BINARY**, **지우기** union 포인터 멤버와 연결 된 메모리를 해제 합니다. **지우기** 설정 `m_dwType` 를 **DBVT_NULL**합니다.  
  
 `CDBVariant` 소멸자 호출 **지우기**합니다.  
  
##  <a name="m_boolval"></a>CDBVariant::m_boolVal  
 형식의 값을 저장 **BOOL**합니다.  
  
### <a name="remarks"></a>주의  
 **m_boolVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_boolVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_BOOL**, 다음 **m_boolVal** 유효한 값이 포함 됩니다; 그렇지 않으면 액세스 **m_boolVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_chval"></a>CDBVariant::m_chVal  
 형식의 값을 저장 `unsigned char`합니다.  
  
### <a name="remarks"></a>주의  
 **m_chVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_chVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_UCHAR**, 다음 **m_chVal** 올바른 값을 포함 합니다; 그렇지 않으면 액세스 **m_chVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_dblval"></a>CDBVariant::m_dblVal  
 형식의 값을 저장 **이중**합니다.  
  
### <a name="remarks"></a>주의  
 **m_dblVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_dblVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_DOUBLE**, 다음 **m_dblVal** 올바른 값을 포함 합니다; 그렇지 않으면 액세스 **m_dblVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_dwtype"></a>CDBVariant::m_dwType  
 이 데이터 멤버에 현재 저장 된 값에 대 한 데이터 형식이 포함 된 `CDBVariant` 개체의 공용 데이터 멤버입니다.  
  
### <a name="remarks"></a>주의  
 이 공용 구조체에 대 한 액세스를 하기 전에 값을 확인 해야 `m_dwType` 공용 데이터 멤버에 액세스를 결정 하기 위해. 다음 표에서 가능한 값에 대 한 `m_dwType` 하 고 해당 공용 구조체 데이터 멤버입니다.  
  
|m_dwType|공용 데이터 멤버|  
|---------------|-----------------------|  
|**DBVT_NULL**|공용 구조체 멤버 액세스에 대 한 유효합니다.|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>CDBVariant::m_fltVal  
 형식의 값을 저장 **float**합니다.  
  
### <a name="remarks"></a>주의  
 **m_fltVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_fltVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_SINGLE**, 다음 **m_fltVal** 올바른 값을 포함 합니다; 그렇지 않으면 액세스 **m_fltVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_ival"></a>CDBVariant::m_iVal  
 형식의 값을 저장 **짧은**합니다.  
  
### <a name="remarks"></a>주의  
 **m_iVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_iVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_SHORT**, 다음 **m_iVal** 올바른 값을 포함 합니다; 그렇지 않으면 액세스 **m_iVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_lval"></a>CDBVariant::m_lVal  
 형식의 값을 저장 **긴**합니다.  
  
### <a name="remarks"></a>주의  
 **m_lVal** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_lVal**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_LONG**, 다음 **m_lVal** 올바른 값을 포함 합니다; 그렇지 않으면 액세스 **m_lVal** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_pbinary"></a>CDBVariant::m_pbinary  
 형식의 개체에 대 한 포인터를 저장 [CLongBinary](../../mfc/reference/clongbinary-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 **m_pbinary** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_pbinary**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_BINARY**, 다음 **m_pbinary** 유효한 포인터를 포함 합니다; 그렇지 않으면 액세스 **m_pbinary** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_pdate"></a>CDBVariant::m_pdate  
 형식의 개체에 대 한 포인터를 저장 **TIMESTAMP_STRUCT**합니다.  
  
### <a name="remarks"></a>주의  
 **m_pdate** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_pdate**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_DATE**, 다음 **m_pdate** 유효한 포인터를 포함 합니다; 그렇지 않으면 액세스 **m_pdate** 안정적이 지 않은 결과 생성 합니다.  
  
 에 대 한 자세한 내용은 **TIMESTAMP_STRUCT** 항목을 참조 데이터 형식, [C 데이터 형식은](https://msdn.microsoft.com/library/ms714556.aspx) 의 부록 D에는 *ODBC 프로그래머 참조* 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="m_pstring"></a>CDBVariant::m_pstring  
 형식의 개체에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md)합니다.  
  
### <a name="remarks"></a>주의  
 **m_pstring** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_pstring**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_STRING**, 다음 **m_pstring** 유효한 포인터를 포함 합니다; 그렇지 않으면 액세스 **m_pstring** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_pstringa"></a>CDBVariant::m_pstringA  
 ASCII에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 **m_pstringA** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_pstringA**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_ASTRING**, 다음 **m_pstringA** 유효한 포인터를 포함 합니다; 그렇지 않으면 액세스 **m_pstringA** 안정적이 지 않은 결과 생성 합니다.  
  
##  <a name="m_pstringw"></a>CDBVariant::m_pstringW  
 한 차원에 대 한 포인터를 저장 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 **m_pstringW** 데이터 멤버는 공용 구조체에 속합니다. 에 액세스 하기 전에 **m_pstringW**의 값을 먼저 확인 [CDBVariant::m_dwType](#m_dwtype)합니다. 경우 `m_dwType` 로 설정 된 **DBVT_WSTRING**, 다음 **m_pstringW** 유효한 포인터를 포함 합니다; 그렇지 않으면 액세스 **m_pstringW** 안정적이 지 않은 결과 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRecordset 클래스](../../mfc/reference/crecordset-class.md)

