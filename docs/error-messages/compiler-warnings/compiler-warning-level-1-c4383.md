---
title: "컴파일러 경고 (수준 1) C4383 | Microsoft Docs"
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
  - "C4383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4383"
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'instance\_dereference\_operator' : 사용자 정의 'operator' 연산자가 있으면 핸들 역참조의 의미가 달라질 수 있습니다. 피연산자를 명시적으로 지정하려면 연산자를 정적 함수로 작성하십시오.  
  
 관리되는 형식의 역참조 연산자에 대한 사용자 정의 인스턴스 재정의를 추가하면 형식의 역참조 연산자에서 핸들의 개체를 반환할 수 있는지 여부가 재정의될 가능성이 있습니다.  사용자 정의 역참조 연산자는 정적으로 작성하는 것이 좋습니다.  
  
 자세한 내용은 [개체 연산자에 대한 핸들\(^\)](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md) 및 [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)를 참조하십시오.  
  
 또한 기타 언어 컴파일러에서는 참조된 메타데이터를 통해 인스턴스 연산자를 사용할 수 없습니다.  자세한 내용은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C4383 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4383.cpp  
// compile with: /clr /W1  
  
ref struct S {  
   int operator*() { return 0; }   // C4383  
};  
  
ref struct T {  
   static int operator*(T%) { return 0; }  
};   
  
int main() {  
   S s;  
   S^ pS = %s;  
  
   T t;  
   T^ pT = %t;  
   T% rT = *pT;  
}  
```