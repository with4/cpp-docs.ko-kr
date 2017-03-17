---
title: "CDefaultCharTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 12991cfcf1ac96808a0315899d01ce3012324dc6
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits 클래스
이 클래스는 대 문자와 소문자 사이 문자를 변환 하기 위한 두 개의 정적 함수를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(정적) 문자를 대문자로 변환 하려면이 함수를 호출 합니다.|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(정적) 문자를 소문자로 변환 하려면이 함수를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 클래스에서 사용 되는 함수를 제공 합니다. [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 문자를 소문자로 변환 하려면이 함수를 호출 합니다.  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 소문자로 변환할 문자입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Utilities #&132;](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 문자를 대문자로 변환 하려면이 함수를 호출 합니다.  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 대문자로 변환할 문자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

