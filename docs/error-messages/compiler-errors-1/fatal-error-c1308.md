---
title: "심각한 오류 C1308 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1308"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1308"
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 심각한 오류 C1308
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링크 어셈블리는 지원되지 않습니다.  
  
 netmodule을 링커에 대한 입력 파일로 사용할 수 있지만 어셈블리는 사용할 수 없습니다.  이 오류는 `/clr:safe`로 컴파일된 어셈블리를 링크하려고 할 때 발생할 수 있습니다.  
  
 자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하십시오.  
  
 다음 샘플에서는 C1308 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 두 번째 코드 파일:  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```