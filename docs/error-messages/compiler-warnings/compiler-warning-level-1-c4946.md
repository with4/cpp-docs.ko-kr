---
title: "컴파일러 경고 (수준 1) C4946 | Microsoft Docs"
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
  - "C4946"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4946"
ms.assetid: b85cbef0-e053-4de6-9b14-7b0f82d40495
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4946
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관련 클래스 'class1'과\(와\) 'class2' 사이에 reinterpret\_cast가 사용되었습니다.  
  
 관련 형식 간에 캐스팅하는데 [reinterpert\_cast](../../cpp/reinterpret-cast-operator.md)를 사용하면 안 됩니다.  [static\_cast](../../cpp/static-cast-operator.md) 다형성 종류 또는 대신 사용하여 [dynamic\_cast](../../cpp/dynamic-cast-operator.md)을 사용합니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 예를 들어, 다음 코드에서는 C4946 경고가 발생합니다.  
  
```  
// C4946.cpp  
// compile with: /W1  
#pragma warning (default : 4946)  
class a {  
public:  
   a() : m(0) {}  
   int m;  
};  
  
class b : public virtual a {  
};  
  
class b2 : public virtual a {  
};  
  
class c : public b, public b2 {  
};  
  
int main() {  
   c* pC = new c;  
   a* pA = reinterpret_cast<a*>(pC);   // C4946  
   // try the following line instead  
   // a* pA = static_cast<a*>(pC);  
}  
```