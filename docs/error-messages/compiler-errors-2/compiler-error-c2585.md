---
title: "컴파일러 오류 C2585 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2585"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2585"
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2585
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type'\(으\)로의 명시적 변환이 모호합니다.  
  
 형식 변환은 둘 이상의 결과를 생성할 수 있습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  클래스 또는 구조체 형식으로부터의 변환이 여러 상속을 기반으로 합니다.  형식이 동일 기본 클래스를 두 번 이상 상속하는 경우에는 변환 함수 또는 연산자는 범위 결정 연산자\(`::`\)를 사용하여 변환에 사용할 상속된 클래스를 지정해야 합니다.  
  
2.  변환 연산자와 생성자가 동일하게 변환되도록 정의되었습니다.