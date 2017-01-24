---
title: "컴파일러 오류 C3539 | Microsoft Docs"
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
  - "C3539"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3539"
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3539
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'형식': 템플릿 인수는 'auto'가 포함된 형식일 수 없습니다.  
  
 지정된 템플릿 인수 형식에서는 `auto` 키워드를 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  템플릿 인수에 `auto` 키워드를 지정하지 마십시오.  
  
## 예제  
 다음 예제에서는 C3539가 발생합니다.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)