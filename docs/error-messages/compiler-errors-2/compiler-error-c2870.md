---
title: "컴파일러 오류 C2870 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2870"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2870"
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2870
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name' : 네임스페이스 정의는 파일 범위에서 사용하거나 다른 네임스페이스 정의 바로 안쪽에 사용해야 합니다.  
  
 `name` 네임 스페이스를 잘못 정의했습니다.  네임스페이스는 파일 범위\(모든 블록 및 클래스 외부\)에 정의하거나 다른 네임스페이스 바로 안쪽에 정의해야 합니다.  
  
 다음 샘플에서는 C2870 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```