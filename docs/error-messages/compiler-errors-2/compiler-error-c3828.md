---
title: "컴파일러 오류 C3828 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3828"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3828"
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3828
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'object type': 관리되는 클래스 또는 WinRT 클래스의 인스턴스를 만드는 동안 배치 인수를 사용할 수 없습니다.  
  
 관리되는 형식 또는 Windows 런타임 형식의 개체를 만들 때는 연산자 [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) 또는 [new](../../cpp/new-operator-cpp.md)의 배치 형식을 사용할 수 없습니다.  
  
 다음 샘플에서는 C3828 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```