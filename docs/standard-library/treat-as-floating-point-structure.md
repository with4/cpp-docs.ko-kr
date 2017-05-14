---
title: "treat_as_floating_point 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9d9e6b0b281fb97475b0c23acb4bf7d0fc391a52
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point 구조체
`Rep`가 부동 소수점 형식으로 처리될 수 있는지를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## <a name="remarks"></a>설명  
 특수화 `treat_as_floating_point<Rep>`가 [true_type](../standard-library/type-traits-typedefs.md#true_type)에서 파생되는 경우에만 `Rep`를 부동 소수점 형식으로 처리할 수 있습니다. 사용자 형식 정의에 대해 템플릿 클래스를 특수화할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<c h >  
  
 **네임스페이스:** std::chrono  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


