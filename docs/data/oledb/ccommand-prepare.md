---
title: 'Ccommand:: Prepare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CCommand.Prepare
- CCommand::Prepare
- Prepare
dev_langs:
- C++
helpviewer_keywords:
- Prepare method
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d029664508b6be71348aa3aa8d5801191f2aca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089339"
---
# <a name="ccommandprepare"></a>CCommand::Prepare
유효성을 검사 하 고 현재 명령을 최적화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT CCommandBase::Prepare(ULONG cExpectedRuns = 0) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 *cExpectedRuns*  
 [in] 명령을 실행 해야 하는 횟수입니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 OLE DB 메서드를 래핑합니다 [icommandprepare:: Prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)