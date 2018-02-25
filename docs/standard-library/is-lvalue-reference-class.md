---
title: "is_lvalue_reference 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26cbc7dc51fe6db51f47a8b60c6b209dfbc9a337
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="islvaluereference-class"></a>is_lvalue_reference 클래스
형식이 lvalue 참조인지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct is_lvalue_reference;
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 이 형식 조건자의 인스턴스는 형식 `Ty`가 개체나 함수에 대한 참조인 경우 true이고 그렇지 않은 경우 false입니다. `Ty`가 rvalue 참조가 아닐 수 있습니다. rvalue에 대한 자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)



