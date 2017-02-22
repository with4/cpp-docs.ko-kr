---
title: "링커 도구 오류 LNK2020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2020"
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# 링커 도구 오류 LNK2020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

확인되지 않은 토큰 'token'  
  
 정의되지 않은 외부 참조 오류에서와 마찬가지로, 예외적으로 메타데이터를 통해 참조됩니다.  메타데이터에서 모든 함수와 데이터가 정의되어야 합니다.  
  
 해결 방법:  
  
-   누락된 함수나 데이터를 정의합니다. 또는  
  
-   누락된 함수나 데이터가 이미 정의되어 있는 개체 파일이나 라이브러리를 포함시킵니다.  
  
## 예제  
 다음 샘플에서는 LNK2020 오류가 발생합니다.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## 예제  
 LNK2020은 관리되는 템플릿 형식의 변수를 만들었지만 이 형식을 인스턴스화하지 않은 경우에도 발생합니다.  
  
 다음 샘플에서는 LNK2020 오류가 발생합니다.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```