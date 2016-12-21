---
title: "CCommand::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CCommand.Open"
  - "ATL::CCommand::Open"
  - "CCommand.Open"
  - "CCommand::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Executes and optionally binds the command.  
  
## 구문  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### 매개 변수  
 `session`  
 \[in\] The session in which to execute the command.  
  
 `wszCommand`  
 \[in\] The command to execute, passed as a Unicode string.  Can be **NULL** when using `CAccessor`, in which case the command will be retrieved from the value passed to the [DEFINE\_COMMAND](../../data/oledb/define-command.md) macro.  See [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in the *OLE DB Programmer's Reference* for details.  
  
 `szCommand`  
 \[in\] Same as `wszCommand` except that this parameter takes an ANSI command string.  The fourth form of this method can take a NULL value.  See "Remarks" later in this topic for details.  
  
 *pPropSet*  
 \[in\] A pointer to an array of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures containing properties and values to be set.  See [Property Sets and Property Groups](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pRowsAffected`  
 \[in\/out\] A pointer to memory where the count of rows affected by a command is returned.  If *\*pRowsAffected* is **NULL**, no row count is returned.  Otherwise, **Open** sets \*`pRowsAffected` according to the following conditions:  
  
|상태|결과|  
|--------|--------|  
|The **cParamSets** element of `pParams` is greater than 1|\*`pRowsAffected` represents the total number of rows affected by all of the parameter sets specified in the execution.|  
|The number of affected rows is not available|\*`pRowsAffected` is set to –1.|  
|The command does not update, delete, or insert rows|\*`pRowsAffected` is undefined.|  
  
 `guidCommand`  
 \[in\] A GUID that specifies the syntax and general rules for the provider to use in parsing the command text.  See [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) and [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) in the *OLE DB Programmer's Reference* for details.  
  
 `bBind`  
 \[in\] Specifies whether to bind the command automatically after being executed.  The default is **true**, which causes the command to be bound automatically.  Setting `bBind` to **false** prevents the automatic binding of the command so that you can bind manually. \(Manual binding is of particular interest to OLAP users.\)  
  
 `ulPropSets`  
 \[in\] The number of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures passed in the *pPropSet* argument.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 The first three forms of **Open** take a session, create a command, and execute the command, binding any parameters as necessary.  
  
 The first form of **Open** takes a Unicode command string and has no default value.  
  
 The second form of **Open** takes an ANSI command string and no default value \(provided for backward compatibility with existing ANSI applications\).  
  
 The third form of **Open** allows the command string to be NULL, because of type `int` with a default value of NULL.  It is provided for calling `Open(session, NULL);` or `Open(session);` because NULL is of type `int`.  This version requires and asserts that the `int` parameter be NULL.  
  
 Use the fourth form of **Open** when you have already created a command and you want to perform a single [Prepare](../../data/oledb/ccommand-prepare.md) and multiple executions.  
  
> [!NOTE]
>  **Open** calls **Execute**, which in turn calls `GetNextResult`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)