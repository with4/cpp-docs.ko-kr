---
title: "링커 도구 경고 LNK4006 | Microsoft Docs"
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
  - "LNK4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4006"
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbol이\(가\) 개체에 이미 정의되어 있습니다. 초 정의가 무시됩니다.  
  
 데코레이팅된 형식으로 표시되는, 지정된 `symbol`이 여러 번 정의되었습니다.  이 경고가 발생할 경우에는 `symbol`이 두 번 추가되지만 첫째 형식만 사용됩니다.  
  
 두 개의 가져오기 라이브러리를 하나로 병합하려고 하면 이 경고가 발생할 수 있습니다.  
  
 C 런타임 라이브러리를 다시 빌드하는 중이면 이 메시지를 무시해도 됩니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  지정된 `symbol`은 [\/Gy](../../build/reference/gy-enable-function-level-linking.md)로 컴파일해서 만든 패키지 함수일 수 있습니다.  이 기호는 둘 이상의 파일에 포함되었지만 컴파일 간에 변경되었습니다.  `symbol`을 포함하는 모든 파일을 다시 컴파일하십시오.  
  
2.  지정된 `symbol`이 서로 다른 라이브러리에 있는 두 멤버 개체에 다르게 정의되어 있습니다.  
  
3.  절대 기호는 각 정의에 서로 다른 값을 사용하여 두 번 정의될 수 있습니다.  
  
4.  라이브러리를 조합할 때 오류 메시지가 수신되면 `symbol`이 추가 중인 라이브러리에 이미 있는 것입니다.