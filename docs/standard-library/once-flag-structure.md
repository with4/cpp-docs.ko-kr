---
title: "once_flag 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: a39919d3c1608d53edc6a75ecc3dd2e0ff504b1c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="onceflag-structure"></a>once_flag 구조체
실행 스레드가 여러 개 있는 경우에도 초기화 코드를 한 번만 호출하기 위해 템플릿 함수 [call_once](../standard-library/mutex-functions.md#call_once)와 함께 사용되는 `struct`를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
struct once_flag { constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag& operator=(const once_flag&); };  
  
## <a name="remarks"></a>설명  
 `once_flag``struct`에는 기본 생성자만 포함되어 있습니다.  
  
 `once_flag` 형식의 개체는 만들 수는 있지만 복사할 수는 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<뮤텍스 >  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




