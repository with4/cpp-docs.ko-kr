---
title: "관리되는 형식 및 main 함수(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main 함수, 관리되는 응용 프로그램"
  - "관리 코드, main() 함수"
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 관리되는 형식 및 main 함수(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr**를 사용하여 응용 프로그램을 작성할 때 **main\(\)** 함수의 인수는 관리되는 형식이 될 수 없습니다.  
  
 다음은 알맞은 시그니처의 예제입니다.  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## 참고 항목  
 [관리되는 형식](../dotnet/managed-types-cpp-cli.md)