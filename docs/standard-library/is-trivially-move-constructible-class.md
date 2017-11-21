---
title: "is_trivially_move_constructible 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_move_constructible
dev_langs: C++
helpviewer_keywords: is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba32f03d08032bc47373d2389831e52913298d49
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallymoveconstructible-class"></a>is_trivially_move_constructible 클래스
형식에 Trivial 이동 생성자가 있는지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct is_trivially_move_constructible;
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 형식 `Ty`가 Trivial 이동 생성자를 가진 클래스인 경우 true이고 그렇지 않은 경우 false입니다.  
  
 클래스 `Ty`에 대한 이동 생성자는 다음과 같은 경우 Trivial입니다.  
  
 암시적으로 선언된 경우  
  
 매개 변수 형식이 암시적 선언의 형식과 동일한 경우  
  
 클래스 `Ty`에 가상 함수가 없는 경우  
  
 클래스 `Ty`에 가상 기본이 없는 경우  
  
 클래스에 휘발성 비정적 데이터 멤버가 없는 경우  
  
 클래스 `Ty`의 모든 직접 기본에 Trivial 이동 생성자가 있는 경우  
  
 클래스 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 이동 생성자가 있는 경우  
  
 클래스 배열 형식의 모든 비정적 데이터 멤버의 클래스에 Trivial 이동 생성자가 있는 경우  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



