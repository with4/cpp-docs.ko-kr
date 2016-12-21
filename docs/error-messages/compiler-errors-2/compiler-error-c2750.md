---
title: "컴파일러 오류 C2750 | Microsoft Docs"
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
  - "C2750"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2750"
ms.assetid: 30450034-feb5-448c-9655-b8c5f3639695
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2750
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 참조 형식에는 'new'를 사용할 수 없습니다. 대신 'gcnew'를 사용하십시오.  
  
 가비지 수집된 힙에 인스턴스가 배치되도록 CLR 형식의 인스턴스를 만들려면 [gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)를 사용해야 합니다.  
  
 다음 샘플에서는 C2750 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2750.cpp  
// compile with: /clr  
ref struct Y1 {};  
  
int main() {  
   Y1 ^ x = new Y1;   // C2750  
  
   // try the following line instead  
   Y1 ^ x2 = gcnew Y1;  
}  
```