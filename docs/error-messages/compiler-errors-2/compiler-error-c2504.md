---
title: "컴파일러 오류 C2504 | Microsoft Docs"
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
  - "C2504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2504"
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2504
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 기본 클래스를 정의하지 않았습니다.  
  
 기본 클래스가 선언되었으나 정의되지는 않았습니다.  가능한 원인  
  
1.  포함 파일이 없습니다.  
  
2.  외부 기본 클래스가 [extern](../../cpp/using-extern-to-specify-linkage.md)을 사용하여 선언되지 않았습니다.  
  
 다음 샘플에서는 C2504 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 \/\/ OK  
  
```  
class C{};  
class D : public C {};  
```