---
title: "컴파일러 경고 (수준 4) C4623 | Microsoft Docs"
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
  - "C4623"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4623"
ms.assetid: e630d8d0-f6ea-469c-a74f-07b027587225
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 4) C4623
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'`derived class`': 기본 클래스의 기본 생성자에 액세스할 수 없거나 이러한 생성자가 삭제되므로 기본 생성자가 암시적으로 삭제된 것으로 정의됩니다.  
  
 생성자가 기본 클래스에서 액세스할 수 없으며 파생 클래스에 대해 생성되지 않았습니다.  스택에 이 형식의 개체를 만들려고 하면 컴파일러 오류가 발생합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C4623 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4623.cpp  
// compile with: /W4  
#pragma warning(default : 4623)  
class B {  
   B();  
};  
  
class C {  
public:  
   C();  
};  
  
class D : public B {};   // C4623 - to fix, make B's constructor public  
class E : public C {};   // OK - class C constructor is public  
  
int main() {  
   // D d;  will cause an error  
}  
```