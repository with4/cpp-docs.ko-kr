---
title: "수학 오류 M6111 | Microsoft Docs"
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
  - "M6111"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6111"
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 수학 오류 M6111
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스택 언더플로가 발생했습니다.  
  
 8087\/287\/387 보조 프로세서 또는 에뮬레이터에서 부동 소수점 연산의 스택 언더플로가 발생했습니다.  
  
 일반적으로 이 오류는 값을 반환하지 않는 `long double` 함수에 대한 호출 때문에 발생합니다.  예를 들어, 다음 코드를 컴파일하여 실행하면 이 오류가 생성됩니다.  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 프로그램은 종료 코드 139로 종료됩니다.