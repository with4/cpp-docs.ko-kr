---
title: "컴파일러 경고 (수준 3) C4414 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4414
dev_langs: C++
helpviewer_keywords: C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76745a1cf505a685bcb9a6d2e74faf98bad77556
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4414"></a>컴파일러 경고(수준 3) C4414
'function': 함수로 short 점프는 near로 변환 됩니다  
  
 Short 점프 명령에서 제한 된 범위 내에 있는 주소로 분기 되는 간단한 명령을 생성 합니다. 명령 대상 주소를 함수 정의 점프 사이의 거리를 나타내는 짧은 오프셋이 포함 되어 있습니다. 연결 하는 동안 함수 함수을 short 오프셋에서 연결할 수 범위 밖으로 이동할 수 있는 이동 되거나 링크 타임 최적화 수 있습니다. 컴파일러에 되도록 jmp 명령이 점프에 대 한 특별 한 레코드를 생성 해야 합니다. 컴파일러에서 변환을 만들었습니다.  
  
 예를 들어 다음 코드에서는 C4414를 생성합니다.  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```