---
title: "컴파일러 오류 C3541 | Microsoft Docs"
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
  - "C3541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3541"
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': typeid는 'auto'를 포함하는 형식에 적용할 수 없습니다.  
  
 지정된 형식에는 `auto` 지정자가 있기 때문에 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자를 적용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 C3541이 발생합니다.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [\/Zc:auto\(변수 형식 추론\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../../windows/typeid-cpp-component-extensions.md)