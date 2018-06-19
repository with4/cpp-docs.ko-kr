---
title: 'Ccommand:: Getparameterinfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- GetParameterInfo method
ms.assetid: 9cd9277f-0161-4bd8-ad24-58e5e90b92a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 869675c079a392bb1e1e96656e66ef7742f526c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094285"
---
# <a name="ccommandgetparameterinfo"></a>CCommand::GetParameterInfo
명령의 매개 변수, 속성 이름 및 해당 종류의 목록을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,  
   DBPARAMINFO** ppParamInfo,  
   OLECHAR** ppNamesBuffer) throw ();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [icommandwithparameters:: Getparameterinfo](https://msdn.microsoft.com/en-us/library/ms714917.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)