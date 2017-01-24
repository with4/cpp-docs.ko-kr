---
title: "컴파일러 오류 C3672 | Microsoft Docs"
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
  - "C3672"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3672"
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3672
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

의사\(pseudo\) 소멸자 식은 함수 호출의 일부로만 사용할 수 있습니다.  
  
 소멸자를 잘못 호출했습니다.  자세한 내용은 [소멸자](../../cpp/destructors-cpp.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3672 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```