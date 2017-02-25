---
title: "컴파일러 오류 C2435 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2435"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2435"
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C2435
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 동적 초기화에는 관리되는 CRT가 있어야 합니다. \/clr:safe를 사용해서 컴파일할 수 없습니다.  
  
 응용 프로그램 도메인별로 전역 변수를 초기화하려면 안정성을 확인할 수 있는 이미지를 생성하지 않는 `/clr:pure`를 사용하여 컴파일된 CRT가 필요합니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하십시오.  
  
 다음 샘플에서는 C2435 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```