---
title: "컴파일러 오류 C2708 | Microsoft Docs"
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
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 실제 매개 변수 길이\(바이트\)가 이전 호출 또는 참조와 다릅니다.  
  
 [\_\_stdcall](../../cpp/stdcall.md) 함수 앞에 프로토타입이 와야 합니다.  그렇지 않으면 컴파일러는 함수에 대한 첫 번째 호출을 프로토타입으로 해석합니다. 이 오류는 컴파일러가 일치하지 않는 호출을 발견할 경우에 발생합니다.  
  
 이 오류를 해결하려면 함수 프로토타입을 추가하십시오.