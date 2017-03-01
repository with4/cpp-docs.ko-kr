---
title: "ATL 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: 16
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 87aadf7aacc31ded165a8e1380823cb20e614fb1
ms.lasthandoff: 02/24/2017

---
# <a name="atl-operators"></a>ATL 연산자
이 섹션에서는 ATL 전역 연산자에 대 한 참조 항목을 포함합니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|[연산자 = =](#operator_eq_eq)|두 `CSid` 개체 또는 `SID` 구조체가 같은지 여부입니다.|  
|[연산자! =](#operator_neq)|두 `CSid` 개체 또는 `SID` 구조체가 다른 지 합니다.|  
|[연산자](#operator_lt)|테스트는 `CSid` 개체 또는 `SID` 연산자의 왼쪽에는 구조는 보다 작은 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.|  
|[연산자 >](#operator_gt)|테스트는 `CSid` 개체 또는 `SID` 연산자의 좌 변에 구조 보다 크면는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.|  
|[연산자<>](#operator_lt__eq)|테스트는 `CSid` 개체 또는 `SID` 값 보다 작거나 같음 연산자의 왼쪽에는 구조는는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.|  
|[연산자 > =](#operator_gt__eq)|테스트는 `CSid` 개체 또는 `SID` 보다 크거나 같음 연산자의 왼쪽에는 구조는는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.|  
  
 이러한 연산자는 모든 파일 atlsecurity.h에 정의 됩니다.  
  
##  <a name="a-nameoperatoreqeqa--operator-"></a><a name="operator_eq_eq"></a>연산자 = =  
 비교 `CSid` 개체 또는 `SID` 구조체가 같은지 (보안 식별자)입니다.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 개체가 동일 하면 **false** 같지 않은 경우.  
  
##  <a name="a-nameoperatorneqa--operator-"></a><a name="operator_neq"></a>연산자! =  
 비교 `CSid` 개체 또는 `SID` 구조체가 다른 지 (보안 식별자)입니다.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 개체가 같지 않으면 **false** 같으면 합니다.  
  
##  <a name="a-nameoperatorlta--operator-"></a><a name="operator_lt"></a>연산자  
 테스트는 `CSid` 개체 또는 `SID` 연산자의 왼쪽에는 구조는 보다 작은 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우의 주소는 `lhs` 개체의 주소 보다 작으면는 `rhs` 개체 **false** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 연산자의 주소에 대 한 조치는 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스와의 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="a-nameoperatorgta--operator-"></a><a name="operator_gt"></a>연산자 >  
 테스트는 `CSid` 개체 또는 `SID` 연산자의 좌 변에 구조 보다 크면는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우의 주소는 `lhs` 의 주소 보다 크면는 `rhs`, **false** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 연산자의 주소에 대 한 조치는 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스와의 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="a-nameoperatorlteqa--operator-"></a><a name="operator_lt__eq"></a>연산자<=></=>  
 테스트는 `CSid` 개체 또는 `SID` 값 보다 작거나 같음 연산자의 왼쪽에는 구조는는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우의 주소는 `lhs` 보다 작거나 같으면의 주소에는 `rhs`, **false** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 연산자의 주소에 대 한 조치는 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스와의 호환성을 제공 하기 위해 구현 됩니다.  
  
##  <a name="a-nameoperatorgteqa--operator-"></a><a name="operator_gt__eq"></a>연산자 > =  
 테스트는 `CSid` 개체 또는 `SID` 보다 크거나 같음 연산자의 왼쪽에는 구조는는 `CSid` 개체 또는 `SID` 구조 (c + + 표준 라이브러리 호환용) 오른쪽에 있습니다.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `lhs`  
 첫 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
 `rhs`  
 두 번째 `CSid` 개체 또는 `SID` 비교할 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우의 주소는 `lhs` 보다 크거나 같으면의 주소에는 `rhs`, **false** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 이 연산자의 주소에 대 한 조치는 `CSid` 개체 또는 `SID` 구조체와 c + + 표준 라이브러리 컬렉션 클래스와의 호환성을 제공 하기 위해 구현 됩니다.




