---
title: "ML Error Messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.errors.ml"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MASM (Microsoft Macro Assembler), ML error messages"
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ML Error Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Masm에서는 구성 요소에 의해 생성 된 오류 메시지가 세 가지 범주로 구분 됩니다.  
  
-   **치명적인 오류가 발생 했습니다.** 이 유틸리티는 정상적인 과정을 완료할 수 없습니다 하는 심각한 문제를 나타냅니다.  
  
-   **치명적이 지 않은 오류가 발생 했습니다.** 유틸리티는 해당 프로세스를 완료할 수 있습니다.  만약 그 결과가 원하는 가능성이 아닙니다.  
  
-   **경고입니다.** 이러한 메시지는 원하는 결과 얻기에서 하지 못할 조건을 나타냅니다.  
  
 모든 오류 메시지는 다음 형식을 사용합니다.  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 다음은 각 문자에 대한 설명입니다.  
  
 `Utility`  
 오류 메시지를 전송 하는 프로그램입니다.  
  
 *파일 이름*  
 오류를 생성 하는 조건을 포함 하는 파일입니다.  
  
 *줄*  
 오류 조건이 있는 대략적인 행 합니다.  
  
 *Error\_type*  
 치명적인 오류, 오류 또는 경고입니다.  
  
 *코드*  
 고유한 5 또는 6 자리 오류 코드입니다.  
  
 `Message_text`  
 짧고 일반적인 오류 상황의 설명입니다.  
  
## 참고 항목  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)