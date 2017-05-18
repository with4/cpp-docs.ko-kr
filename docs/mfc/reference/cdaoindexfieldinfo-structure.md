---
title: "CDaoIndexFieldInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
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
ms.openlocfilehash: 975b3a704936adc9d4205938bb2c757ab650f0d9
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 구조체
`CDaoIndexFieldInfo` 구조에 데이터 액세스 개체 (DAO)에 대해 정의 되는 인덱스 필드 개체에 대 한 정보가 들어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 인덱스 필드 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 *m_bDescending*  
 Index 개체에 정의 된 인덱스 순서를 나타냅니다. **True 이면** 내림차순의 경우.  
  
## <a name="remarks"></a>주의  
 Index 개체에서 테이블 정의 (또는 테이블을 기반으로 레코드 집합)는 인덱싱된 필드를 나타내는 필드의 있을 수 있습니다. 위의 기본에 대 한 참조 정보에 반환 되는 방법을 나타내는 `m_pFieldInfos` 의 멤버는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 를 호출 하 여 가져온 개체는 `GetIndexInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.  
  
 Index 개체 및 인덱스 필드 개체는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 은 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 각 인덱스 개체 field 개체의 컬렉션을 포함합니다. 이러한 클래스는 개별 항목의 인덱스 정보에 액세스 하는 멤버 함수를 제공 하거나 한 번에 액세스할 수 있습니다는 `CDaoIndexInfo` 를 호출 하 여 개체의 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다. `CDaoIndexInfo` 개체, 그런 다음에 데이터 멤버가, `m_pFieldInfos`, 배열을 가리키는 `CDaoIndexFieldInfo` 개체입니다.  
  
 호출 된 `GetIndexInfo` 인덱스가 있는 컬렉션은 포함 된 테이블 정의 또는 레코드 집합 개체의 멤버 함수에 관심이 index 개체를 저장 합니다. 다음 액세스는 `m_pFieldInfos` 의 멤버는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 개체입니다. 길이 `m_pFieldInfos` 배열에 저장 된 `m_nFields`합니다. `CDaoIndexFieldInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoIndexFieldInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)


