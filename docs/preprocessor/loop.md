---
title: "루프 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs: C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2f8e7274ad5da4f0bb3978b18be62952006f8ffd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="loop"></a>루프
자동 평행화 도우미에서 루프 코드를 고려하는 방법을 제어하고 자동 벡터화 도우미에서 루프를 고려 대상에서 제외합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma loop( hint_parallel(n) )  
```  
  
```  
  
#pragma loop( no_vector )  
```  
  
```  
  
#pragma loop( ivdep )  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hint_parallel(` `n` `)`  
 이 루프가 `n` 스레드에서 평행화되어야 함을 알리는 컴파일러에 대한 힌트입니다. 여기서 `n`은 양의 정수 리터럴 또는 0입니다. `n`이 0일 경우 런타임에 최대 스레드 수가 사용됩니다. 이는 명령이 아니라 컴파일러에 대한 힌트이며 루프가 평행화된다는 보장은 없습니다. 루프에 데이터 종속성 또는 구조적 문제(예: 루프 본문을 벗어나 사용되는 스칼라에 루프가 저장함)가 있는 경우에는 루프가 평행화되지 않습니다.  
  
 컴파일러는 경우가 아니면이 옵션을 무시 된 [/Qpar](../build/reference/qpar-auto-parallelizer.md) 컴파일러 스위치를 지정 합니다.  
  
 `no_vector`  
 기본적으로 자동 벡터화 도우미는 설정되어 있으며 혜택이 있는 것으로 평가되는 모든 루프를 벡터화하려고 합니다. 다음 루프에 대해 자동 벡터화 도우미를 사용하지 않으려면 이 pragma를 지정하십시오.  
  
 `ivdep`  
 이 루프에 대한 벡터 종속성을 무시할 것을 알리는 컴파일러에 대한 힌트입니다. 이를 `hint_parallel`과 함께 사용하십시오.  
  
## <a name="remarks"></a>설명  
 `loop` pragma를 사용하려면 이 pragma를 루프 정의 안이 아니라 루프 정의 바로 앞에 배치하십시오. 그러면 pragma가 뒤에 오는 루프의 범위에 적용됩니다. 순서에 상관없이 루프에 여러 pragma를 적용할 수 있지만 각 pragma를 별도의 pragma 문에 지정해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [자동 병렬화 및 자동 벡터화](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)