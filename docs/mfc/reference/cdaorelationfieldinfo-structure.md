---
title: "CDaoRelationFieldInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
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
ms.openlocfilehash: 23d7497502f611cf2311e574556186dc5f7c7d3d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 구조체
`CDaoRelationFieldInfo` 구조에 데이터 액세스 개체 (DAO)에 대해 정의 된 관계에 있는 필드에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 관계의 기본 테이블에 있는 필드의 이름입니다.  
  
 `m_strForeignName`  
 관계의 외래 테이블의 필드의 이름입니다.  
  
## <a name="remarks"></a>주의  
 DAO relation 개체는 기본 테이블 및 관계를 정의 하는 외래 테이블의 필드에 필드를 지정 합니다. 위의 구조 정의에서 기본에 대 한 참조 정보에 반환 되는 방법을 나타내는 `m_pFieldInfos` 의 멤버는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 를 호출 하 여 가져온 개체는 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 클래스의 멤버 함수 `CDaoDatabase`합니다.  
  
 관계 개체 및 관계 field 개체는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 관계 컬렉션 이라고 하는 관계 개체의 컬렉션을 포함 합니다. 각 관계 개체 관계 field 개체의 컬렉션을 포함합니다. 각 관계 field 개체 상호 외래 테이블의 필드와 기본 테이블의 필드를 연결합니다. 전체적으로 볼 때, 관계 field 개체 필드 그룹 각 테이블에 있는 정의 함께 관계를 정의 합니다. `CDaoDatabase`사용 하 여 관계 개체에 액세스할 수 있습니다는 `CDaoRelationInfo` 를 호출 하 여 개체의 `GetRelationInfo` 멤버 함수입니다. `CDaoRelationInfo` 개체, 그런 다음에 데이터 멤버가, `m_pFieldInfos`, 배열을 가리키는 `CDaoRelationFieldInfo` 개체입니다.  
  
 호출의 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 포함 하는 멤버 함수 `CDaoDatabase` 개체 관계 컬렉션은 해당 관심이 있는 relation 개체 저장 합니다. 다음 액세스는 `m_pFieldInfos` 의 멤버는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 개체입니다. `CDaoRelationFieldInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoRelationFieldInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 구조체](../../mfc/reference/cdaorelationinfo-structure.md)

