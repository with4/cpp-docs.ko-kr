---
title: "컴파일러 경고 (수준 1) C4711 | Microsoft Docs"
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
  - "C4711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4711"
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인라인 확장을 위해 'function' 함수가 선택되었습니다.  
  
 주어진 함수에 대해 인라이닝 표시를 하지 않았지만 컴파일러에서 인라이닝을 수행했습니다.  
  
 [\/Ob2](../../build/reference/ob-inline-function-expansion.md)가 지정되어 있으면 C4711이 활성화됩니다.  
  
 인라이닝은 컴파일러의 판단 하에 수행됩니다.  이 경고는 정보를 제공하기 위한 것입니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  경고를 활성화하려면 [\#pragma warning](../../preprocessor/warning.md)을 사용하십시오.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.