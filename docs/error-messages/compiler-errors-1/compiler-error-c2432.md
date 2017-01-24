---
title: "컴파일러 오류 C2432 | Microsoft Docs"
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
  - "C2432"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2432"
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2432
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'에 16비트 데이터에 대한 참조가 잘못되었습니다.  
  
 16비트 레지스터가 인덱스 또는 기본 레지스터로 사용되었습니다.  컴파일러가 16비트 데이터 참조를 지원하지 않습니다. 32비트 코드에 대한 컴파일을 수행할 때 16비트 레지스터를 인덱스 또는 기본 레지스터로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2432 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```