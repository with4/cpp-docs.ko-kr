---
title: "할당 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "allocate"
  - "allocate_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec 키워드[C++], 할당"
  - "allocate __declspec 키워드"
ms.assetid: 67828b31-de60-4c0e-b0a6-ef3aab22641d
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 **allocate** 선언 지정자는 데이터 항목이 할당될 데이터 세그먼트의 이름을 지정합니다.  
  
## 구문  
  
```  
  
__declspec(allocate("  
segname  
")) declarator  
```  
  
## 설명  
 *segname*이라는 이름은 다음 pragma 중 하나를 사용하여 선언해야 합니다.  
  
-   [code\_seg](../preprocessor/code-seg.md)  
  
-   [const\_seg](../preprocessor/const-seg.md)  
  
-   [data\_seg](../preprocessor/data-seg.md)  
  
-   [init\_seg](../preprocessor/init-seg.md)  
  
-   [section](../preprocessor/section.md)  
  
## 예제  
  
```  
// allocate.cpp  
#pragma section("mycode", read)  
__declspec(allocate("mycode"))  int i = 0;  
  
int main() {  
}  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)