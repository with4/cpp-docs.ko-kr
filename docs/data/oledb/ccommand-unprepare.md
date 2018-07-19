---
title: 'Ccommand:: Unprepare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
dev_langs:
- C++
helpviewer_keywords:
- Unprepare method
ms.assetid: 4fe59988-fe51-4c7c-a156-72b68e3d642b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab5fdd595e646e181aa3815d6385595f3fee21a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094360"
---
# <a name="ccommandunprepare"></a>CCommand::Unprepare
현재 명령 실행 계획을 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CCommandBase::Unprepare() throw();  
  
```  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 OLE DB 메서드를 래핑합니다 [icommandprepare:: Unprepare](https://msdn.microsoft.com/en-us/library/ms719635.aspx)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)