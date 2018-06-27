---
title: CDaoQueryDefInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a31928bc98b8b2fd403f1db40c040357c388b104
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952289"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 구조체
`CDaoQueryDefInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 쿼리 정의 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoQueryDefInfo  
{  
    CString m_strName;               // Primary  
    short m_nType;   // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    BOOL m_bUpdatable;               // Secondary  
    BOOL m_bReturnsRecords;          // Secondary  
    CString m_strSQL;                // All  
    CString m_strConnect;            // All  
    short m_nODBCTimeout;            // All  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *m_strName*  
 쿼리 정의 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다. 호출 [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 를이 속성을 직접 검색 합니다.  
  
 *m_nType*  
 쿼리 정의 개체의 작업 유형을 나타내는 값입니다. 값은 다음 중 하나일 수 있습니다.  
  
- **dbQSelect** 선택-쿼리 레코드를 선택 합니다.  
  
- **dbQAction** 동작-쿼리 이동 하거나 데이터를 변경 하지만 레코드를 반환 하지 않습니다.  
  
- **dbQCrosstab** 크로스탭-쿼리는 스프레드시트 형식으로 데이터를 반환 합니다.  
  
- **dbQDelete** 삭제-쿼리에 지정 된 행 집합을 삭제 합니다.  
  
- **dbQUpdate** 업데이트-쿼리가 레코드 집합을 변경 합니다.  
  
- **dbQAppend** Append-쿼리는 테이블 또는 쿼리의 끝에 새 레코드를 추가 합니다.  
  
- **dbQMakeTable** 테이블 만들기 — 쿼리에서 레코드 집합에서 새 테이블을 만듭니다.  
  
- **dbQDDL** 데이터 정의-쿼리에서 테이블이 나 해당 파트의 구조에 영향을 줍니다.  
  
- **dbQSQLPassThrough** 통과-SQL 문을 데이터베이스 백 엔드가 중간 처리 하지 않고 직접 전달 됩니다.  
  
- **dbQSetOperation** 공용 구조체-중복 된 레코드를 자세한 테이블 제거 또는 쿼리에서 두 지정 된 모든 레코드에서에서 데이터를 포함 하는 스냅숏 형식 recordset 개체를 만듭니다. 중복 값을 포함 하려면 키워드를 추가 **모든** 쿼리 정의 SQL 문에 합니다.  
  
- **dbQSPTBulk** 사용한 **dbQSQLPassThrough** 레코드를 반환 하지 않는 쿼리를 지정 합니다.  
  
> [!NOTE]
>  SQL 통과 쿼리를 만들려면 설정 하지 않으면는 **dbQSQLPassThrough** 상수입니다. 이 설정은 자동으로 Microsoft Jet 데이터베이스 엔진에 의해 쿼리 정의 개체를 만들고 연결 속성을 설정 합니다.  
  
 자세한 내용은 DAO 도움말의 "Type 속성" 항목을 참조 합니다.  
  
 *m_dateCreated*  
 날짜 및 쿼리 정의 만든 시간입니다. 직접 쿼리 정의 만든 날짜를 검색 하려면 호출는 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 의 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하십시오. DAO 도움말의 항목 "DateCreated LastUpdated 속성"를 참조 하세요.  
  
 *m_dateLastUpdated*  
 날짜 및 시간을 가장 최근 쿼리 정의에 적용 한 변경입니다. 테이블을 마지막으로 수정한 날짜를 직접 검색 하려면 호출는 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) 쿼리 정의의 멤버 함수입니다. 자세한 내용은 아래 메모를 참조 하십시오. 고 DAO 도움말의 "LastUpdated 속성 DateCreated" 항목을 참조 하십시오.  
  
 *m_bUpdatable*  
 변경 내용을 쿼리 정의 개체를 연결할 수 있는지 여부를 나타냅니다. 이 속성이 **TRUE**, 쿼리 정의 업데이트할 수 있는, 그렇지 않으면, 없습니다. 업데이트 가능 쿼리 정의 개체의 쿼리 정의 변경할 수 있습니다를 의미 합니다. 업데이트할 수 있는 쿼리 정의 개체의 속성이 **TRUE** 경우 쿼리 정의 업데이트 결과 레코드 집합을 업데이트할 수 없는 경우에 합니다. 이 속성을 직접 검색 하려면 쿼리 정의 호출 [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "업데이트할 수 있는 Property" 항목을 참조 합니다.  
  
 *m_bReturnsRecords*  
 외부 데이터베이스에는 SQL 통과 쿼리의 레코드를 반환 하는지 여부를 나타냅니다. 이 속성이 **TRUE**, 쿼리 레코드를 반환 합니다. 이 속성을 직접 검색 하려면 호출 [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)합니다. 모든 SQL 통과 쿼리 외부 데이터베이스에 레코드를 반환 합니다. 예를 들어 SQL **업데이트** SQL 동안 레코드를 반환 하지 않고 레코드를 업데이트 하는 문을 **선택** 문에 레코드를 반환 합니다. 자세한 내용은 DAO 도움말의 "ReturnsRecords Property" 항목을 참조 하십시오.  
  
 *m_strSQL*  
 쿼리 정의 개체에 의해 실행 되는 쿼리를 정의 하는 SQL 문입니다. 레코드 선택 방법, 그룹화 및 정렬 쿼리를 실행 하는 경우를 결정 하는 SQL 문을 포함 하는 SQL 속성입니다. 다이너셋 또는 스냅숏 형식 레코드 집합 개체에 포함할 레코드를 선택 하는 쿼리를 사용할 수 있습니다. 대량 레코드를 반환 하지 않고 데이터를 수정 하는 쿼리를 정의할 수 있습니다. 직접 쿼리 정의 호출 하 여이 속성의 값을 검색할 수 있습니다 [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) 멤버 함수입니다.  
  
 *m_strConnect*  
 통과 쿼리에 사용 되는 데이터베이스의 원본에 대 한 정보를 제공 합니다. 이 정보는 연결 문자열의 형식을 사용 합니다. 자세한 정보에 대 한 연결 문자열을 한이 속성의 값을 직접 검색 하는 방법에 대 한 정보를 참조 하십시오.는 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) 멤버 함수입니다.  
  
 *m_nODBCTimeout*  
 초를 대기한 후 시간 초과 오류가 Microsoft Jet 데이터베이스 엔진에는 ODBC 데이터베이스에서 쿼리를 실행할 때 발생 합니다. Microsoft SQL Server와 같은 ODBC 데이터베이스에서 사용 하는 경우에 ODBC 서버의 네트워크 트래픽 또는 중형 사용량이 지연이 나타날 수 있습니다. 무기한 대기 하는 대신 Microsoft Jet 엔진 오류가 발생 하기 전에 대기 하는 시간을 지정할 수 있습니다. 기본 제한 시간 값은 60 초입니다. 직접 쿼리 정의 호출 하 여이 속성의 값을 검색할 수 있습니다 [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "ODBCTimeout Property" 항목을 참조 하십시오.  
  
## <a name="remarks"></a>설명  
 쿼리 정의 클래스의 개체 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 주, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 클래스에서 멤버 함수 `CDaoDatabase`합니다.  
  
 검색 한 정보는 [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) 멤버 함수에 저장 되는 `CDaoQueryDefInfo` 구조입니다. 호출 `GetQueryDefInfo` 인 QueryDefs 컬렉션 querydef 개체 저장 된 데이터베이스 개체에 대 한 합니다. `CDaoQueryDefInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoQueryDefInfo` 개체입니다. 클래스 `CDaoDatabase` 직접 모두에서 반환 되는 속성에 액세스 하기 위한 멤버 함수를 제공 하는 또한는 `CDaoQueryDefInfo` 되므로 호출할 필요가 거의 아마도 개체 `GetQueryDefInfo`합니다.  
  
 쿼리 정의 개체의 필드 또는 매개 변수 컬렉션에 새 필드 또는 매개 변수 개체를 추가 하는 경우 기본 데이터베이스에 새 개체에 대해 지정 된 데이터 형식을 지원 하지 않는 경우 예외가 throw 됩니다.  
  
 날짜 및 시간 설정에는 쿼리 정의 만들었거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 얻어야 이러한 설정을 사용 하 여 파일 서버에서 직접는 **시간 net** DateCreated 및 LastUpdated 속성 설정에서 불일치를 방지 하기 위해 명령입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)
