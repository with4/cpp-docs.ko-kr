---
title: "BEGIN_PROPSET_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_PROPSET_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPSET_MAP 매크로"
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BEGIN_PROPSET_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the beginning of the property set map entries.  
  
## 구문  
  
```  
  
BEGIN_PROPSET_MAP(  
Class   
)  
  
```  
  
#### 매개 변수  
 *클래스*  
 \[in\] The class in which this property set is specified.  A property set can be specified in the following OLE DB objects:  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="75bbb794f21139fcd243c18fff6050d2" class\="tgtSentence"\>Data Source Objects\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="e423b0fba10fc83bd76e01e3eee2fd69" class\="tgtSentence"\>Session Objects\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="5f6bc08c46cee6f21bfcdd08aff6e8aa" class\="tgtSentence"\>명령\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## 예제  
 Here is a sample property set map:  
  
 [!CODE [NVC_OLEDB_Provider#3](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#3)]  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)