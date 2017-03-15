---
title: "How to: Declare Value Types with the interior_ptr Keyword (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ptr keyword"
  - "value types, declaring"
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare Value Types with the interior_ptr Keyword (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`interior_ptr` 는 값 형식을 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  이 언어 기능은   **\/clr**  컴파일러 옵션을 지원하지만  **\/ZW**  컴파일러 옵션은 지원하지 않습니다.  
  
## 예제  
  
### 설명  
 다음 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 예제는 값 형식과  `interior_ptr` 의 사용하는 방법을 보여줍니다.  
  
### 코드  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### Output  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## 예제  
  
### 설명  
 값 형식에는  `this`  포인터를 가져와 interior\_ptr로 계산합니다.  
  
 `V`  값 형식의 비정적 멤버 함수 본문에서,  `this` 는 함수를 호출 하는 개체의 주소 값을 갖는   `interior_ptr<V>`  형식의 표현입니다.  
  
### 코드  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## 예제  
  
### 설명  
 다음 샘플에 정적 멤버를 사용하여 주소 연산자를 사용하는 방법을 보여줍니다.  
  
 Visual C\+\+ 형식의 정적 멤버의 주소는 네이티브 포인터를 생성합니다.  정적 값 형식 멤버의 주소는 값 형식 멤버 런타임 힙에 할당되고 가비지 수집기에서 이동할 수 있기 때문에 관리되는 포인터입니다.  
  
### 코드  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### Output  
  
```  
22  
23  
hello  
```  
  
## 참고 항목  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)