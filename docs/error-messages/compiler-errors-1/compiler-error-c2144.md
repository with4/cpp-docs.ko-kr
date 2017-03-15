---
title: "컴파일러 오류 C2144 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2144"
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# 컴파일러 오류 C2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류 : 'type'은\(는\) 'token' 다음에 와야 합니다.  
  
 컴파일러에 `token`이 필요하지만 `type`이 대신 발견되었습니다.  
  
 이 오류는 닫는 중괄호, 오른쪽 괄호 또는 세미콜론이 누락된 경우에 발생할 수 있습니다.  
  
 C2144는 공백 문자가 포함된 CLR 키워드로 매크로를 만들려는 경우에도 발생할 수 있습니다.  
  
 형식을 전달하려고 하는 경우에도 C2144가 발생할 수 있습니다.  자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2144 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## 예제  
 다음 샘플에서는 C2144 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```