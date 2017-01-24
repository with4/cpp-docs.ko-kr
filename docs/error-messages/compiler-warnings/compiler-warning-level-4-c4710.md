---
title: "컴파일러 경고 (수준 4) C4710 | Microsoft Docs"
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
  - "C4710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4710"
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수를 인라이닝하지 못했습니다.  
  
 주어진 함수를 인라인 확장용으로 선택했지만 컴파일러에서 인라이닝을 수행하지 못했습니다.  
  
 인라이닝은 컴파일러의 판단 하에 수행됩니다.  **inline** 키워드는 **register** 키워드와 같이 컴파일러에 대한 힌트로 사용됩니다.  컴파일러에서는 휴리스틱을 사용하여 속도에 중점을 두고 컴파일할 때 코드의 속도를 높이기 위해 특정 함수를 인라인할 것인지 또는 공간에 중점을 두고 컴파일할 때 코드를 작게 만들기 위해 특정 함수를 인라인할 것인지를 결정합니다.  컴파일러에서는 공간에 중점을 두고 컴파일할 때 매우 작은 함수만 인라인합니다.  
  
 일부 경우에서는 컴파일러가 기계적인 이유로 인해 특정 함수를 인라인하지 않습니다.  컴파일러에서 함수를 인라인하지 않는 이유에 대한 설명 목록은 [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)를 참조하십시오.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.