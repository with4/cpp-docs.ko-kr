---
title: "shuffle_order_engine 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- shuffle_order_engine
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- shuffle_order_engine class
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 93c5721a4b651315bc4d67cc9d5a0cb7d2f852a3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine 클래스
기본 엔진에서 반환된 값을 다시 정렬하여 임의의 시퀀스를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Engine, size_t K>  
class shuffle_order_engine;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Engine`  
 기본 엔진 유형입니다.  
  
 `K`  
 **테이블 크기**. 버퍼(테이블)에 있는 요소의 수입니다. **사전 조건**: `0 < K`  
  
## <a name="members"></a>멤버  
  
||||  
|-|-|-|  
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|  
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|  
  
 엔진 구성원에 대한 자세한 내용은 [\<random>](../standard-library/random.md)을 참조하세요.  
  
## <a name="remarks"></a>설명  
 이 템플릿 클래스는 기본 엔진에서 반환하는 값을 다시 정렬하여 값을 생성하는 *엔진 어댑터*에 대해 설명합니다. 각 생성자는 기본 엔진에서 반환한 `K` 값으로 내부 테이블을 채우고 값이 요청되면 이 테이블에서 임의 요소가 선택됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<random>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\<random>](../standard-library/random.md)


