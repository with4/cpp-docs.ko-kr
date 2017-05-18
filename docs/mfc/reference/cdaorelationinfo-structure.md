---
title: "CDaoRelationInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7c3a8195aed2c3b3fe5c78c98afcc6e72a83cc21
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
 `m_strName`  
 Relation 개체를 이름을 고유 하 게 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 하십시오.  
  
 *m_strTable*  
 관계에서 기본 테이블을 이름을 지정 합니다.  
  
 *m_strForeignTable*  
 관계에서 외래 테이블을 이름을 지정 합니다. 외래 테이블은 외래 키를 포함 하는 데 사용 되는 테이블입니다. 일반적으로 사용 하 여 외래 테이블 설정 하거나 참조 무결성을 적용 합니다. 외래 테이블은 대개 일 대 다 관계의 다 쪽에 있습니다. 외래 테이블의 예로 미국 또는 캐나다의 주 고객 주문에 대 한 코드를 포함 하는 테이블입니다.  
  
 `m_lAttributes`  
 관계 형식에 대 한 정보를 포함합니다. 이 멤버의 값은 다음 중 하나일 수 있습니다.  
  
- **dbRelationUnique** 한 일 관계입니다.  
  
- **dbRelationDontEnforce** 관계가 않습니다 (참조 무결성)를 적용 합니다.  
  
- **dbRelationInherited** 관계는 두 개의 연결 된 테이블을 포함 하는 현재 데이터베이스에 존재 합니다.  
  
- **dbRelationLeft** 관계는 왼쪽된 조인 합니다. 첫 번째에서 레코드의 모든을 포함 하는 왼쪽된 우선 외부 조인 (왼쪽) 두 테이블의 두 번째 (오른쪽) 테이블의 레코드에 일치 하는 값이 없는 경우에 합니다.  
  
- **dbRelationRight** 관계는 오른쪽 조인입니다. 오른쪽 우선 외부 조인에서 두 번째 레코드를 모두 포함 (오른쪽) 두 테이블의 첫 번째 (왼쪽) 테이블의 레코드에 일치 하는 값이 없는 경우에 합니다.  
  
- **중** 계단식 업데이트를 수행 합니다.  
  
- **dbRelationDeleteCascade** 삭제에 연계 됩니다.  
  
 `m_pFieldInfos`  
 배열에 대 한 포인터 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 구조입니다. 배열 관계의 각 필드에 대 한 개체를 포함합니다. `m_nFields` 데이터 멤버는 배열 요소의 수를 제공 합니다.  
  
 `m_nFields`  
 수가 `CDaoRelationFieldInfo` 개체에 `m_pFieldInfos` 데이터 멤버입니다.  
  
## <a name="remarks"></a>주의  
 기본 및 보조 위의에 대 한 참조에서의 정보를 반환 하는 방법을 나타내는 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 클래스에서 멤버 함수 `CDaoDatabase`합니다.  
  
 관계 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, MFC 개체를 내부 DAO 개체는 `CDaoDatabase` 관계 개체의 컬렉션을 유지 하는 클래스: `CDaoDatabase` 관계 정보나 사용자의 일부 개별 항목에 액세스 하는 공급 멤버 함수를 한 번에 액세스할 수는 `CDaoRelationInfo` 를 호출 하 여 개체는 `GetRelationInfo` 포함 하는 데이터베이스 개체의 멤버 함수입니다.  
  
 검색 한 정보는 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 멤버 함수에 저장 되는 `CDaoRelationInfo` 구조입니다. `CDaoRelationInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoRelationInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [CDaoRelationFieldInfo 구조체](../../mfc/reference/cdaorelationfieldinfo-structure.md)

