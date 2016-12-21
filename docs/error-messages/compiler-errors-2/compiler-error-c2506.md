---
title: "컴파일러 오류 C2506 | Microsoft Docs"
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
  - "C2506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2506"
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : '\_\_declspec\(modifier\)'는 이 기호에 적용할 수 없습니다.  
  
 관리되는 클래스의 정적 멤버에 대한 프로세스별 또는 응용 프로그램 도메인별 기호를 선언할 수 없습니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2506 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```