---
title: CDaoTableDefInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80c1422c4d0e45599ca8bc2e9c86a4263b8ac9b6
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955611"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 구조체
`CDaoTableDefInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 테이블 정의 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *m_strName*  
 고유 하 게 테이블 정의 개체의 이름을 지정 합니다. 이 속성의 값을 직접 검색 하 여 테이블 정의 개체를 호출 [GetName](../../mfc/reference/cdaotabledef-class.md#getname) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 *m_bUpdatable*  
 테이블에 변경 내용을 만들 수 있는지 여부를 나타냅니다. 열려는 테이블을 업데이트할 수 있는지 여부를 확인 하는 빠른 방법은는 `CDaoTableDef` 테이블에 대 한 개체와 개체의 호출 [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) 멤버 함수입니다. `CanUpdate` 항상 0이 아닌 값을 반환 합니다 (**TRUE**) tabledef 새로 만든된 개체 및 0에 대 한 (**FALSE**) 연결 된 테이블 정의 개체에 대 한 합니다. 새 테이블 정의 개체는 현재 사용자에 대 한 쓰기 권한이 있는 데이터베이스에만 추가할 수 있습니다. 테이블에만 업데이트할 수 없는 필드가 포함 하는 경우 `CanUpdate` 0을 반환 합니다. 하나 이상의 필드를 업데이트할 수, `CanUpdate` 0이 아닌 값을 반환 합니다. 업데이트할 수 있는 필드에만 편집할 수 있습니다. 자세한 내용은 DAO 도움말의 "업데이트할 수 있는 Property" 항목을 참조 합니다.  
  
 *m_lAttributes*  
 테이블 정의 개체로 표시 된 테이블의 특성을 지정 합니다. 테이블 정의의 현재 속성을 검색 하려면 해당 [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) 멤버 함수입니다. 반환 되는 값이 긴 상수의 조합 수 (비트 OR를 사용 하 여 (**&#124;**) 연산자).  
  
- **dbAttachExclusive** Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 테이블은 배타적으로 사용에 대 한 열린 연결된 된 테이블을 나타냅니다.  
  
- **dbAttachSavePWD** 나타냅니다 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스, 사용자 ID와 연결 된 테이블에 대 한 암호는 연결 정보가 저장 됩니다.  
  
- **dbSystemObject** Microsoft Jet 데이터베이스 엔진에서 제공 하는 시스템 테이블은 해당 테이블이 나타냅니다. 읽기 전용입니다.  
  
- **dbHiddenObject** (임시 사용 하 여에) 대 한 Microsoft Jet 데이터베이스 엔진에서 제공 하는 숨겨진된 테이블은 해당 테이블이 나타냅니다. 읽기 전용입니다.  
  
- **dbAttachedTable** Paradox 데이터베이스와 같은 비 ODBC 데이터베이스에서 연결된 된 테이블은 해당 테이블이 나타냅니다.  
  
- **dbAttachedODBC** 에서 Microsoft SQL Server와 같은 ODBC 데이터베이스 연결된 된 테이블은 해당 테이블이 나타냅니다.  
  
 *m_dateCreated*  
 날짜 및 테이블을 만든 시간입니다. 테이블을 만든 날짜를 직접 검색 하려면 호출는 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) 의 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하십시오. 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
 *m_dateLastUpdated*  
 날짜 및 시간을 테이블의 디자인에 대 한 가장 최근의 변경입니다. 테이블을 마지막으로 수정한 날짜를 직접 검색 하려면 호출는 [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) 의 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 자세한 내용은 아래 메모를 참조 하십시오. 관련된 내용은 DAO 도움말의 "DateCreated LastUpdated 속성" 항목을 참조 합니다.  
  
 *m_strSrcTableName*  
 있는 경우 연결된 된 테이블의 이름을 지정 합니다. 원본 테이블 이름을 직접 검색 하려면 호출는 [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) 의 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다.  
  
 *m_strConnect*  
 열려 있는 데이터베이스의 원본에 대 한 정보를 제공 합니다. 호출 하 여이 속성을 확인할 수 있습니다는 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) 의 멤버 함수에 `CDaoTableDef` 개체입니다. 에 대 한 자세한 정보에 대 한 연결 문자열, 참조 `GetConnect`합니다.  
  
 *m_strValidationRule*  
 변경 되거나 테이블에 추가 될 때 테이블 정의 필드의 데이터 유효성을 검사 하는 값입니다. 유효성 검사는 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대해서만 지원 됩니다. 유효성 검사 규칙을 직접 검색 하려면 호출는 [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) 의 멤버 함수는 `CDaoTableDef` 테이블에 연결 된 개체입니다. 관련된 정보에 대 한 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다.  
  
 *m_strValidationText*  
 유효성 검사 규칙 속성에 지정 된 유효성 검사 규칙을 충족 되지 않는 경우 응용 프로그램을 표시 하는 메시지의 텍스트를 지정 하는 값입니다. 관련된 정보에 대 한 DAO 도움말의 "유효성 검사 텍스트 Property" 항목을 참조 합니다.  
  
 *m_lRecordCount*  
 테이블 정의 개체에 액세스 하는 레코드의 수입니다. 이 속성 설정은 읽기 전용입니다. Record count를 직접 검색 하려면 호출는 [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) 의 멤버 함수는 `CDaoTableDef` 개체입니다. 에 대 한 설명서 `GetRecordCount` 레코드 수를 더 이상에 대해 설명 합니다. 이 개수를 검색 수 있음을 시간이 많이 걸리는 작업 테이블에 있는 경우 여러 레코드가 note 합니다.  
  
## <a name="remarks"></a>설명  
 테이블 정의 클래스의 개체 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)합니다. 주, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) 클래스에서 멤버 함수 `CDaoDatabase`합니다.  
  
 검색 한 정보는 [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) 멤버 함수에 저장 되는 `CDaoTableDefInfo` 구조입니다. 호출 된 `GetTableDefInfo` 의 멤버 함수는 `CDaoDatabase` 테이블 정의 개체는 저장 된 해당 TableDefs 컬렉션 개체입니다. `CDaoTableDefInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoTableDefInfo` 개체입니다.  
  
 날짜 및 시간 설정에 기본 테이블을 만들거나 마지막으로 업데이트 하는 컴퓨터에서 파생 됩니다. 다중 사용자 환경에서 사용자가 이러한는 DateCreated에서 불일치를 방지 하기 위해 파일 서버에서 직접 설정 및 LastUpdated 속성 설정을 받아야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef 클래스](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase 클래스](../../mfc/reference/cdaodatabase-class.md)
