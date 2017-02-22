---
title: "컴파일러 오류 C2430 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2430"
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C2430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier'에 인덱스 레지스터가 두 개 이상 있습니다.  
  
 둘 이상의 레지스터의 배율이 조정되었습니다.  컴파일러가 배율 조정된 인덱싱을 지원하지만 하나의 레지스터 배율만 조정할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C2430 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```