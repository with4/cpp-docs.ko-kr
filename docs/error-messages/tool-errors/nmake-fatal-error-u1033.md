---
title: "NMAKE 심각한 오류 U1033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1033"
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류: 예기치 못한 'string'입니다.  
  
 문자열이 메이크파일의 유효한 구문이 아닙니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  줄의 시작 부분에 인라인 파일의 꺾쇠괄호\(**\<\<**\) 닫는 짝이 없으면 다음 오류가 발생합니다.  
  
    ```  
    syntax error : 'EOF' unexpected  
    ```  
  
2.  메이크파일의 매크로 정의에 선행 이름 없이 등호\(**\=**\)가 들어 있거나 정의할 이름이 확장되지 않는 매크로이면 다음 오류가 발생합니다.  
  
    ```  
    syntax error : '=' unexpected  
    ```  
  
3.  TOOLS.INI 파일의 주석줄에 있는 세미콜론\(**;**\)이 줄의 시작 부분에 없으면 다음 오류가 발생합니다.  
  
    ```  
    syntax error : ';' unexpected  
    ```  
  
4.  메이크파일을 워드 프로세서로 작성하면 다음 오류가 발생합니다.  
  
    ```  
    syntax error : ':' unexpected  
    ```