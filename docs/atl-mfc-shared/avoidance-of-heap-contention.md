---
title: "Avoidance of Heap Contention | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "heap contention"
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Avoidance of Heap Contention
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC와 ATL에서 제공 하는 기본 문자열 관리자는 전역 힙 위에 간단한 래퍼입니다.  이 전역 힙 완전히 스레드\-다중 스레드를 할당 하 고 힙 손상 없이 동시에 메모리를 확보 하도록 보호 됩니다.  스레드 안전성을 보장 하려면 힙 자체에 대 한 액세스를 serialize 해야 합니다.  이 중요 섹션 또는 이와 유사한 잠금 메커니즘을 일반적으로 수행 됩니다.  두 스레드에서 힙에 동시에 액세스 하려고 하면 한 스레드가 다른 스레드의 요청이 완료 될 때까지 차단 됩니다.  많은 응용 프로그램에 대 한이 이런 거의 발생 하지 않으므로 힙 잠금 메커니즘의 성능에 미치는 영향을 무시할 수 있습니다.  그러나 여러 스레드에서 힙에 자주 액세스 하는 응용 프로그램에 대 한 힙 잠금 경합 응용 프로그램을 단일 스레드 \(컴퓨터 에서도 여러 cpu\) 된 경우 보다 느리게 실행 될 수 있습니다.  
  
 사용 하는 응용 프로그램  [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 힙 경합에 특히 취약 하기 때문에 작업에서 `CStringT` 개체는 문자열 버퍼를 재할당 자주 필요.  
  
 스레드 간의 힙 경합을 완화 시키기 위한 방법 중 하나를 개인, 스레드 로컬 힙에서 문자열을 할당 하는 각 스레드입니다.  문자열을 사용 하 여 할당으로 특정 스레드의 할당자 해당 스레드에서만 사용, 할당 자가 스레드로부터 안전한 필요가 없습니다.  
  
## 예제  
 다음 예제에서는 문자열에서 해당 스레드를 사용 하는 자체 개인 스레드로부터 안전한 힙 할당 한 스레드 프로시저를 보여 줍니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/CPP/avoidance-of-heap-contention_1.cpp)]  
  
## 설명  
 여러 스레드가 이와 동일한 프로시저로 실행 될 수 있지만 각 스레드에 고유 힙이 있기 때문 스레드 간 경합이 없는.  또한 스레드가 하나의 복사본을 실행 하는 경우에 각 힙 스레드로부터 안전 하지 않은 팩트 성능이 많이 향상을 제공 합니다.  동시 액세스 로부터 보호 하기 위해 연동된 작업 비용이 사용 힙 만들어집니다.  
  
 보다 복잡 한 스레드 프로시저에 대 한 편리 하 게 스레드 로컬 저장소 \(TLS\) 슬롯에 스레드의 문자열 관리자에 대 한 포인터를 저장할 수 있습니다.  이 스레드의 문자열 관리자에 액세스 하는 스레드 프로시저에서 호출한 다른 함수가 있습니다.  
  
## 참고 항목  
 [Memory Management with CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)