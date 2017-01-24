---
title: "Allocating and Releasing Memory for a BSTR | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "bstr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR, 메모리 할당"
  - "메모리[C++], 해제"
  - "메모리 할당, BSTR"
  - "memory deallocation, BSTR memory"
  - "memory deallocation, string memory"
  - "문자열[C++], 해제"
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Allocating and Releasing Memory for a BSTR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

만들 때 `BSTR`s 및 해당 COM 개체 간에 전달, 메모리 누수를 방지 하기 위해 사용 하는 메모리 처리에 주의 해야 합니다.  경우는 `BSTR` 상태로 인터페이스 내에서 사용 해야 자유 메모리에 작업이 완료 되 면.  그러나, 경우는 `BSTR` 가공 인터페이스에서 받는 개체는 메모리 관리에 대 한 책임.  
  
 일반적으로 할당 하 고 메모리를 해제 하는 방법에 대 한 규칙에 할당 된 `BSTR`s는 다음과 같습니다.  
  
-   필요한 함수를 호출 하면는 `BSTR` 인수, 메모리를 할당 해야는 `BSTR` 호출 하기 전에 나중에 해제 합니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   반환 하는 함수를 호출을 `BSTR`, 문자열을 직접 해제 해야 합니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   반환 하는 함수를 구현 된 `BSTR`, 문자열을 할당만 하 고 해제 하지 않습니다.  수신 함수에서 메모리를 해제 합니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/CPP/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## 참고 항목  
 [문자열](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md)   
 [SysAllocString](http://msdn.microsoft.com/ko-kr/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)   
 [SysFreeString](http://msdn.microsoft.com/ko-kr/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)