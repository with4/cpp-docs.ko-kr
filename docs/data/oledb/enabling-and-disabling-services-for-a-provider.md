---
title: "공급자 서비스 사용 및 사용 안 함 | Microsoft Docs"
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
  - "OLE DB 서비스[OLE DB], 사용 및 사용 안 함"
  - "서비스 공급자[OLE DB]"
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 공급자 서비스 사용 및 사용 안 함
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본적으로 단일 공급자에 액세스하는 모든 응용 프로그램에 대해 개별 OLE DB 서비스를 사용하거나 사용하지 않을 수 있습니다.  공급자의 CLSID에 다음 표에서와 같이 서비스 사용 또는 사용하지 않음을 지정하는 `DWORD` 값을 지정하여 **OLEDB\_SERVICES** 레지스트리 항목을 추가하면 됩니다.  
  
|사용하는 기본 서비스|키워드 값|  
|-----------------|-----------|  
|모든 서비스\(기본값\)|0xffffffff|  
|Pooling과 AutoEnlistment를 제외한 모든 서비스|0xfffffffe|  
|Client Cursor를 제외한 모든 서비스|0xfffffffb|  
|Pooling, AutoEnlistment, Client Cursor를 제외한 모든 서비스|0xfffffff0|  
|서비스 사용 안 함|0x00000000|  
|집합체 없음, 모든 서비스 사용 안 함|\<missing key\>|  
  
## 참고 항목  
 [OLE DB 서비스 사용 및 사용 안 함](../../data/oledb/enabling-and-disabling-ole-db-services.md)