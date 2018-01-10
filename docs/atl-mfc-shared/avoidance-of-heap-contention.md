---
title: "힙 경합 방지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f17f73efc8fba19bb129e3b118f8a4357444aad0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="avoidance-of-heap-contention"></a>힙 경합 방지
MFC와 ATL에서 제공 하는 기본 문자열 관리자는 간단한 래퍼는 전역 힙 위에입니다. 이 글로벌 힙에 완벽 하 게 스레드로부터 안전, 즉 여러 스레드 할당 되 고에서 힙 손상 시 키 지 않고 동시에 메모리를 해제할 수 있습니다. 스레드 보안을 제공 하려면 힙에 자체에 대 한 액세스를 serialize 하는 데에 있습니다. 이 임계 영역 또는 비슷한 잠금 메커니즘으로 일반적으로 수행 됩니다. 두 개의 스레드를 힙에 동시에 액세스 하려고 때마다 다른 스레드의 요청이 완료 될 때까지 한 스레드가 차단 됩니다. 대부분의 응용 프로그램에 대 한 이러한 상황에서 거의 발생 하 고 힙의 잠금 메커니즘 성능에 미치는 영향은 매우 적습니다. 그러나 힙에 여러 스레드에서 자주 액세스 하는 응용 프로그램에 대 한 힙의 잠금에 대 한 경합이 (여러 Cpu 사용 하 여 컴퓨터)에 단일 스레드는 경우 보다 느리게 실행 응용 프로그램을 발생할 수 있습니다.  
  
 사용 하는 응용 프로그램 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 힙 경합에 특히 취약 하기 때문에 대 한 작업 `CStringT` 개체 문자열 버퍼의 재할당을 자주 필요 합니다.  
  
 스레드 간 힙 경합을 해결 하는 한 가지 방법은 각 스레드에 private, 스레드 로컬 힙에서 문자열 메모리 할당을 것입니다. 로 할당 된 문자열에 특정 스레드 할당 자가 해당 스레드 에서만 사용 되며, 할당자 스레드로부터 안전한 필요는 없습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 해당 스레드에서 문자열에 대 한 사용 하도록 자체 개인 스레드로부터 안전 하지 않은 힙 할당 하 고, 스레드 프로시저를 보여 줍니다.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]  
  
## <a name="comments"></a>설명  
 여러 스레드가 동일한 스레드에서 절차를 사용 하 여 실행 될 수 있지만 없기 때문에 각 스레드는 자체 힙 스레드 간에 경합이 없습니다. 또한 각 힙 스레드로부터 안전한 된다는 사실에 입각 스레드의 복사본이 하나만 실행 하는 경우에 많이 성능 향상을 제공 합니다. 동시 액세스를 방지 하기 위해 비용이 많이 드는 연동된 작업을 사용 하지 힙의 결과입니다.  
  
 더 복잡 한 스레드 프로시저에 대 한 스레드 로컬 저장소 (TLS) 슬롯에는 스레드의 문자열 관리자에 대 한 포인터를 저장 하는 것이 편리할 수입니다. 이렇게 하면 스레드 문자열 관리자에 액세스 하려면 스레드 프로시저에서 호출 된 다른 함수.  
  
## <a name="see-also"></a>참고 항목  
 [CStringT를 사용한 메모리 관리](../atl-mfc-shared/memory-management-with-cstringt.md)

