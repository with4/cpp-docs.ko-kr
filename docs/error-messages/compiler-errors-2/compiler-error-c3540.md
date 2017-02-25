---
title: "컴파일러 오류 C3540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3540"
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': sizeof는 'auto'를 포함하는 형식에 적용할 수 없습니다.  
  
 지정된 형식에는 `auto` 지정자가 있기 때문에 [sizeof](../../cpp/sizeof-operator.md) 연산자를 적용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 C3540이 발생합니다.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [\/Zc:auto\(변수 형식 추론\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 연산자](../../cpp/sizeof-operator.md)