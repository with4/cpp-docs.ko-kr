---
title: "CEnumeratorAccessor::m_szParseName | Microsoft Docs"
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
  - "CEnumeratorAccessor::m_szParseName"
  - "ATL::CEnumeratorAccessor::m_szParseName"
  - "m_szParseName"
  - "CEnumeratorAccessor.m_szParseName"
  - "ATL.CEnumeratorAccessor.m_szParseName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_szParseName"
ms.assetid: 32e826b6-0890-4db4-aa92-fc1ea3f528b2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumeratorAccessor::m_szParseName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

String to pass to [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) to obtain a moniker for the data source or enumerator.  
  
## 구문  
  
```  
  
WCHAR m_szParseName[129];  
  
```  
  
## 설명  
 See [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx) in the *OLE DB Programmer's Reference* for more information.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CEnumeratorAccessor 클래스](../../data/oledb/cenumeratoraccessor-class.md)