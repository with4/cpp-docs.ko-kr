---
title: "컴파일러 오류 C3537 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3537"
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': 'auto'가 포함된 형식으로 캐스팅할 수 없습니다.  
  
 형식에 `auto` 키워드가 포함되어 있고 기본 [\/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션이 적용 중이기 때문에 변수를 지정된 형식으로 캐스팅할 수 없습니다.  
  
## 예제  
 다음 코드에서는 변수가 `auto` 키워드를 포함하는 형식으로 캐스팅되므로 C3537이 발생합니다.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)