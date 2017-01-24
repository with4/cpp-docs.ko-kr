---
title: "컴파일러 오류 C3894 | Microsoft Docs"
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
  - "C3894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3894"
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 'class' 클래스의 클래스 생성자에서만 initonly 정적 데이터 멤버를 왼쪽 항의 값\(l\-value\)으로 사용할 수 있습니다.  
  
 정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 해당 선언 지점 또는 정적 생성자에서만 l\-value로 사용할 수 있습니다.  
  
 인스턴스 \(비정적\) initonly 데이터 멤버는 해당 선언 지점 또는 인스턴스 \(비정적\) 생성자에서만 l\-value로 사용할 수 있습니다.  
  
 다음 샘플에서는 C3894 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```