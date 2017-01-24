---
title: "DEFINE_COMMAND | Microsoft Docs"
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
  - "DEFINE_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND 매크로"
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Specifies the command that will be used to create the rowset when using the [CCommand](../../data/oledb/ccommand-class.md) class.  Accepts only string types matching the specified application type \(ANSI or Unicode\).  
  
> [!NOTE]
>  It is recommended that you use [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) instead of `DEFINE_COMMAND`.  
  
## 구문  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### 매개 변수  
 *x*  
 \[in\] The name of the user record \(command\) class.  
  
 `szCommand`  
 \[in\] The command string that will be used to create the rowset when using [CCommand](../../data/oledb/ccommand-class.md).  
  
## 설명  
 The command string that you specify will be used as the default if you do not specify command text in the [CCommand::Open](../../data/oledb/ccommand-open.md) method.  
  
 This macro accepts ANSI strings if you build your application as ANSI, or Unicode strings if you build your application as Unicode.  It is recommended that you use [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) instead of `DEFINE_COMMAND`, because the former accepts Unicode strings, regardless of the ANSI or Unicode application type.  
  
## 예제  
 See [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)