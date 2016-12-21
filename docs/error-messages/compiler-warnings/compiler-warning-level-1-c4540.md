---
title: "컴파일러 경고 (수준 1) C4540 | Microsoft Docs"
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
  - "C4540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4540"
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

액세스할 수 없거나 모호한 기본 클래스로 변환하기 위해 dynamic\_cast를 사용했습니다. 'type1'에서 'type2'\(으\)로의 런타임 테스트에 실패합니다.  
  
 한 형식을 다른 형식으로 변환하기 위해 `dynamic_cast`를 사용했습니다.  기본 클래스가 액세스할 수 없거나\(예: `private`\) 모호하므로\(예: 클래스 계층 구조에 여러 번 표시됨\) 컴파일러에서 캐스트가 항상 실패할\(**NULL 반환**\) 것이라고 판단했습니다.  
  
 다음은 이 경고에 대한 예제입니다.  **B** 클래스는 **A** 클래스에서 파생됩니다.  프로그램에서는 `dynamic_cast`를 사용하여 **B** 클래스\(파생 클래스\)를 **A** 클래스로 캐스팅하지만 항상 실패합니다. 이는 **A** 클래스가 `private`이므로 액세스할 수 없기 때문입니다.  **A**에 대한 액세스를 **public**으로 변경하면 이 문제가 해결됩니다.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```