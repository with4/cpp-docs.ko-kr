---
title: "#undef 지시문 (C/c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#undef'
dev_langs:
- C++
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 428831b2718009fc0b471d238cff965f74528a2f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="undef-directive-cc"></a>#undef 지시문 (C/C++)
전에 `#define`으로 만든 이름을 제거(정의 해제)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#undef   
identifier  
  
```  
  
## <a name="remarks"></a>설명  
 `#undef` 지시문의 현재 정의가 제거 *식별자*합니다. 따라서 이후에 나오는 *식별자* 전처리기에 의해 무시 됩니다. 사용 하 여 매크로 정의 제거 하려면 `#undef`, 지정 된 매크로 *식별자* ; 매개 변수 목록을 제공 하지 마십시오.  
  
 이전의 정의가 없는 식별자에 `#undef` 지시문을 적용할 수도 있습니다. 그러면 식별자가 정의되지 않습니다. `#undef` 문에서 매크로가 바뀌지 않습니다.  
  
 대개 `#undef` 지시문은 `#define` 지시문과 쌍을 이루어 식별자가 특별한 의미를 갖는 소스 프로그램에서 영역을 만듭니다. 예를 들어, 소스 프로그램의 특정한 함수가 매니페스트 상수를 사용하여 프로그램의 나머지 부분에 영향을 주지 않는 환경 관련 값을 정의할 수 있습니다. 또한 `#undef` 지시문은 `#if` 지시문과 함께 사용되어 소스 프로그램의 조건부 컴파일을 제어합니다. 참조 [#if, #elif, #else, 및 #endif 지시문](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) 자세한 정보에 대 한 합니다.  
  
 다음 예제에서 `#undef` 지시문이 기호 상수 및 매크로의 정의를 제거합니다. 매크로의 식별자만 제공됩니다.  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft 전용**  
  
 명령줄에서 /U 옵션 뒤에 정의 해제할 매크로 이름을 입력하여 매크로 정의를 해제할 수 있습니다. 이 명령을 실행의 효과의 시퀀스와 같은 `#undef` *매크로 이름* 파일의 시작 부분에 문의 합니다.  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)