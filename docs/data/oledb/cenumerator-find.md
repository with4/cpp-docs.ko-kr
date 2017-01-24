---
title: "CEnumerator::Find | Microsoft Docs"
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
  - "CEnumerator::Find"
  - "ATL::CEnumerator::Find"
  - "ATL.CEnumerator.Find"
  - "CEnumerator.Find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Find 메서드"
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumerator::Find
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Looks for a specified name among available providers.  
  
## 구문  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
```  
  
#### 매개 변수  
 *szSearchName*  
 \[in\] The name to search for.  
  
## 반환 값  
 **true** if the name was found.  그렇지 않으면 **false**입니다.  
  
## 설명  
 This name maps to the **SOURCES\_NAME** member of the [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) interface.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CEnumerator 클래스](../../data/oledb/cenumerator-class.md)