---
title: "BEGIN_PROVIDER_COLUMN_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_PROVIDER_COLUMN_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROVIDER_COLUMN_MAP 매크로"
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BEGIN_PROVIDER_COLUMN_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of the provider column map entries.  
  
## 구문  
  
```  
  
BEGIN_PROVIDER_COLUMN_MAP(  
theClass   
)  
  
```  
  
#### 매개 변수  
 `theClass`  
 \[in\] The name of the class this map belongs to.  
  
## 예제  
 Here is a sample provider column map:  
  
 [!CODE [NVC_OLEDB_Provider#4](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#4)]  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)