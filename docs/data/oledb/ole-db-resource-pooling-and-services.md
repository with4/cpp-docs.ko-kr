---
title: "OLE DB 리소스 풀링 및 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5d3d9ddba2039c1b4445bdb8d4ee77e9a68d9796
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB 리소스 풀링 및 서비스
OLE DB 서비스 또는 OLE DB 풀링을와 잘 작동 하려면 공급자는 모든 개체의 집계를 지원 해야 합니다. 이 작업은 모든 OLE DB 1.5 또는 이상 공급자의 필요 합니다. 것이 서비스를 활용 하기 위해 중요 합니다. 집계를 지원 하지 않는 공급자 풀링 될 수 없으므로 하 고 추가 서비스가 제공 됩니다.  
  
 공급자는 풀링할 수 있으려면 자유 스레드 모델을 지원 해야 합니다. 리소스 풀에 따라 공급자의 스레드 모델 확인는 **DBPROP_THREADMODEL** 속성입니다.  
  
 공급자 데이터 원본 초기화 된 상태인 동안 변경 될 수 있는 전역 연결 상태에 있는 경우 새 지원 해야 **DBPROP_RESETDATASOURCE** 속성입니다. 이 속성은 연결을 다시 사용 되 고 다음 사용 하기 전에 상태를 정리할 수 있는 기회가 공급자에 게 제공 하기 전에 호출 됩니다. 공급자 연결과 관련 된 일부 상태를 정리할 수, 하는 경우 반환할 수 있지만 **DBPROPSTATUS_NOTSETTABLE** 속성 및 연결을 다시 사용할 됩니다에 대 한 합니다.  
  
 원격 데이터베이스에 연결 하 고 연결 손실 될 수 있습니다 지원 하는지 여부를 검색할 수 있는 공급자는 **DBPROP_CONNECTIONSTATUS** 속성입니다. 이 속성 OLE DB 서비스 유효 하지 않은 연결을 검색 하 고 풀에 반환 되지 않습니다 있는지 확인 하는 기능을 제공 합니다.  
  
 마지막으로, 자동 트랜잭션 인 리스트 먼 트 일반적으로 않으면 작동 하지 않습니다는 풀링이 발생 동일한 수준에서 구현 됩니다. 자동 트랜잭션 인 리스트 먼 트를 자체 지원 공급자에 노출 하 여이 인 리스트 먼이 트를 비활성화 하면 지원 해야는 **DBPROP_INIT_OLEDBSERVICES** 속성 및 경우에 인 리스트 먼 트를 비활성화 하면는 **DBPROPVAL_OS_ TXNENLISTMENT** 선택 취소 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)