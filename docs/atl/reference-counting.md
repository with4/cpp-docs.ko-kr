---
title: "Reference Counting | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef method [C++]"
  - "AddRef method [C++], reference counting"
  - "reference counting"
  - "reference counts"
  - "참조, 계산"
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Reference Counting
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 개체는 더 이상 사용 되지 것을 생각 하면 메모리에서 개체를 제거 하려면 자동으로 시도 하지 않습니다.  대신 개체 프로그래머가 사용 되지 않는 개체를 제거 해야 합니다.  프로그래머는 개체 참조 횟수에 따라 제거할 수 있는지 여부를 결정 합니다.  
  
 COM 사용의  **IUnknown** 메서드  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 및  [릴리스](http://msdn.microsoft.com/library/windows/desktop/ms682317), 개체 인터페이스의 참조 횟수를 관리 합니다.  이러한 메서드를 호출 하는 일반적인 규칙은 다음과 같습니다.  
  
-   클라이언트에 대 한 인터페이스 포인터를 받을 때마다 `AddRef` 인터페이스에서 호출 해야 합니다.  
  
-   클라이언트 인터페이스 포인터를 사용 하 여 완료 될 때마다 호출 해야  **릴리스**.  
  
 간단한 구현에서 각 `AddRef` 를 증가 시키고 각 호출  **릴리스** 감소 개체 내의 카운터 변수를 호출 합니다.  카운트는 0으로 반환 될 때 더 이상 인터페이스는 사용자가 및 자체 메모리에서 제거 됩니다.  
  
 각 개체 \(않은 개별 인터페이스\)에 참조 횟수가 계산 되도록 참조 횟수 또한 구현할 수 있습니다.  이 경우 각 `AddRef` 및  **릴리스** 개체에는 중앙 구현 대리자 호출 및  **릴리스** 의 참조 횟수가 0이 되 면 전체 개체를 해제 합니다.  
  
> [!NOTE]
>  때를 `CComObject`\-입니다 파생된 개체 생성을 사용 하는  **새** 연산자, 참조 횟수가 0입니다.  따라서 호출 `AddRef` 성공적으로 만든 후 이루어져야 합니다는 `CComObject`\-파생 개체입니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [Managing Object Lifetimes through Reference Counting](http://msdn.microsoft.com/library/windows/desktop/ms687260)