---
title: "OLE DB 응용 프로그램의 리소스 풀링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 공급자, 리소스 풀링"
  - "OLE DB 서비스[OLE DB], 리소스 풀링"
  - "OLE DB, 리소스 풀링"
  - "리소스 풀링[OLE DB], 서비스"
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB 응용 프로그램의 리소스 풀링
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램에서 풀링을 사용하려면 **IDataInitialize**나 **IDBPromptInitialize**를 통해 데이터 소스를 확보하여 OLE DB 서비스가 호출되도록 해야 합니다.  공급자의 CLSID를 기준으로 `CoCreateInstance`를 직접 사용하여 공급자를 호출하면 OLE DB 서비스가 호출되지 않습니다.  
  
 OLE DB 서비스는 **IDataInitialize**나 **IDBPromptInitialize**에 대한 참조가 유지되는 동안이나 연결이 사용되는 동안에는 연결된 데이터 소스의 풀을 유지 관리합니다.  또한 풀은 COM\+ 1.0 Services나 IIS\(인터넷 정보 서비스\) 환경 내에서 자동으로 유지 관리됩니다.  응용 프로그램이 COM\+ 1.0 Services나 IIS 환경 외부에서 풀링을 이용할 경우에는 **IdataInitialize** 또는 **IDBPromptInitialize**에 대한 참조를 유지하거나 최소한 연결을 하나는 유지해야 합니다.  응용 프로그램이 마지막 연결을 해제할 경우 풀이 소멸되지 않도록 하려면 응용 프로그램을 사용하는 동안 참조를 유지하거나 연결을 끊지 마십시오.  
  
 OLE DB 서비스는 `Initialize`가 호출될 때 연결을 끌어 온 풀을 식별합니다.  풀에서 연결을 끌어 온 후에는 연결을 다른 풀로 이동할 수 없습니다.  따라서 `Initialize`를 호출하기 전에 공급자 특정 인터페이스에 `UnInitialize`나 `QueryInterface`를 호출하는 것과 같은 초기화 정보 변경 작업을 응용 프로그램에서 수행하지 않도록 하십시오.  또한 **DBPROMPT\_NOPROMPT**가 아닌 다른 프롬프트 값으로 설정된 연결은 풀링되지 않습니다.  그러나 프롬프트를 통해 설정된 연결에서 검색한 초기화 문자열을 사용하여 같은 데이터 소스에 풀링된 추가 연결을 설정할 수 있습니다.  
  
 일부 공급자는 세션마다 별도의 연결을 설정해야 합니다.  이러한 추가 연결이 있을 경우에는 분산 트랜잭션에 별도로 참여해야 합니다.  OLE DB 서비스는 데이터 소스마다 단일 세션을 캐시하고 다시 사용하지만, 응용 프로그램이 단일 데이터 소스에서 한 번에 여러 세션을 요청할 경우에는 공급자가 추가 연결을 설정하고 풀링되지 않은 추가 트랜잭션 참여를 수행하게 됩니다.  따라서 단일 데이터 소스에서 여러 세션을 만드는 것보다는 풀링된 환경에서 세션마다 별도의 데이터 소스를 만드는 것이 사실상 더 효율적입니다.  
  
 ADO는 자동으로 OLE DB 서비스를 사용하므로 ADO를 사용하여 연결을 설정하면 풀링과 참여가 자동으로 발생합니다.  
  
## 참고 항목  
 [OLE DB 리소스 풀링 및 서비스](../../data/oledb/ole-db-resource-pooling-and-services.md)