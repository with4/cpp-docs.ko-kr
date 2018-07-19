---
title: auto 키워드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9b4b9e2526d621e9e9fee1d1f8c05c5a05d3312
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941680"
---
# <a name="auto-keyword"></a>auto 키워드
합니다 **자동** 키워드는 선언 지정자. 그러나 C++ 표준에는 이 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다. Visual c + + 2010 이전를 **자동** 키워드에서 변수를 선언 합니다 *자동* 저장소 클래스, 즉 변수는 로컬 수명을 갖고입니다. Visual c + + 2010을 사용 하 여 시작 합니다 **자동** 선언의 초기화 식에서 형식이 추론 되는 변수를 선언 하는 키워드입니다. [/zc: auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션의 의미를 제어 합니다 **auto** 키워드입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>설명  
 정의 된 **자동** C 프로그래밍 언어 아니라 c + + 프로그래밍 언어의 키워드 변경 합니다.  
  
 다음 항목에 설명 합니다 **자동** 키워드 및 해당 컴파일러 옵션:  
  
-   [자동](../cpp/auto-cpp.md) 의 새 정의 설명 합니다 **자동** 키워드입니다.  
  
  
-   [/Zc: auto (변수 형식 추론)](../build/reference/zc-auto-deduce-variable-type.md) 는 정의 컴파일러에 알리는 컴파일러 옵션을 설명 합니다 **자동** 키워드를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)