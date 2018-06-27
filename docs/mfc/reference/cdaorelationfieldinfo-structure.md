---
title: CDaoRelationFieldInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d86faf89aea0f991a9fdd27bec6bb7969404986
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956913"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 구조체
`CDaoRelationFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 관계에 있는 필드에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *m_strName*  
 관계의 기본 테이블에 있는 필드의 이름입니다.  
  
 *m_strForeignName*  
 관계의 외래 테이블에 있는 필드의 이름입니다.  
  
## <a name="remarks"></a>설명  
 DAO relation 개체는 기본 테이블 및 관계를 정의 하는 외래 테이블의 필드에 필드를 지정 합니다. 위의 구조 정의에 기본에 대 한 참조 정보가 반환 되는 방법을 나타내는 `m_pFieldInfos` 의 멤버는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 호출 하 여 가져온 개체는 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)클래스의 멤버 함수 `CDaoDatabase`합니다.  
  
 관계 개체 및 관계 필드 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, DAO 개체 클래스의 기본 MFC 개체 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Relations 컬렉션 이라고 하는 관계 개체의 컬렉션을 포함 합니다. 각 relation 개체 관계 필드 개체의 컬렉션을 포함합니다. 각 관계 field 개체 외래 테이블의 필드와 기본 테이블의 필드에에서 연관 시킵니다. 전체적으로 볼 때, 관계 필드 개체 정의 필드 그룹을 각 테이블의 관계 정의 합니다. `CDaoDatabase` 사용 하 여 관계 개체에 액세스할 수 있습니다는 `CDaoRelationInfo` 호출 하 여 개체는 `GetRelationInfo` 멤버 함수입니다. `CDaoRelationInfo` 개체, 데이터 멤버를 다음에 `m_pFieldInfos`, 배열을 가리키는 `CDaoRelationFieldInfo` 개체입니다.  
  
 호출 된 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 포함 하는 멤버 함수 `CDaoDatabase` 개체의 관계 컬렉션이 갖는에 관심이 있는 relation 개체 저장 합니다. 다음 액세스는 `m_pFieldInfos` 의 멤버는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 개체입니다. `CDaoRelationFieldInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoRelationFieldInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 구조체](../../mfc/reference/cdaorelationinfo-structure.md)
