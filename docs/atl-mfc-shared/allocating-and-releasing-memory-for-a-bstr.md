---
title: "메모리 할당 및 해제에 대 한 BSTR | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- bstr
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 282ceac05587452fad750f05b642c0ffd5b929a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>BSTR에 대해 메모리 할당 및 해제
만들 때 `BSTR`s 및 COM 개체 사이 어떻게 전달, 메모리 누수를 방지 하기 위해 사용 하는 메모리를 처리 하는 방법에 주의 해야 합니다. 경우는 `BSTR` 인터페이스 내에서 유지 되며, 완료 되 면 메모리를 해제 해야 합니다. 그러나, 한 `BSTR` 인터페이스 외부로 과정을 받는 개체는 해당 메모리 관리 담당 합니다.  
  
 에 대 한 메모리 할당 및 해제에 대 한 규칙을 할당 하는 일반적으로 `BSTR`s는 다음과 같습니다.  
  
-   필요한 함수를 호출 하는 경우는 `BSTR` 인수에 대 한 메모리를 할당 해야는 `BSTR` 호출 전에 나중에 놓습니다. 예:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   반환 하는 함수를 호출 하는 경우는 `BSTR`, 문자열을 직접 해제 해야 합니다. 예:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   반환 하는 함수를 구현 하는 경우는 `BSTR`, 문자열을 할당 하지만 해제 하지는 않습니다. 수신 함수는 메모리를 해제 합니다. 예:  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx)   
 [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)

