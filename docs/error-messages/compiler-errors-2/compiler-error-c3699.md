---
title: "컴파일러 오류 C3699 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3699"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3699"
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3699
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 'type' 형식에 이 간접 참조를 사용할 수 없습니다.  
  
 `type`에 허용되지 않는 간접 참조를 사용하려고 했습니다.  
  
## 예제  
 다음 샘플에서는 C3699 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## 예제  
 trivial 속성은 참조 형식일 수 없습니다.  자세한 내용은 [property](../../windows/property-cpp-component-extensions.md)를 참조하십시오.  다음 샘플에서는 C3699 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## 예제  
 "포인터에 대한 포인터" 구문을 사용하는 것은 추적 참조에 대한 핸들을 사용하는 것과 같습니다.  다음 샘플에서는 C3699 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```