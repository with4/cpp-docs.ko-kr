---
title: "is_rvalue_reference 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 950f36fc4240e76d464bfcd1eaff4bb46783311c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference 클래스
형식이 rvalue 참조인지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Ty>
struct is_rvalue_reference;
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 이 형식 조건자의 인스턴스는 `Ty` 형식이 [rvalue 참조](../cpp/rvalue-reference-declarator-amp-amp.md)인 경우 true입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md)



