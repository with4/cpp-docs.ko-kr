---
title: "컴파일러 오류 C2555 | Microsoft Docs"
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
  - "C2555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2555"
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

' class1::function1': 'class2::function2'과\(와\) 재정의 가상 함수의 반환 형식이 다르거나 공변\(covariant\)이 아닙니다.  
  
 가상 함수와 파생 재정의 함수는 동일한 매개 변수 목록을 사용하지만 반환 형식이 다릅니다.  반환 형식만으로 파생 클래스의 재정의 함수와 기본 클래스의 가상 함수를 구별할 수는 없습니다.  
  
 이 오류를 해결하려면 가상 함수가 호출된 후 반환 값을 캐스팅하십시오.  
  
 이 오류는 \/CLR을 사용하며 컴파일하는 경우에도 발생할 수 있습니다.   예를 들어, 다음의 C\# 선언에 해당하는 Visual C\+\+ 선언을 사용하면 이 오류가 발생할 수 있습니다.  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 이 선언은 아래 선언과 같습니다.  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 C2555에 대한 자세한 내용은 기술 자료 문서 Q240862를 참조하십시오.  
  
 다음 샘플에서는 C2555 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```