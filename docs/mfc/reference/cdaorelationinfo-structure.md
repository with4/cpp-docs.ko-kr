---
title: CDaoRelationInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a49bdfb00c3f2ceba424af7bfdfa652cacec929e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951294"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 구조체
`CDaoRelationInfo` 구조에서 두 테이블의 필드 간에 정의 된 관계에 대 한 정보를 포함 한 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *m_strName*  
 Relation 개체를 이름을 고유 하 게 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 *m_strTable*  
 관계에서 기본 테이블을 이름을 지정 합니다.  
  
 *m_strForeignTable*  
 관계에서 외래 테이블을 이름을 지정 합니다. 에 있는 외래 테이블은 외래 키를 포함 하는 데 사용 되는 테이블입니다. 일반적으로 설정 하거나 참조 무결성을 유지 하에 있는 외래 테이블을 사용 합니다. 외래 테이블은 일반적으로 일 대 다 관계의 다 쪽에 있습니다. 외래 테이블의 예로 미국 또는 캐나다의 주 또는 고객 주문에 대 한 코드를 포함 하는 테이블입니다.  
  
 *m_lAttributes*  
 관계 형식에 대 한 정보를 포함합니다. 이 멤버의 값은 다음 중 하나일 수 있습니다.  
  
- **dbRelationUnique** 한 일 관계입니다.  
  
- **dbRelationDontEnforce** 관계가 않습니다 (참조 무결성)를 적용 합니다.  
  
- **dbRelationInherited** 관계는 두 개의 연결 된 테이블을 포함 하는 고정 데이터베이스에 존재 합니다.  
  
- **dbRelationLeft** 관계는 왼쪽된 조인 합니다. 왼쪽된 우선 외부 조인을 첫 번째에서 레코드를 모두 포함 (왼쪽) 두 테이블의 두 번째 (오른쪽) 테이블의 레코드에 대 한 일치 하는 값이 없는 경우에 합니다.  
  
- **dbRelationRight** 관계는 오른쪽 조인 합니다. 오른쪽 우선 외부 조인에서 두 번째 레코드를 모두 포함 (오른쪽) 두 테이블의 첫 번째 (왼쪽) 테이블의 레코드에 대 한 일치 하는 값이 없는 경우에 합니다.  
  
- **중** 계단식 업데이트를 수행 합니다.  
  
- **dbRelationDeleteCascade** 삭제 연계 됩니다.  
  
 *m_pFieldInfos*  
 배열에 대 한 포인터 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 구조입니다. 배열에는 관계의 각 필드에 대 한 개체가 포함 됩니다. *m_nFields* 데이터 멤버는 배열 요소의 수를 제공 합니다.  
  
 *m_nFields*  
 수가 `CDaoRelationFieldInfo` 개체에 *m_pFieldInfos* 데이터 멤버입니다.  
  
## <a name="remarks"></a>설명  
 기본 및 보조 위의에 대 한 참조 정보에서 반환 되는 방법을 나타내는 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 클래스에서 멤버 함수 `CDaoDatabase`합니다.  
  
 관계 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, MFC 개체를 원본 DAO 개체는 `CDaoDatabase` 관계 개체의 컬렉션을 유지 하는 클래스: `CDaoDatabase` 관계 정보 또는 있습니다 일부 개별 항목에 액세스 하는 공급 멤버 함수는 를사용하여한번에모두액세스할수있습니다`CDaoRelationInfo` 호출 하 여 개체는 `GetRelationInfo` 포함 하는 데이터베이스 개체의 멤버 함수입니다.  
  
 검색 한 정보는 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 멤버 함수에 저장 되는 `CDaoRelationInfo` 구조입니다. `CDaoRelationInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoRelationInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [CDaoRelationFieldInfo 구조체](../../mfc/reference/cdaorelationfieldinfo-structure.md)
