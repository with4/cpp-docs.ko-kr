---
title: "How to: Declare and Use Interior Pointers and Managed Arrays (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointers, interior"
  - "arrays [C++], managed"
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare and Use Interior Pointers and Managed Arrays (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] 샘플에서는 선언 내부 배열 포인터를 사용하는 방법을 보여줍니다.  
  
> [!IMPORTANT]
>  이 언어 기능은   **\/clr**  컴파일러 옵션을 지원하지만  **\/ZW**  컴파일러 옵션은 지원하지 않습니다.  
  
## 예제  
  
### 코드  
  
```  
// interior_ptr_arrays.cpp  
// compile with: /clr  
#define SIZE 10  
  
int main() {  
   // declare the array  
   array<int>^ arr = gcnew array<int>(SIZE);  
  
   // initialize the array  
   for (int i = 0 ; i < SIZE ; i++)  
      arr[i] = i + 1;  
  
   // create an interior pointer into the array  
   interior_ptr<int> ipi = &arr[0];  
  
   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);  
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);  
  
   ipi++;  
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);  
}  
```  
  
### Output  
  
```  
1st element in arr holds: 1  
ipi points to memory address whose value is: 1  
after incrementing ipi, it points to memory address whose value is: 2  
```  
  
## 참고 항목  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)