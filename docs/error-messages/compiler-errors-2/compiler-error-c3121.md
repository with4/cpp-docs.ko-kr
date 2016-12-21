---
title: "컴파일러 오류 C3121 | Microsoft Docs"
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
  - "C3121"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3121"
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3121
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class\_name' 클래스의 GUID를 변경할 수 없습니다.  
  
 [\_\_declspec\(uuid\)](../../cpp/uuid-cpp.md)를 사용하여 클래스 ID를 변경하려고 했습니다.  
  
 예를 들어, 다음 코드에서는 C3121 오류가 발생합니다.  
  
```  
// C3121.cpp  
[emitidl];  
[module(name="MyLibrary")];  
  
[coclass, uuid="00000000-0000-0000-0000-111111111111"]  
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121  
{  
};  
int main()  
{  
}  
```