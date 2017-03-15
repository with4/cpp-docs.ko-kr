---
title: "컴파일러 경고(수준 1) C4788 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4788"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4788"
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고(수준 1) C4788
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 식별자가 'number'개 문자로 잘렸습니다.  
  
 컴파일러에서 사용할 수 있는 함수 이름의 최대 길이는 제한되어 있습니다.  EH\/SEH 코드에 대해 컴파일러에서 funclet이 생성되면 "\_\_catch", "\_\_unwind" 또는 기타 문자열의 경우와 같이 텍스트를 함수 이름 앞에 추가하여 funclet 이름을 만듭니다.  
  
 결과로 생성되는 funclet 이름이 너무 긴 경우 컴파일러에서 이 이름을 자르고 C4788 경고를 표시합니다.  
  
 이 경고를 해결하려면 원래 함수 이름을 짧게 지정하십시오.  이 함수가 C\+\+ 템플릿 함수 또는 메서드인 경우 이름의 일부에 typedef를 사용하십시오.  예를 들면 다음과 같습니다.  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 이는 다음으로 대체됩니다.  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 이 경고에는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴파일러에서만 발생합니다.