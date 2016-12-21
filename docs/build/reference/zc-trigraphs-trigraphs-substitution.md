---
title: "/Zc:trigraphs(삼중자 대체) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션(C++)"
  - "규칙 컴파일러 옵션"
  - "Zc 컴파일러 옵션(C++)"
  - "-Zc 컴파일러 옵션(C++)"
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:trigraphs(삼중자 대체)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Zc:trigraphs**를 지정하면 컴파일러가 해당 문장 부호 문자를 사용하여 삼중자 문자 시퀀스를 바꿉니다.  삼중자 대체 기능을 해제하려면 **\/Zc:trigraphs\-**를 지정합니다.  **\/Zc:trigraphs**는 기본적으로 사용되지 않습니다.  
  
## 구문  
  
```  
/Zc:trigraphs[-]  
```  
  
## 설명  
 삼중자는 연속되는 두 개의 물음표\(??\)와 물음표 이외의 세 번째 문자로 이루어집니다.  예를 들어, 컴파일러는 '\#' 문자를 사용하여 "??\=" 삼중자를 바꿉니다.  삼중자는 특정 문장 부호 문자에 대한 편리한 그래픽 표현을 포함하지 않는 문자 집합이 사용되는 C 소스 파일에서 사용합니다.  
  
 C\/C\+\+ 삼중자 및 삼중자를 사용하는 방법을 보여주는 예제는 [삼중자](../../c-language/trigraphs.md)를 참조하십시오.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)   
 [삼중자](../../c-language/trigraphs.md)