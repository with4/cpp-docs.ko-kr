---
title: "DEFINE_COMMAND_EX | Microsoft Docs"
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
  - "DEFINE_COMMAND_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND_EX 매크로"
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Specifies the command that will be used to create the rowset when using the [CCommand](../../data/oledb/ccommand-class.md) class.  Supports Unicode and ANSI applications.  
  
## 구문  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### 매개 변수  
 *x*  
 \[in\] The name of the user record \(command\) class.  
  
 `wszCommand`  
 \[in\] The command string that will be used to create the rowset when using [CCommand](../../data/oledb/ccommand-class.md).  
  
## 설명  
 The command string that you specify will be used as the default if you do not specify command text in the [CCommand::Open](../../data/oledb/ccommand-open.md) method.  
  
 This macro accepts Unicode strings, regardless of the application type.  This macro is preferred over [DEFINE\_COMMAND](../../data/oledb/define-command.md) because it supports Unicode as well as ANSI applications.  
  
## 예제  
 See [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)