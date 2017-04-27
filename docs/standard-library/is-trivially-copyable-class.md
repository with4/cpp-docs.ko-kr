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
- is_trivially_copyable
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3e154db9981558eeef6c802a0e9538bdb04a8f9c
ms.lasthandoff: 02/24/2017

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




