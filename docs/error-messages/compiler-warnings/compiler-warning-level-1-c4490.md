---
title: "컴파일러 경고 (수준 1) C4490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4490"
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 경고 (수준 1) C4490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override' : 재정의 지정자를 잘못 사용했습니다. 'function'이\(가\) 기본 ref 클래스 메서드와 일치하지 않습니다.  
  
 재정의 지정자를 잘못 사용했습니다.  예를 들어, 인터페이스 함수를 재정의하지 말고 이를 구현해야 합니다.  
  
 자세한 내용은 [Override 지정자](../../windows/override-specifiers-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4490 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```