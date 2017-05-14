---
title: "&lt;iomanip&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::<iomanip>
- std::<iomanip>
- <iomanip>
- std.<iomanip>
dev_langs:
- C++
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 753e2a5bab18a3643456504bda2ab84df530754e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/29/2017

---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;
`iostreams` 표준 헤더 `<iomanip>`를 포함하여 각각 단일 인수를 사용하는 여러 조작자를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <iomanip>  
  
```  
  
## <a name="remarks"></a>설명  
 이러한 각 조작자는 **T1**부터 **T10**까지라는 지정되지 않은 형식을 반환하며, 이 형식은 `basic_istream`\<**Elem**, **Tr**>`::`[operator>>](../standard-library/istream-operators.md#op_gt_gt) 및 `basic_ostream`\<**Elem**, **Tr**>`::`[operator<<](../standard-library/ostream-operators.md#op_lt_lt)를 모두 오버로드합니다.  
  
### <a name="manipulators"></a>조작자  
  
|||  
|-|-|  
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|통화 금액을 필요에 따라 국가별 형식으로 가져옵니다.|  
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|지정된 형식으로 사용하여 시간 구조의 시간을 가져옵니다.|  
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|통화 금액을 필요에 따라 국가별 형식으로 제공합니다.|  
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|시간 구조의 시간 및 사용할 형식 문자열을 제공합니다.|  
|[quoted](../standard-library/iomanip-functions.md#quoted)|삽입 및 추출 연산자를 사용하여 문자열의 편리한 라운드트립을 사용하도록 설정합니다.|  
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|지정된 플래그를 지웁니다.|  
|[setbase](../standard-library/iomanip-functions.md#setbase)|정수의 밑을 설정합니다.|  
|[setfill](../standard-library/iomanip-functions.md#setfill)|오른쪽 맞춤된 디스플레이에서 공백을 채우는데 사용할 문자를 설정합니다.|  
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|지정된 플래그를 설정합니다.|  
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|부동 소수점 값의 전체 자릿수를 설정합니다.|  
|[setw](../standard-library/iomanip-functions.md#setw)|표시 필드의 너비를 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)




