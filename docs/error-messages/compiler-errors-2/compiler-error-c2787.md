---
title: "컴파일러 오류 C2787 | Microsoft Docs"
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
  - "C2787"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2787"
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2787
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 이 개체와 연결된 GUID가 없습니다.  
  
 [\_\_uuidof](../../cpp/uuidof-operator.md) 연산자가 첨부 GUID를 포함하는 사용자 정의 형식을 사용하거나 사용자 정의 형식의 개체를 사용합니다.  이 오류는 인수가 GUID를 포함하지 않는 사용자 정의 형식인 경우에 발생합니다.  
  
 다음 샘플에서는 C2787 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```