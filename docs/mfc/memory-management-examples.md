---
title: "메모리 관리: 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc937e64a09ecedb127524de384d48860da5764f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-examples"></a>메모리 관리: 예
이 문서에서는 MFC 프레임 할당과 힙 할당에 대 한 성능을 각 메모리 할당의 세 가지 일반적인 종류를 설명 합니다.  
  
-   [바이트 배열](#_core_allocation_of_an_array_of_bytes)  
  
-   [데이터 구조](#_core_allocation_of_a_data_structure)  
  
-   [개체](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a>바이트 배열 할당  
  
#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>프레임에 바이트 배열을 할당 하려면  
  
1.  다음 코드에 의해 표시 된 것 처럼 배열을 정의 합니다. 배열을 자동으로 삭제 하 고 메모리는 배열 변수가 해당 범위를 벗어날 때 회수 합니다.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]  
  
#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>힙의 바이트 (또는 기본 데이터 형식)의 배열을 할당 하려면  
  
1.  사용 하 여는 **새** 이 예제에 표시 된 배열 구문 사용 하 여 연산자:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]  
  
#### <a name="to-deallocate-the-arrays-from-the-heap"></a>힙에서 배열을 할당을 취소 하려면  
  
1.  사용 하 여 **삭제** 다음과 같이 연산자:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a>데이터 구조의 할당  
  
#### <a name="to-allocate-a-data-structure-on-the-frame"></a>프레임에는 데이터 구조를 할당 하려면  
  
1.  다음과 같이 구조체 변수를 정의 합니다.  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]  
  
     구조에서 사용한 메모리는 해당 범위를 벗어나면 회수 됩니다.  
  
#### <a name="to-allocate-data-structures-on-the-heap"></a>힙에 데이터 구조를 할당  
  
1.  사용 하 여 **새** 힙에 데이터 구조를 할당 하 고 **삭제** 다음 예에 표시 된 것 처럼, 할당을 취소할 수:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a>개체의 할당  
  
#### <a name="to-allocate-an-object-on-the-frame"></a>프레임에 개체를 할당  
  
1.  개체를 다음과 같이 선언 합니다.  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]  
  
     개체에 대 한 소멸자는 개체의 범위를 벗어날 때 자동으로 호출 됩니다.  
  
#### <a name="to-allocate-an-object-on-the-heap"></a>힙의 개체를 할당  
  
1.  사용 하 여는 **새** 연산자, 개체에 대 한 포인터를 반환 하는 힙의 개체에 할당할 수 있습니다. 사용 하 여는 **삭제** 으로 삭제 하는 연산자입니다.  
  
     힙 및 프레임 다음 예제에서는 `CPerson` 생성자에 인수가 없습니다.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]  
  
     경우에 대 한 인수는 `CPerson` 생성자에 대 한 포인터는 `char`, 프레임 할당 문은입니다.  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]  
  
     힙 할당에 대 한 문이입니다.  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [메모리 관리: 힙 할당](../mfc/memory-management-heap-allocation.md)

