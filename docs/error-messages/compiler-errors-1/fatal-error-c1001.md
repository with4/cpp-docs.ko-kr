---
title: "심각한 오류 C1001 | Microsoft Docs"
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
  - "C1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1001"
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

내부 컴파일러 오류\(컴파일러 파일 file, 줄 number\)  
  
 식과 최적화 옵션의 조합으로 인해 컴파일러에서 구문에 대한 올바른 코드를 생성할 수 없습니다.  최적화 옵션을 하나 이상 제거한 다음 오류 메시지에 표시된 줄을 포함하는 함수를 다시 컴파일해 보십시오.  
  
 최적화 옵션을 하나 이상 제거하여 문제를 해결할 수 있습니다.  잘못된 옵션을 확인하려면 오류 메시지가 표시되지 않을 때까지 옵션을 한 번에 하나씩 제거한 다음 다시 컴파일하십시오.  가장 주된 원인이 되는 옵션은 **\/Og**, **\/Oi** 및 `/Oa`입니다.  원인이 되는 옵션을 확인했다면 오류가 발생한 함수에 대해 [optimize](../../preprocessor/optimize.md) pragma를 사용하여 이 옵션을 비활성화하고 이 옵션을 나머지 모듈에 대해 계속 사용할 수 있습니다.  
  
 C1001에 대한 자세한 내용은 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650)을 참조하십시오.  
  
 오류가 보고된 줄이나 해당 줄 주위의 여러 코드 줄을 다시 작성해 보십시오.