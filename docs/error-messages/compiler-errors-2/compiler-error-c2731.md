---
title: "컴파일러 오류 C2731 | Microsoft Docs"
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
  - "C2731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2731"
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 함수를 오버로드할 수 없습니다.  
  
 `main`, `WinMain`, `DllMain` 및 `LibMain` 함수는 오버로드할 수 없습니다.  
  
 다음 샘플에서는 C2731 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2731.cpp  
extern "C" void WinMain(int, char *, char *);  
void WinMain(int, short, char *, char*);   // C2731  
```