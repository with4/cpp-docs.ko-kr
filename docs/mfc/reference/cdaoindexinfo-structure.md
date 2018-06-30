---
title: CDaoIndexInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d07193e43198797b31519b042b9f813676e08c2
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121459"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 구조체

`CDaoIndexInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 인덱스 개체에 대 한 정보를 포함 합니다.

## <a name="syntax"></a>구문

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>매개 변수

*m_strName*  
Field 개체를 이름을 고유 하 게 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_pFieldInfos*  
배열에 대 한 포인터 [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) tabledef 또는 레코드 집합 필드는 인덱스의 키 필드를 나타내는 개체입니다. 각 개체는 인덱스의 한 필드를 식별합니다. 기본 인덱스 순서는 오름차순입니다. Index 개체 각 레코드에 대 한 인덱스 키를 나타내는 하나 이상의 필드를 가질 수 있습니다. 이러한 내림차순, 필터 또는 조합을 오름차순 될 수 있습니다.

*m_nFields*  
에 저장 된 필드 수가 `m_pFieldInfos`합니다.

*m_bPrimary*  
기본 속성이 **TRUE**, index 개체 기본 인덱스를 나타냅니다. 기본 인덱스는 미리 정의 된 순서로 테이블의 모든 레코드를 고유 하 게 식별 하는 하나 이상의 필드로 구성 됩니다. 인덱스 필드는 고유 해야 하기 때문에 Unique Index 개체의도 속성이 **TRUE** dao에서 합니다. 기본 인덱스 둘 이상의 필드로 구성 된 각 필드에 중복 값이 포함 될 수 있습니다 하지만 인덱싱된 모든 필드에서 값 조합은 각각 고유 해야 합니다. 기본 인덱스를 테이블에 대 한 키 구성 되며 일반적으로 기본 키와 같은 필드를 포함 합니다.

테이블에 대 한 기본 키를 설정 하면 기본 키 테이블에 대 한 기본 인덱스를 자동으로 이루어집니다. 자세한 내용은 "기본" 속성과 DAO 도움말의 "고유 Property" 항목을 참조 합니다.

> [!NOTE]
> 인덱스가 있을 수 있습니다, 최대 하나의 기본 테이블에 합니다.

*m_bUnique*  
Index 개체가 테이블에 대 한 고유 인덱스를 나타내는지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체에 있는 고유 인덱스를 나타냅니다. 고유 인덱스는 고유 하 고 미리 정의 된 순서로 테이블의 모든 레코드를 논리적으로 정렬 하는 하나 이상의 필드로 구성 됩니다. 인덱스 하나 필드로 구성 된 경우 해당 필드의 값이 전체 테이블에 대 한 고유 해야 합니다. 인덱스 둘 이상의 필드로 구성 된 각 필드에 중복 값이 포함 될 수 있습니다 하지만 인덱싱된 모든 필드에서 값 조합은 각각 고유 해야 합니다.

Unique 및 Primary 속성이 모두 index 개체의 하도록 설정 된 경우 **TRUE**, 인덱스가 unique 및 primary: 미리 정의 된 논리적 순서로 테이블의 모든 레코드를 고유 하 게 식별 합니다. 기본 속성이로 설정 된 경우 **FALSE**, 인덱스는 보조 인덱스입니다. 보조 인덱스 (키 및 키가 아닌) 테이블의 레코드에 대 한 식별자 역할을 수행 하지 않고 미리 정의 된 순서로 레코드를 논리적으로 정렬 합니다.

자세한 내용은 "기본" 속성과 DAO 도움말의 "고유 Property" 항목을 참조 합니다.

*m_bClustered*  
인덱스 개체가 테이블에 대 한 클러스터형된 인덱스가 있는지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체 클러스터형된 인덱스를 나타냅니다; 그렇지 않으면 그렇지 않은 경우. 하나로 구성 된 클러스터형된 인덱스 또는 필드는 더 많은 집합적, 전체적으로 볼 때, 미리 정의 된 순서에 따라 테이블의 모든 레코드를 정렬 합니다. 클러스터형된 인덱스가 있는 테이블의 데이터를 문자 그대로 클러스터형된 인덱스에 의해 지정 된 순서로 저장 됩니다. 클러스터형된 인덱스는 테이블의 레코드에 효율적으로 액세스를 제공합니다. 자세한 내용은 DAO 도움말의 "클러스터형 Property" 항목을 참조 하십시오.

> [!NOTE]
> Clustered 속성은 Jet 데이터베이스 엔진에서 클러스터형된 인덱스를 지원 하지 않으므로 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대 한 무시 됩니다.

*m_bIgnoreNulls*  
인덱스 필드에 Null 값이 포함 된 레코드에 대해 인덱스 항목이 있는지 여부를 나타냅니다. 이 속성이 **TRUE**, Null 값을 갖는 필드가 있는 색인 항목 필요가 없습니다. 필드를 더 빠르게 사용 하 여 레코드에 대 한 검색을 하려면 필드에 대 한 인덱스를 정의할 수 있습니다. 인덱싱된 필드에 Null 항목을 허용 하 고 다양 한 항목 Null을 예상 하는 경우에 인덱스 개체에 대 한 IgnoreNulls 속성을 설정할 수 있습니다 **TRUE** 인덱스를 사용 하는 저장소 공간의 양을 줄일 수 있습니다. IgnoreNulls 속성 설정 및 필요한 속성 설정을 함께 Null 인덱스 값을 가진 레코드를 포함 하는 인덱스 항목을 다음 표에서 같이 있는지 여부를 결정 합니다.

|IgnoreNulls|필수|인덱스 필드에 null|
|-----------------|--------------|-------------------------|
|True|False|Null 값 허용 인덱스 항목이 추가 되었습니다.|
|False|False|Null 값 허용 인덱스 항목을 추가 했습니다.|
|True 또는 False|True|Null 값을 사용할 수 없습니다. 인덱스 항목이 추가 되었습니다.|

자세한 내용은 DAO 도움말의 "IgnoreNulls Property" 항목을 참조 하십시오.

*m_bRequired*  
DAO index 개체는 Null이 아닌 값을 필요한 지 여부를 나타냅니다. 이 속성이 **TRUE**, index 개체는 Null 값을 허용 하지 않습니다. 자세한 내용은 DAO 도움말의 "필수 속성" 항목을 참조 하십시오.

> [!TIP]
> Field 개체 (테이블 정의 레코드 집합 또는 querydef 개체에 포함 된) 또는 DAO index 개체에 대 한이 속성을 설정할 수 있는 경우 필드 개체에 대 한 설정 합니다. Field 개체에 대 한 속성 설정의 유효성을 검사 하는 index 개체의 하기 전에 확인 됩니다.

*m_bForeign*  
Index 개체는 테이블의 외래 키를 나타내는지 여부를 나타냅니다. 이 속성이 **TRUE**, 인덱스 테이블의 외래 키를 나타냅니다. 외래 키 기본 테이블의 행을 고유 하 게 식별 하는 외래 테이블의 하나 이상의 필드로 구성 됩니다. Microsoft Jet 데이터베이스 엔진 외래 테이블에 대 한 인덱스 개체를 만들고 참조 무결성을 적용 하는 관계를 만들 때 외래 속성을 설정 합니다. 자세한 내용은 DAO 도움말의 "외래 Property" 항목을 참조 하십시오.

*m_lDistinctCount*  
연결된 된 테이블에 포함 된 인덱스 개체에 대 한 고유 값의 수를 나타냅니다. 인덱스의 키 또는 고유 값의 수를 확인 하려면 DistinctCount 속성을 확인 하십시오. 아무 키나 인덱스 중복 값을 허용 하는 경우 해당 값의 여러 번 나타날 경우에 한 번만 계산 됩니다. 이 정보는 인덱스 정보를 평가 하 여 데이터 액세스를 최적화 하려고 하는 응용 프로그램에 유용 합니다. 고유 값의 개수는 index 개체의 카디널리티 라고도 합니다. DistinctCount 속성은 특정 시간에 키의 실제 수 그대로 반영 하지 합니다. 예를 들어 트랜잭션 롤백에 의해 발생 한 변경 DistinctCount 속성에 즉시 반영 되지 않습니다. 자세한 내용은 DAO 도움말의 "DistinctCount Property" 항목을 참조 하십시오.

## <a name="remarks"></a>설명

주, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 `GetIndexInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.

Index 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, DAO 개체 클래스의 기본 MFC 개체 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 이러한 클래스는 개별 항목의 인덱스 정보에 액세스 하는 멤버 함수를 제공 하거나 인수를 한 번에 모두를 사용 하 여 액세스할 수 있습니다는 `CDaoIndexInfo` 호출 하 여 개체는 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다.

`CDaoIndexInfo` 에 생성자와 소멸자 제대로 할당 하 고 인덱스 필드 정보에 할당을 취소 하기 위해 `m_pFieldInfos`합니다.

검색 한 정보는 `GetIndexInfo` tabledef 개체의 멤버 함수에 저장 되는 `CDaoIndexInfo` 구조입니다. 호출 된 `GetIndexInfo` 인덱스 개체가 보관 되어 있는 인덱스 컬렉션에 포함 하는 테이블 정의 개체의 멤버 함수입니다. `CDaoIndexInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoIndexInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)  
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)  
