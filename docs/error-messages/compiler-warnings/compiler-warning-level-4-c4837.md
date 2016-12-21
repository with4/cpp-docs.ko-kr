---
title: "컴파일러 경고 (수준 4) C4837 | Microsoft Docs"
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
  - "C4837"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4837"
ms.assetid: 9a3c7b6b-ffe4-443d-96af-43deb80d85b4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4837
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

삼중자가 발견되었습니다. '??%c'이\(가\) '%c'\(으\)로 바뀝니다.  
  
 발견된 삼중자를 지정된 문자로 대체합니다.  
  
 컴파일러는 다른 처리가 완료되기 전에 삼중자를 변환합니다.  문자 이스케이프 시퀀스 `\?`를 사용하면 삼중자와 모양이 비슷한 문자 시퀀스가 잘못 해석되는 것을 방지할 수 있습니다.  삼중자에 대한 자세한 내용은 [삼중자](../../c-language/trigraphs.md)를 참조하십시오.  이스케이프 시퀀스에 대한 자세한 내용은 [이스케이프 시퀀스](../../c-language/escape-sequences.md)를 참조하십시오.  
  
 C4837은 기본적으로 표시되지 않습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
1.  소스 코드에서 '?' 문자 중 하나 대신 이스케이프 시퀀스 `\?`를 사용합니다.  
  
## 참고 항목  
 [삼중자](../../c-language/trigraphs.md)   
 [이스케이프 시퀀스](../../c-language/escape-sequences.md)   
 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)