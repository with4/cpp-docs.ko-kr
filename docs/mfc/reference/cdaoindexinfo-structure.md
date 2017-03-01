---
title: "CDaoIndexInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
caps.latest.revision: 13
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
ms.openlocfilehash: 92206d8d8f9b2315fb859e2712a83d32a4c293ad
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 구조체
`CDaoIndexInfo` 구조에 데이터 액세스 개체 (DAO)에 대해 정의 된 인덱스 개체에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 Field 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 `m_pFieldInfos`  
 배열에 대 한 포인터 [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) tabledef 또는 레코드 집합 필드는 인덱스의 키 필드를 나타내는 개체입니다. 각 개체는 인덱스의 한 필드를 식별합니다. 기본 인덱스 순서는 오름차순입니다. Index 개체는 각 레코드에 대 한 인덱스 키를 나타내는 하나 이상의 필드를 가질 수 있습니다. 이러한 수 오름차순, 내림차순 또는 조합 합니다.  
  
 `m_nFields`  
 필드에 저장 된 수가 `m_pFieldInfos`합니다.  
  
 *m_bPrimary*  
 기본 속성이 **TRUE**, index 개체에는 기본 인덱스를 나타냅니다. 기본 인덱스는 미리 정의 된 순서에 따라 테이블의 모든 레코드를 고유 하 게 식별 하는 하나 이상의 필드로 구성 됩니다. Index 개체의 고유 속성 설정할 수도 인덱스 필드는 고유 해야 하기 때문에 **TRUE** dao에서 합니다. 기본 인덱스 둘 이상의 필드로 구성 된 경우 각 필드에 중복 값이 포함 될 수 있지만 인덱싱된 모든 필드에서 값의 각 조합은 고유 해야 합니다. 기본 인덱스를 테이블에 대 한 키 구성 되며 일반적으로 기본 키와 동일한 필드를 포함 합니다.  
  
 테이블에 대 한 기본 키를 설정 하면 기본 키 테이블에 대 한 기본 인덱스를 자동으로 이루어집니다. 자세한 내용은 "기본" 속성과 "고유 속성" DAO 도움말의 항목을 참조 합니다.  
  
> [!NOTE]
>  있을 수 있습니다, 최대 테이블에 대 한 기본 인덱스.  
  
 *m_bUnique*  
 Index 개체는 테이블에 대 한 고유 인덱스를 나타내는지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체에 있는 고유 인덱스를 나타냅니다. 고유 인덱스를 고유 하 고 미리 정의 된 순서에 따라 테이블의 모든 레코드를 논리적으로 정렬 하는 하나 이상의 필드를 이루어져 있습니다. 인덱스 하나의 필드로 구성 된 경우 해당 필드의 값이 전체 테이블에 대해 고유 해야 합니다. 인덱스가 둘 이상의 필드로 구성 된 경우 각 필드에 중복 값이 포함 될 수 있지만 인덱싱된 모든 필드에서 값의 각 조합은 고유 해야 합니다.  
  
 Unique 및 Primary 속성이 모두는 index 개체의 설정 된 경우 **TRUE**, 인덱스는 고유 하 고 기본: 미리 정의 된 논리적 순서로 테이블의 모든 레코드를 고유 하 게 식별 합니다. 기본 속성을로 설정 하는 경우 **FALSE**, 보조 인덱스입니다. 보조 인덱스 (키 및 키가 아닌) 테이블의 레코드에 대 한 식별자로 서비스를 제공 하지 않고 미리 정의 된 순서에 따라 레코드를 논리적으로 정렬 합니다.  
  
 자세한 내용은 "기본" 속성과 "고유 속성" DAO 도움말의 항목을 참조 합니다.  
  
 *m_bClustered*  
 Index 개체는 테이블에 대 한 클러스터형된 인덱스를 나타내는지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체 클러스터형된 인덱스를 나타냅니다; 그렇지 않으면 그렇지 않은 경우. 클러스터형된 인덱스를 하나 구성 되거나 이러한 필드는 더 많은 집합적, 전체적으로 볼 때, 미리 정의 된 순서에 따라 테이블의 모든 레코드를 정렬 합니다. 클러스터형된 인덱스가 있는 테이블의 데이터를 문자 그대로 클러스터형된 인덱스에 의해 지정 된 순서에 저장 됩니다. 클러스터형된 인덱스는 테이블의 레코드에 대 한 효율적인 액세스를 제공합니다. 자세한 내용은 DAO 도움말에서 "클러스터 속성" 항목을 참조 하십시오.  
  
