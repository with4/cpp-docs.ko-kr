---
title: "식 계산기 오류 CXX0017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0017"
  - "CXX0017"
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기호를 찾을 수 없습니다.  
  
 식에 지정한 기호를 찾을 수 없습니다.  
  
 이 오류의 가능한 원인 중 하나는 기호 이름에 대\/소문자가 일치하지 않기 때문입니다.  C 및 C\+\+ 언어는 대\/소문자를 구분하는 언어이므로 기호 이름은 소스에 정의된 대\/소문자와 정확하게 일치해야 합니다.  
  
 이 오류는 디버깅하는 동안 변수를 감시하기 위해 변수를 형식 변환할 때 발생합니다.  `typedef`는 형식에 새 이름을 선언하지만 새 형식은 정의하지 않습니다.  디버거에서 형식을 변환하려면 정의된 형식의 이름이 있어야 합니다.  
  
 이 오류는 CAN0017과 동일합니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  이 기호가 사용되는 프로그램의 위치에서 이미 선언되어 있는지 확인하십시오.  
  
2.  디버거에서 `typedef`로 정의된 이름 대신에 실제 형식 이름을 사용하여 변수를 캐스팅하십시오.