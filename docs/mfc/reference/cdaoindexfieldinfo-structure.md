---
title: CDaoIndexFieldInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7be9a6a9db842f1e80be62f48a9990cff36168e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 구조체
`CDaoIndexFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 인덱스 필드 개체에 대 한 정보를 포함 합니다.  
  
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
 고유 하 게 인덱스 필드 개체의 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 *m_bDescending*  
 Index 개체에 정의 된 인덱스 순서를 나타냅니다. **True 이면** 내림차순의 경우.  
  
## <a name="remarks"></a>설명  
 Index 개체는 여러 테이블 정의 (또는 테이블을 기반으로 레코드 집합)에 인덱싱된 필드를 나타내는 필드가 있을 수 있습니다. 위의 주에 대 한 참조 정보가 반환 되는 방법을 나타내는 `m_pFieldInfos` 의 멤버는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 호출 하 여 가져온 개체는 `GetIndexInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.  
  
 Index 개체 및 인덱스 필드 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, DAO 개체 클래스의 기본 MFC 개체 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 또는 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 각 index 개체 필드 개체의 컬렉션을 포함합니다. 이러한 클래스는 개별 항목의 인덱스 정보에 액세스 하는 멤버 함수를 제공 하거나 인수를 한 번에 모두를 사용 하 여 액세스할 수 있습니다는 `CDaoIndexInfo` 호출 하 여 개체는 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다. `CDaoIndexInfo` 개체, 데이터 멤버를 다음에 `m_pFieldInfos`, 배열을 가리키는 `CDaoIndexFieldInfo` 개체입니다.  
  
 호출 된 `GetIndexInfo` 인덱스가 있는 컬렉션은 포함 tabledef 또는 레코드 집합 개체의 멤버 함수에 관심이 있는 index 개체를 저장 합니다. 다음 액세스는 `m_pFieldInfos` 의 멤버는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 개체입니다. 길이 `m_pFieldInfos` 배열에 저장 된 `m_nFields`합니다. `CDaoIndexFieldInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoIndexFieldInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