> [!NOTE]
>  Clustered 속성은 Jet 데이터베이스 엔진에서 클러스터형된 인덱스를 지원 하지 않으므로 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대 한 무시 됩니다.  
  
 *m_bIgnoreNulls*  
 인덱스 필드에 Null 값이 포함 된 레코드에 대해 인덱스 항목이 있는지 여부를 나타냅니다. 이 속성이 **TRUE**, Null 값이 있는 필드에 있는 색인 항목 필요가 없습니다. 필드를 더 빠르게 사용 하 여 레코드를 검색 하는 필드에 대 한 인덱스를 정의할 수 있습니다. 인덱스 개체에 대 한 IgnoreNulls 속성을 설정할 수는 인덱싱된 필드에 Null 항목을 허용 하 고 Null로 항목의 많은 기대 하는 경우 **TRUE** 인덱스가 사용 하는 저장 공간의 양을 줄일 수 있습니다. IgnoreNulls 속성 설정 및 필수 속성 설정 Null 인덱스 값을 가진 레코드를 포함 하는 인덱스 항목을 다음 표에서 같이 있는지 여부를 결정 합니다.  
  
|IgnoreNulls|필수|인덱스 필드에 null|  
|-----------------|--------------|-------------------------|  
|True|False|Null 값을 사용할 수 있습니다. 인덱스 항목이 추가 되었습니다.|  
|False|False|Null 값을 사용할 수 있습니다. 인덱스 항목이 추가 되었습니다.|  
|True 또는 False|True|Null 값 허용 되지 않습니다. 인덱스 항목이 추가 되었습니다.|  
  
 자세한 내용은 DAO 도움말의 "IgnoreNulls 속성" 항목을 참조 하십시오.  
  
 `m_bRequired`  
 DAO index 개체는 Null이 아닌 값을 필요한 지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체는 Null 값을 허용 하지 않습니다. 자세한 내용은 DAO 도움말의 "필수 속성" 항목을 참조 하십시오.  
  
> [!TIP]
>  DAO index 개체 또는 field 개체 (테이블 정의 레코드 집합 또는 쿼리 정의 개체에 의해 포함 됨)에 대해이 속성을 설정 하면 field 개체에 대 한 설정 합니다. Field 개체에 설정 된 속성의 유효성을 검사 하는 index 개체의 하기 검사 됩니다.  
  
 *m_bForeign*  
 Index 개체가 테이블의 외래 키를 나타내는지 여부를 나타냅니다. 이 속성이 **TRUE**, 인덱스는 테이블의 외래 키를 나타냅니다. 외래 키 기본 테이블의 행을 고유 하 게 식별 하는 외래 테이블에 하나 이상의 필드로 구성 됩니다. Microsoft Jet 데이터베이스 엔진 외래 테이블에 대 한 인덱스 개체를 만들고 참조 무결성을 적용 하는 관계를 만들 때 외래 속성을 설정 합니다. 자세한 내용은 DAO 도움말에서 "외래 속성" 항목을 참조 합니다.  
  
 *m_lDistinctCount*  
 연결된 된 테이블에 포함 된 인덱스 개체에 대 한 고유 값의 수를 나타냅니다. 인덱스의 키 또는 고유 값 수를 확인 하려면 DistinctCount 속성을 확인 하십시오. 아무 키나 인덱스에서 중복 값을 허용 하는 경우 해당 값의 여러 번 나타날 경우에 한 번만 계산 됩니다. 이 정보는 인덱스 정보를 평가 하 여 데이터 액세스를 최적화 하려고 시도 하는 응용 프로그램에 유용 합니다. 고유 값의 개수는 index 개체의 카디널리티 라고도 합니다. DistinctCount 속성 반영 되지 않습니다 항상 키의 실제 수는 특정 시간에 있습니다. 예를 들어 트랜잭션 롤백에 의해 발생 한 변경 DistinctCount 속성에 즉시 반영 되지 않습니다. 자세한 내용은 DAO 도움말의 "DistinctCount 속성" 항목을 참조 하십시오.  
  
## <a name="remarks"></a>주의  
 기본, 보조 및 위에서 모두에 대 한 참조에서의 정보를 반환 하는 방법을 나타내는 `GetIndexInfo` 클래스 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.  
  
 Index 개체는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 은 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 이러한 클래스는 개별 항목의 인덱스 정보에 액세스 하는 멤버 함수를 제공 하거나 한 번에 액세스할 수 있습니다는 `CDaoIndexInfo` 를 호출 하 여 개체의 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다.  
  
 `CDaoIndexInfo`생성자 및 소멸자 제대로 할당 하 고 인덱스 필드 정보를 할당 해제 하기 위해 `m_pFieldInfos`합니다.  
  
 검색 한 정보는 `GetIndexInfo` tabledef 개체의 멤버 함수에 저장 되는 `CDaoIndexInfo` 구조입니다. 호출 된 `GetIndexInfo` 인덱스 개체가 저장 인 인덱스 컬렉션에 포함 하는 테이블 정의 개체의 멤버 함수입니다. `CDaoIndexInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoIndexInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)


