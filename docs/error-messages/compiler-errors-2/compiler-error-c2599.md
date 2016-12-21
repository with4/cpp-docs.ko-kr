---
title: "컴파일러 오류 C2599 | Microsoft Docs"
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
  - "C2599"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2599"
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2599
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum' : 열거형의 전방 선언은 허용되지 않습니다.  
  
 컴파일러가 더 이상 관리되는 열거의 전방 선언을 지원하지 않습니다.  
  
 [\/Za](../../build/reference/za-ze-disable-language-extensions.md) 옵션이 지정된 경우에는 열거형의 전방 선언이 허용되지 않습니다.  
  
 다음 샘플에서는 C2599 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2599.cpp  
// compile with: /clr /c  
enum class Status;   // C2599  
  
enum class Status2 { stop2, hold2, go2};   
  
ref struct MyStruct {  
   // Delete the following line to resolve.  
   Status m_status;  
  
   Status2 m_status2;   // OK  
};  
  
enum class Status { stop, hold, go };  
```