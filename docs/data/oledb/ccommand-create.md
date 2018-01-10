---
title: 'Ccommand:: Create | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs: C++
helpviewer_keywords: Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bbd236c2ec7ae6857ede1ac64f738ca8600774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreate"></a>CCommand::Create
호출 [ccommand:: Createcommand](../../data/oledb/ccommand-createcommand.md) 지정된 된 세션에 대 한 명령을 만들려면 다음 호출 [icommandtext:: Setcommandtext](https://msdn.microsoft.com/en-us/library/ms709825.aspx) 명령 텍스트를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `session`  
 [in] 명령을 만드는 세션입니다.  
  
 `wszCommand`  
 [in] 명령 문자열의 유니코드 텍스트에 대 한 포인터입니다.  
  
 `szCommand`  
 [in] 명령 문자열의 ANSI 텍스트에 대 한 포인터입니다.  
  
 `guidCommand`  
 [in] 명령 텍스트를 구문 분석의 구문 및 사용 하도록 공급자에 대 한 일반 규칙을 지정 하는 GUID입니다. 언어에 대 한 참조 [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 형태 **만들기** 유니코드 명령 문자열을 사용 합니다. 두 번째 형식의 **만들기** (기존 ANSI 응용 프로그램과 함께 이전 버전과 호환성을 위해 제공) 하는 ANSI 명령 문자열을 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)