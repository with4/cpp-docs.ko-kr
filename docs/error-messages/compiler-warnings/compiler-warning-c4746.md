---
title: "컴파일러 경고 C4746 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# 컴파일러 경고 C4746
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\<expression\>'의 volatile 액세스를 사용하려면 \/volatile:\[iso&#124;ms\] 설정이 필요합니다. \_\_iso\_volatile\_load\/store 내장 함수를 사용해 보십시오.  
  
 C4746 휘발성 변수에 직접 액세스할 때마다 생성 됩니다.  개발자가 현재 지정 된 휘발성 특정 모델에 의해 영향을 받는 코드 위치를 확인 하는 것 \(으로 제어할 수 있는 [](../../build/reference/volatile-volatile-keyword-interpretation.md "-volatile (volatile Keyword Interpretation)") 일시적\/ 컴파일러 옵션\).  특히, \/volatile:ms를 사용 하는 경우 컴파일러에서 생성 된 하드웨어 메모리 장벽을 찾기에 유용할 수 있습니다.  
  
 \_\_Iso\_volatile\_load\/저장 내장 휘발성 모델에 의해 영향을 받지 않고 휘발성 메모리를 명시적으로 액세스를 사용할 수 있습니다.  이러한 내장 함수를 사용 하 여 C4746가 트리거되지 않습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.