---
title: OLE DB 리소스 풀링 및 서비스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2a04d0b990906f9f124edc9dbda71d65127e4ed
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338563"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB 리소스 풀링 및 서비스
OLE DB 풀링, 또는 모든 OLE DB 서비스를 사용 하 여 제대로 작동 하려면 공급자에 게 모든 개체의 집계를 지원 해야 합니다. 모든 OLE DB 1.5 또는 이상 공급자의 요구 사항입니다. 중요 한 서비스를 활용 하는 것입니다. 집계를 지원 하지 않는 공급자는 풀링 될 수 없습니다 하 고 추가 서비스가 제공 됩니다.  
  
 공급자는 풀링할 수 자유 스레드 모델을 지원 해야 합니다. 리소스 풀에는 공급자의 스레드 모델에 따라 결정 된 `DBPROP_THREADMODEL` 속성입니다.  
  
 공급자 데이터 원본이 초기화 상태인 동안 변경 될 수 있는 전역 연결 상태에 있는 경우 새 지원 해야 `DBPROP_RESETDATASOURCE` 속성입니다. 이 속성은 연결을 다시 사용 되는 공급자가 다음 사용 하기 전에 상태를 정리할 수 있도록 전에 호출 됩니다. 공급자 연결과 관련 된 일부 상태를 정리할 수 없습니다, 경우 반환할 수 `DBPROPSTATUS_NOTSETTABLE` 속성 및 연결을 다시 사용할 됩니다에 대 한 합니다.  
  
 원격 데이터베이스에 연결 및 연결 손실 될 수 있습니다를 지원 하는지 여부를 검색할 수 있는 공급자는 `DBPROP_CONNECTIONSTATUS` 속성입니다. 이 속성의 OLE DB 서비스 하지 않은 연결을 검색 하 고 풀에 반환 되지 않습니다 있는지 확인 하는 기능을 제공 합니다.  
  
 마지막으로, 자동 트랜잭션 인 리스트 먼 트 일반적으로 않으면 작동 하지 않습니다 발생 풀링 하는 동일한 수준에서 구현 됩니다. 자동 트랜잭션 인 리스트 먼 트를 자체 지원 공급자에 노출 하 여이 인 리스트 먼이 트를 비활성화를 지원 해야 합니다 `DBPROP_INIT_OLEDBSERVICES` 속성과 경우 인 리스트 먼 트를 사용 하지 않도록 설정는 `DBPROPVAL_OS_TXNENLISTMENT` 선택이 취소 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 공급자 기술](../../data/oledb/advanced-provider-techniques.md)