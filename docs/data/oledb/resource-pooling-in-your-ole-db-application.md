---
title: "OLE DB 응용 프로그램의 리소스 풀링 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9d094b3545978aa042ba5a6d308a09369b238e4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB 응용 프로그램의 리소스 풀링
응용 프로그램의 풀링 활용, OLE DB 서비스를 통해 데이터 소스를 확보 하 여 호출 되 고 있는지 확인 해야 **IDataInitialize** 또는 **IDBPromptInitialize**합니다. 직접 사용 하는 경우 `CoCreateInstance` 공급자의 CLSID에 따라 공급자를 호출 하려면 OLE DB 서비스가 호출 됩니다.  
  
 OLE DB 서비스에 연결 된 데이터 원본에 대 한 참조는의 풀 유지 관리 **IDataInitialize** 또는 **IDBPromptInitialize** 보유 또는 사용 중인 연결 되어 있는 동안 계속 합니다. 풀은 COM + 1.0 서비스 또는 인터넷 정보 서비스 (IIS) 환경 내에서 자동으로 유지 됩니다. 에 대 한 참조를 유지 해야 응용 프로그램이 COM + 1.0 서비스 또는 IIS 환경 외부에서 풀링를 활용 하는 경우 **IDataInitialize** 또는 **IDBPromptInitialize** 또는 적어도 하나에 보관 합니다. 연결입니다. 을 하는 풀 않습니다 가져올 소멸 되지 응용 프로그램에 대 한 마지막 연결 해제 될 때 확인 하기 위해 참조 하거나 응용 프로그램의 수명에 대 한 연결을 유지 합니다.  
  
 OLE DB 서비스를 연결 된 시간에 그려지는 풀을 식별 하는 `Initialize` 라고 합니다. 연결 풀에서 그려진 후 다른 풀으로 이동할 수 없습니다. 따라서 호출 등의 초기화 정보를 변경 하는 응용 프로그램에서 작업을 진행 하지 마십시오 `UnInitialize` 호출 또는 `QueryInterface` 호출 하기 전에 공급자별 인터페이스에 대 한 `Initialize`합니다. 또한 사용 하 여 연결한 프롬프트 값 이외의 다른 **DBPROMPT_NOPROMPT** 풀링 되기도 합니다. 그러나 프롬프트를 통해 설정 되는 연결에서 검색 된 초기화 문자열 동일한 데이터 소스에 추가 풀링된 연결을 설정 데 사용할 수 있습니다.  
  
 일부 공급자는 각 세션에 대 한 별도 연결을 확인 해야 합니다. 있는 경우 이러한 추가 연결이 분산 트랜잭션에 별도로 참여 해야 합니다. OLE DB 서비스를 캐시 하 고 데이터 원본당 하나의 세션을 다시 사용 하지만 응용 프로그램이 단일 데이터 소스에서 한 번에 한 개 이상의 세션을 요청할 경우 공급자 수 추가 연결을 설정 하 고 있는 추가 트랜잭션 참여를 수행 하 풀링되지 합니다. 단일 데이터 원본에서 여러 세션을 만드는 보다 풀링된 환경에서 각 세션에 대 한 별도 데이터 원본을 만들려면 실제로 더 효율적입니다.  
  
 마지막으로, ADO 자동으로 사용 하므로 OLE DB 서비스, ADO 연결을 사용할 수 있습니다 및 풀링 및 인 리스트 먼 트 자동으로 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)