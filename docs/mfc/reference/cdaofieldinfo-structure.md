---
title: CDaoFieldInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63fdab9bae7238f427ff2015beffd53570603af4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 구조체
`CDaoFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 field 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 Field 개체를 이름을 고유 하 게 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 `m_nType`  
 필드의 데이터 형식을 나타내는 값입니다. 자세한 내용은 DAO 도움말의 "Type 속성" 항목을 참조 합니다. 이 속성의 값은 다음 중 하나일 수 있습니다.  
  
- **dbBoolean** Yes/No 동일 **TRUE**/**FALSE**  
  
- **dbByte** 바이트  
  
- **dbInteger** 짧은  
  
- **dbLong** 긴  
  
- **dbCurrency** 통화; 참조 MFC 클래스 [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle** 단일  
  
- **dbDouble** Double  
  
- **dbDate** 날짜/시간; 참조 MFC 클래스 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText** 텍스트 이거나, 이러한 참조 MFC 클래스 [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary** 긴 이진 (OLE 개체); MFC 클래스를 사용 하려는 경우도 [CByteArray](../../mfc/reference/cbytearray-class.md) 클래스 대신 `CLongBinary` 으로 `CByteArray` 풍부 하 고 보다 쉽게 사용할 수 있습니다.  
  
- **dbMemo** 메모; 참조 MFC 클래스`CString`  
  
- **dbGUID** A 전역 고유 식별자/범용 고유 식별자 원격 프로시저 호출에 사용 합니다. 자세한 내용은 DAO 도움말의 "Type 속성" 항목을 참조 합니다.  
  
> [!NOTE]
>  이진 데이터에 대 한 문자열 데이터 형식을 사용 하지 마십시오. 이렇게 하면 오버 헤드가 증가 하 고 예상치 못한 변환으로 인해 발생 하는 유니코드/ANSI 변환 계층을 통해 전달할 데이터입니다.  
  
 *m_lSize*  
 최대 크기 (바이트)를 텍스트 또는 텍스트 또는 숫자 값을 포함 하는 필드 개체의 고정된 크기를 포함 하는 DAO 필드 개체를 나타내는 값입니다. 자세한 내용은 DAO 도움말의 "크기 Property" 항목을 참조 합니다. 크기는 다음 값 중 하나일 수 있습니다.  
  
|형식|크기(바이트)|설명|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1바이트|예/아니요 (True/False와 같음)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|정수|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|통화 ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|날짜/시간 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|텍스트 ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|긴 이진 (OLE 개체입니다. [CByteArray](../../mfc/reference/cbytearray-class.md); 대신 사용 하 여 `CLongBinary`)|  
|**dbMemo**|0|메모 ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|전역적으로 고유 식별자/범용 고유 식별자 원격 프로시저 호출에 사용 합니다.|  
  
 `m_lAttributes`  
 테이블 정의 레코드 집합, 쿼리 또는 인덱스 개체에 포함 된 field 개체의 특성을 지정 합니다. 반환 되는 값이이 상수를 비트 OR는 c + +를 사용 하 여 만든 총 수 (**&#124;**) 연산자:  
  
- **dbFixedField** 필드 크기 (숫자 필드에 대 한 기본값)를 고정 됩니다.  
  
- **dbVariableField** 필드 크기는 변수 (텍스트 필드에만 해당).  
  
- **dbAutoIncrField** 새 레코드에 대 한 필드 값이 고유한 정수 (long) 변경할 수 없는 자동으로 증가 됩니다. Microsoft Jet 데이터베이스 테이블에 대해서만 지원 합니다.  
  
- **dbUpdatableField** 필드 값을 변경할 수 있습니다.  
  
- **dbDescending** 필드가를 내림차순으로 정렬 됩니다 (A-Z 또는 100-0) 순서 (field 개체의 인덱스 개체의 필드 컬렉션, MFC, 개체 자체 테이블 정의 개체에 포함 된 인덱스에만 적용 됨). 이 상수를 생략 하면 필드를 오름차순으로 정렬 됩니다 (A-Z 또는 0-100) 순서 (기본값).  
  
 이 속성의 설정은 검사할 때 사용할 수 있습니다는 c + + 비트-및 연산자 (**&**) 특정 특성에 대 한 테스트 합니다. 여러 특성을 설정할 때 적절 한 상수는 비트 OR 조합 하 여 결합 수 있습니다 (**&#124;**) 연산자. 자세한 내용은 DAO 도움말의 "특성 Property" 항목을 참조 합니다.  
  
 *m_nOrdinalPosition*  
 다른 필드를 기준으로 표시 되는 DAO 필드 개체를 나타내는 필드 숫자 순서를 지정 하는 값입니다. 이 속성을 설정할 수 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다. 자세한 내용은 DAO 도움말의 "OrdinalPosition Property" 항목을 참조 합니다.  
  
 `m_bRequired`  
 DAO field 개체는 Null이 아닌 값을 필요한 지 여부를 나타냅니다. 이 속성이 **TRUE**, 필드는 Null 값을 허용 하지 않습니다. 로 설정 되어 필요한 경우 **FALSE**, AllowZeroLength 및 유효성 검사 규칙 속성 설정에 지정 된 조건을 만족 하는 값은 물론 Null 값 필드에 사용할 수 있습니다. 자세한 내용은 DAO 도움말의 "필수 속성" 항목을 참조 하십시오. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 *m_bAllowZeroLength*  
 나타냅니다 있는지 여부를 빈 문자열 ("")는 DAO 필드 개체를 사용 하는 텍스트 또는 메모 데이터 형식과 유효한 값이 있습니다. 이 속성이 **TRUE**, 빈 문자열은 유효한 값입니다. 이 속성 설정할 수 있습니다 **FALSE** 필드의 값을 설정 하려면 빈 문자열을 사용할 수 없습니다. 자세한 내용은 DAO 도움말의 "AllowZeroLength Property" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 `m_lCollatingOrder`  
 문자열 비교 또는 정렬에 대 한 텍스트 정렬 순서를 지정 합니다. 자세한 내용은 "사용자 지정 Windows 레지스트리 설정에 대 한 데이터 액세스" DAO 도움말의 항목을 참조 합니다. 목록이 반환 되는 가능한 값에 대 한 참조는 **m_lCollatingOrder** 의 멤버는 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) 구조입니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 `m_strForeignName`  
 관계, 기본 테이블에 있는 필드에 해당 하는 외래 테이블의 DAO field 개체의 이름을 지정 하는 값입니다. 자세한 내용은 DAO 도움말의 "ForeignName Property" 항목을 참조 합니다.  
  
 *m_strSourceField*  
 Field 개체 DAO tabledef, 레코드 집합 또는 querydef 개체에 포함 된 데이터 필드의 이름을 나타냅니다. 이 속성은 field 개체와 연결 된 원래 필드 이름을 나타냅니다. 예를 들어 원본 테이블에 필드의 이름을 관련이 없을 쿼리 필드에 있는 데이터의 원본 소스를 확인 하려면이 속성을 사용할 수 있습니다. 세부 정보를 DAO 도움말의 "원본 필드, SourceTable 속성" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 *m_strSourceTable*  
 Field 개체 DAO tabledef, 레코드 집합 또는 querydef 개체에 포함 된 데이터 테이블의 이름을 나타냅니다. 이 속성은 field 개체와 연결 된 원본 테이블 이름을 나타냅니다. 예를 들어 원본 테이블에 필드의 이름을 관련이 없을 쿼리 필드에 있는 데이터의 원본 소스를 확인 하려면이 속성을 사용할 수 있습니다. 세부 정보를 DAO 도움말의 "원본 필드, SourceTable 속성" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 `m_strValidationRule`  
 이 변경 되거나 테이블에 추가 되는 필드의 데이터 유효성을 검사 하는 값입니다. 자세한 내용은 DAO 도움말의 "ValidationRule Property" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 테이블 정의 대 한 관련된 정보에 대 한 참조는 **m_strValidationRule** 의 멤버는 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) 구조입니다.  
  
 `m_strValidationText`  
 DAO 필드 개체의 값은 유효성 검사 규칙 속성 설정으로 지정 된 유효성 검사 규칙을 충족 하지 않으면 응용 프로그램에서 표시 하는 메시지의 텍스트를 지정 하는 값입니다. 자세한 내용은 DAO 도움말의 "유효성 검사 텍스트 Property" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
 *m_strDefaultValue*  
 DAO field 개체의 기본값입니다. 새 레코드를 만들면 DefaultValue 속성 설정이 자동으로 입력 값으로 필드에 대 한 합니다. 자세한 내용은 DAO 도움말의 "DefaultValue Property" 항목을 참조 합니다. 와 테이블 정의 대 한이 속성을 설정할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)합니다.  
  
## <a name="remarks"></a>설명  
 주, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 `GetFieldInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), 및 [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)합니다.  
  
 Field 개체는 MFC 클래스에 의해 표시 되지 않습니다. MFC 개체는 다음 클래스는 DAO 개체 필드 개체의 컬렉션을 포함 하는 대신,: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), 및 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)합니다. 이러한 클래스의 필드 정보를 일부 개별 항목에 액세스 하는 멤버 함수를 제공 하거나 인수를 한 번에 모두를 사용 하 여 액세스할 수 있습니다는 `CDaoFieldInfo` 호출 하 여 개체는 `GetFieldInfo` 포함 하는 개체의 멤버 함수입니다.  
  
 개체 속성을 검사 하기 위한 용도 외에도 사용할 수도 있습니다 `CDaoFieldInfo` 테이블 정의에서 새 필드를 만들기 위한 입력된 매개 변수를 생성 합니다. 간단한 옵션은이 작업을 사용할 수 있지만 보다 세부적으로 제어 하려는 경우에의 버전을 사용할 수 있습니다 [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) 를 사용 하는 `CDaoFieldInfo` 매개 변수입니다.  
  
 검색 한 정보는 `GetFieldInfo` (필드를 포함 하는 클래스)의 멤버 함수에 저장 되는 `CDaoFieldInfo` 구조입니다. 호출 된 `GetFieldInfo` 필드 개체가 보관 되어 있는 Fields 컬렉션에 포함 하는 개체의 멤버 함수입니다. `CDaoFieldInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoFieldInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

