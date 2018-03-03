---
title: "is_trivially_copyable 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6f3cf5f6ca0fc6168c061df2ec276f058abea51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable 클래스
형식이 일반적으로 복사 가능한 형식인지를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>
struct is_trivially_copyable;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `T` 형식이 일반적으로 복사 가능한 형식인 경우 true이고, 그렇지 않으면 false입니다. 일반적으로 복사 가능한 형식에는 특수한 복사 작업, 이동 작업 또는 소멸자가 없습니다. 일반적으로 복사 작업은 비트 복사로 구현할 수 있는 경우 trivial로 간주됩니다. 기본 제공 형식과 일반적으로 복사 가능한 형식의 배열은 모두 일반적으로 복사 가능합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



