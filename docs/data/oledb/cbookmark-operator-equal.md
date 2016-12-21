---
title: "CBookmark::operator = | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>::operator="
  - "CBookmark<0>.operator="
  - "ATL.CBookmark.operator="
  - "CBookmark::operator="
  - "ATL.CBookmark<0>.operator="
  - "ATL::CBookmark<0>::operator="
  - "CBookmark.operator="
  - "ATL::CBookmark::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= 연산자, OLE DB 템플릿"
  - "operator =, 책갈피"
  - "operator=, 책갈피"
ms.assetid: 23805af4-aedd-47ad-bef4-21d902463797
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBookmark::operator =
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Assigns a `CBookmark` object to another.  
  
## 구문  
  
```  
  
      CBookmark& operator =(   
   const CBookmark& bookmark    
) throw( );  
```  
  
## 설명  
 This operator is needed only in **CBookmark\<0\>**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBookmark 클래스](../../data/oledb/cbookmark-class.md)