---
title: CDaoParameterInfo 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e743e7456c185acd100c898cfb946182d63ce63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 구조체
`CDaoParameterInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 매개 변수 개체에 대 한 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `m_strName`  
 고유 하 게 매개 변수 개체의 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.  
  
 `m_nType`  
 매개 변수 개체의 데이터 형식을 나타내는 값입니다. 목록이 가능한 값에 대 한 참조는 `m_nType` 의 멤버는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 자세한 내용은 DAO 도움말의 "Type 속성" 항목을 참조 합니다.  
  
 *m_varValue*  
 에 저장 된 매개 변수의 값을 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.  
  
## <a name="remarks"></a>설명  
 기본 및 보조 위의에 대 한 참조 정보에서 반환 되는 방법을 나타내는 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 클래스에서 멤버 함수 `CDaoQueryDef`합니다.  
  
 MFC는 클래스에서 DAO 매개 변수 개체를 캡슐화 하지 않습니다. 개체를 기본 MFC DAO querydef `CDaoQueryDef` 개체의 매개 변수 컬렉션에서 매개 변수를 저장 합니다. 매개 변수 개체에 액세스 한 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체, 쿼리 정의 개체의 `GetParameterInfo` 특정 매개 변수 이름이 나 매개 변수 컬렉션에 대 한 인덱스에 대 한 멤버 함수입니다. 사용할 수 있습니다는 [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 함께에서 멤버 함수 `GetParameterInfo` 매개 변수 컬렉션을 반복 합니다.  
  
 검색 한 정보는 [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에 저장 되는 `CDaoParameterInfo` 구조입니다. 호출 `GetParameterInfo` 인 매개 변수 컬렉션 매개 변수 개체가 저장 된 쿼리 정의 개체에 대 한 합니다.  
  
> [!NOTE]
>  Get 또는 매개 변수 값 설정, 사용 하려는 경우는 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 및 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 클래스의 멤버 함수 `CDaoRecordset`합니다.  
  
 `CDaoParameterInfo` 또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoParameterInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)
