---
title: OLE DB 소비자 및 공급자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 170f45a3581846dc588abf06aec170d66aa0d545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB 소비자 및 공급자
OLE DB 아키텍처의 소비자 및 공급자 모델을 사용 합니다. 소비자에서는 데이터에 대 한 요청 합니다. 공급자는 테이블 형식으로 데이터를 배치 하는 고객에 게 반환 하 여 이러한 요청에 응답 합니다. 공급자에서 소비자 수 있도록 하는 모든 호출을 구현 되어야 합니다.  
  
 기술적으로 정의 소비자는 모든 시스템 또는 응용 프로그램 코드 (OLE DB 구성 요소 하지 않을 수도 있음) OLE DB 인터페이스를 통해 데이터에 액세스 하는 합니다. 인터페이스는 공급자에 구현 됩니다. 따라서 공급자는 데이터에 대 한 액세스를 캡슐화 하 고 다른 개체 (즉, 소비자)를 노출 하는 OLE DB 인터페이스를 구현 하는 소프트웨어 구성 요소입니다.  
  
 역할의 관점에서 소비자; OLE DB 인터페이스에서 메서드를 호출 OLE DB 공급자는 필요한 OLE DB 인터페이스를 구현합니다.  
  
 OLE DB에서는 이러한 역할 항상 사용할 수 없습니다, n 계층 상황에서 때문에 용어 클라이언트와 서버를 사용 합니다. 소비자에 제공 하는 다른 구성 요소는 계층에 있는 구성 요소 수를 호출할 클라이언트 구성 요소에 게 혼동 합니다. 또한 공급자 때로는 처럼 작동 서버 보다 데이터베이스 드라이버.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 프로그래밍](../../data/oledb/ole-db-programming.md)   
 [OLE DB 프로그래밍 개요](../../data/oledb/ole-db-programming-overview.md)