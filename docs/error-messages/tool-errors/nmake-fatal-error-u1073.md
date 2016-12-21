---
title: "NMAKE 심각한 오류 U1073 | Microsoft Docs"
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
  - "U1073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1073"
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 심각한 오류 U1073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'targetname'을\(를\) 만드는 방법을 모릅니다.  
  
 지정한 대상이 없으며 실행할 명령이 없고 적용할 유추 규칙이 없습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  대상 이름의 맞춤법을 확인합니다.  
  
2.  *targetname*이 의사\(pseudo\) 대상인 경우 다른 설명 블록에 대상으로 지정합니다.  
  
3.  *targetname*이 매크로 호출이면 null 문자열로 확장되지 않도록 합니다.