---
title: "컴파일러 경고 (수준 3) C4414 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4414"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4414"
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 3) C4414
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수로의 short 점프는 near로 변환됩니다.  
  
 Short 점프는 명령으로부터 제한된 범위 내에 있는 주소로 분기되는 간단한 명령을 생성합니다.  이 명령에는 점프와 대상 주소인 함수 정의 사이의 거리를 나타내는 short 오프셋이 포함되어 있습니다.  링크하는 동안 함수가 이동되거나 링크 시간 최적화로 인해 함수가 short 오프셋에서 도달할 수 있는 범위를 벗어날 수 있습니다.  컴파일러에서는 점프에 대해 특별한 레코드를 생성해야 합니다. 이 때 점프 명령은 NEAR 또는 FAR이어야 합니다.  컴파일러에서 변환을 만들었습니다.  
  
 예를 들어, 다음 코드에서는 C4414 경고가 발생합니다.  
  
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