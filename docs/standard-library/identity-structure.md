---
title: "identity 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::identity
- utility/std::identity
- identity
- std.identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a7404d2c1a785fd66489421fd7b9689260e0986d
ms.lasthandoff: 02/24/2017

---
# <a name="identity-structure"></a>identity 구조체
형식 정의를 템플릿 매개 변수로 제공하는 구조체입니다.  
  
## <a name="syntax"></a>구문  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`left`|식별할 값입니다.|  
  
## <a name="remarks"></a>설명  
 클래스에는 템플릿 매개 변수 Type과 동일한 public 형식 정의 `type`이 포함되어 있습니다. 템플릿 함수 [forward](../standard-library/utility-functions.md#forward)와 함께 사용되어 함수 매개 변수가 원하는 형식을 갖도록 합니다.  
  
 이전 코드와의 호환성을 위해 클래스는 해당 인수 `left`를 반환하는 ID 함수 `operator()`도 정의합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<utility>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\<utility>](../standard-library/utility.md)




