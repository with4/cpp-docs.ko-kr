---
title: "CDaoParameterInfo 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
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
ms.openlocfilehash: b41d26b736ea9f84c53f71dbd71949f74fb8ae52
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 구조체
`CDaoParameterInfo` 구조에 데이터 액세스 개체 (DAO)에 대해 정의 된 매개 변수 개체에 대 한 정보가 들어 있습니다.  
  
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
 고유 하 게 매개 변수 개체의 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 하십시오.  
  
 `m_nType`  
 매개 변수 개체의 데이터 형식을 나타내는 값입니다. 가능한 값의 목록에 대 한 참조는 `m_nType` 의 멤버는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 자세한 내용은 DAO 도움말의 "Type 속성" 항목을 참조 하십시오.  
  
 *m_varValue*  
 에 저장 된 매개 변수의 값을 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.  
  
## <a name="remarks"></a>주의  
 기본 및 보조 위의에 대 한 참조에서의 정보를 반환 하는 방법을 나타내는 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 클래스에서 멤버 함수 `CDaoQueryDef`합니다.  
  
 MFC는 클래스에서 DAO 매개 변수 개체를 캡슐화 되지 않습니다. DAO 쿼리 정의는 MFC 기본 개체 `CDaoQueryDef` 개체 매개 변수를 해당 매개 변수 컬렉션에 저장 합니다. 매개 변수 개체에 액세스 하는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체, 쿼리 정의 개체의 호출 `GetParameterInfo` 특정 매개 변수 이름 또는 매개 변수 컬렉션에 대 한 인덱스에 대 한 멤버 함수입니다. 사용할 수는 [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 멤버 함수를 함께 `GetParameterInfo` Parameters 컬렉션을 반복 하 합니다.  
  
 검색 한 정보는 [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에 저장 되는 `CDaoParameterInfo` 구조입니다. 호출 `GetParameterInfo` 쿼리 정의 개체 매개 변수 개체가 해당 매개 변수 컬렉션에 저장 됩니다.  
  
> [!NOTE]
>  가져오기 또는 매개 변수 값을 설정, 사용 하려는 경우는 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 및 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 클래스의 멤버 함수 `CDaoRecordset`합니다.  
  
 `CDaoParameterInfo`또한 정의 `Dump` 디버그에서 멤버 함수를 작성 합니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 `CDaoParameterInfo` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdao.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)

