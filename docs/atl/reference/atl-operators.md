---
title: ATL 연산자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ffb1c782e4b527b5e8a930a07d74859f7d8824c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880205"
---
# <a name="atl-operators"></a>ATL 연산자
이 섹션에서는 ATL 전역 연산자에 대 한 참조 항목을 포함합니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|[operator ==](#operator_eq_eq)|두 `CSid` 개체 또는 `SID` 구조체가 같은지 여부.|  
|[연산자! =](#operator_neq)|두 `CSid` 개체 또는 `SID` 구조체가 다른 지 합니다.|  
|[연산자 <](#operator_lt)|테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조체가 보다 작은 `CSid` 개체 또는 `SID` (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있는 구조체입니다.|  
|[연산자 >](#operator_gt)|테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조 보다 큽니다.는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.|  
|[연산자 < =](#operator_lt__eq)|테스트를 `CSid` 개체 또는 `SID` 보다 작거나 같음 연산자의 좌 변에 있는 구조는는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.|  
|[연산자 > =](#operator_gt__eq)|테스트를 `CSid` 개체 또는 `SID` 보다 크거나 같음 연산자의 좌 변에 있는 구조는는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 합니다.  
  
##  <a name="operator_eq_eq"></a>  operator ==  
 비교 `CSid` 개체 또는 `SID` 같은지 (보안 식별자) 구조입니다.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 같은지 여부를 FALSE 동일 하지 않은 경우 TRUE를 반환 합니다.  
  
##  <a name="operator_neq"></a>  연산자! =  
 비교 `CSid` 개체 또는 `SID` 구조체가 다른 지 (보안 식별자)입니다.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 *rhs*  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 없는 경우 같음, 같지 않으면 FALSE입니다. TRUE를 반환 합니다.  
  
##  <a name="operator_lt"></a>  operator <  
 테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조체가 보다 작은 `CSid` 개체 또는 `SID` (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있는 구조체입니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 *rhs*  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 합니다.의 주소를 *lhs* 개체의 주소 보다 작습니다 합니다 *rhs* 개체 FALSE이 고, 그렇지 합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스를 사용 하 여 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="operator_gt"></a>  operator >  
 테스트를 `CSid` 개체 또는 `SID` 연산자의 좌 변에 있는 구조 보다 큽니다.는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 *rhs*  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 합니다.의 주소를 *lhs* 주소 보다 큰를 *rhs*이 고, FALSE이 고, 그렇지 합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스를 사용 하 여 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="operator_lt__eq"></a>  operator <=  
 테스트를 `CSid` 개체 또는 `SID` 보다 작거나 같음 연산자의 좌 변에 있는 구조는는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 *rhs*  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환의 주소를 *lhs* 주소 보다 작거나 같으면 합니다 *rhs*이 고, FALSE이 고, 그렇지 합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스를 사용 하 여 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="operator_gt__eq"></a>  operator >=  
 테스트를 `CSid` 개체 또는 `SID` 보다 크거나 같음 연산자의 좌 변에 있는 구조는는 `CSid` 개체 또는 `SID` 구조체 (c + + 표준 라이브러리 호환성)에 대 한 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 *rhs*  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우 TRUE를 반환 합니다.의 주소를 *lhs* 주소의 이상이 되는 *rhs*이 고, FALSE이 고, 그렇지.  
  
### <a name="remarks"></a>설명  
 이 연산자의 주소에서 작동 합니다 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스를 사용 하 여 호환성을 제공 하기 위해 구현 됩니다.



