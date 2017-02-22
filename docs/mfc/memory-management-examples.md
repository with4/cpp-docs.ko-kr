---
title: "메모리 관리: 예 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "배열[C++], 리소스 할당"
  - "배열[C++], 메모리 관리"
  - "데이터 구조[C++]"
  - "데이터 구조[C++], 메모리 할당"
  - "예제[MFC], 메모리 할당"
  - "프레임 할당"
  - "힙 할당, 예제"
  - "메모리 할당[C++], 배열"
  - "메모리 할당[C++], 데이터 구조"
  - "메모리 할당[C++], 예제"
  - "메모리 할당[C++], 개체"
  - "MFC[C++], 메모리 관리"
  - "개체[C++], 메모리 할당"
  - "개체[C++], 메모리 할당"
  - "구조체 메모리 할당"
  - "형식[C++], 메모리 할당"
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 메모리 관리: 예
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This article describes how MFC performs frame allocations and heap allocations for each of the three typical kinds of memory allocations:  
  
-   [An array of bytes](#_core_allocation_of_an_array_of_bytes)  
  
-   [A data structure](#_core_allocation_of_a_data_structure)  
  
-   [개체입니다.](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Allocation of an Array of Bytes  
  
#### To allocate an array of bytes on the frame  
  
1.  Define the array as shown by the following code.  The array is automatically deleted and its memory reclaimed when the array variable exits its scope.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/CPP/memory-management-examples_1.cpp)]  
  
#### To allocate an array of bytes \(or any primitive data type\) on the heap  
  
1.  Use the **new** operator with the array syntax shown in this example:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/CPP/memory-management-examples_2.cpp)]  
  
#### To deallocate the arrays from the heap  
  
1.  Use the **delete** operator as follows:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/CPP/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Allocation of a Data Structure  
  
#### To allocate a data structure on the frame  
  
1.  Define the structure variable as follows:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/CPP/memory-management-examples_4.cpp)]  
  
     The memory occupied by the structure is reclaimed when it exits its scope.  
  
#### To allocate data structures on the heap  
  
1.  Use **new** to allocate data structures on the heap and **delete** to deallocate them, as shown by the following examples:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/CPP/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> Allocation of an Object  
  
#### To allocate an object on the frame  
  
1.  Declare the object as follows:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/CPP/memory-management-examples_6.cpp)]  
  
     The destructor for the object is automatically invoked when the object exits its scope.  
  
#### To allocate an object on the heap  
  
1.  Use the **new** operator, which returns a pointer to the object, to allocate objects on the heap.  Use the **delete** operator to delete them.  
  
     The following heap and frame examples assume that the `CPerson` constructor takes no arguments.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/CPP/memory-management-examples_7.cpp)]  
  
     If the argument for the `CPerson` constructor is a pointer to `char`, the statement for frame allocation is:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/CPP/memory-management-examples_8.cpp)]  
  
     The statement for heap allocation is:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/CPP/memory-management-examples_9.cpp)]  
  
## 참고 항목  
 [메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)