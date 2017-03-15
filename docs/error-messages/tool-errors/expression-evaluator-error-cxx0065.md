---
title: "식 계산기 오류 CXX0065 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0065"
  - "CXX0065"
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

변수에 스택 프레임이 필요합니다.  
  
 현재 범위에 있지만 아직 만들어지지 않은 변수가 식에 들어 있습니다.  
  
 함수에 대한 스택 프레임이 아직 설정되지 않은 상태에서 프롤로그를 한 단계씩 코드 실행 했거나 함수의 종료 코드를 한 단계씩 실행했을 때 이 오류가 발생합니다.  
  
 식을 계산하기 전 스택 프레임이 설정될 때까지 프롤로그 코드를 단계별로 실행하십시오.  
  
 이 오류는 CAN0065와 동일합니다.