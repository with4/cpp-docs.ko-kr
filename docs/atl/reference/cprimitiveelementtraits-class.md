---
title: CPrimitiveElementTraits 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2219be699e879afb6ec19ad84acc50f18d93a9a9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885811"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits 클래스
이 클래스는 기본 메서드를 제공 하 고 함수 컬렉션 클래스에 대 한 기본 데이터 유형으로 구성 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 컬렉션 클래스 개체에 저장할 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.|  
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 기본 정적 함수 및 이동, 복사, 비교 및 컬렉션 클래스 개체에 저장 하는 기본 데이터 형식 요소를 해시에 대 한 메서드를 제공 합니다.  
  
 자세한 내용은 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CPrimitiveElementTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE  
 컬렉션 클래스 개체에 요소를 추가 하는 데 데이터 형식입니다.  
  
```
typedef T INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE  
 컬렉션 클래스 개체의 요소를 검색에 사용할 데이터 형식입니다.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>참고 항목  
 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
