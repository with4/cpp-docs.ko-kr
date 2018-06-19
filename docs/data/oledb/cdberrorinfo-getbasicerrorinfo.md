---
title: 'Cdberrorinfo:: Getbasicerrorinfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo::GetBasicErrorInfo
- ATL.CDBErrorInfo.GetBasicErrorInfo
- CDBErrorInfo.GetBasicErrorInfo
- ATL::CDBErrorInfo::GetBasicErrorInfo
- GetBasicErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetBasicErrorInfo method
ms.assetid: 263cec53-63f6-48fe-b46e-31d20251863e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4bef16b2c67c63b2c1f5014ce4da17618c602c94
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090314"
---
# <a name="cdberrorinfogetbasicerrorinfo"></a>CDBErrorInfo::GetBasicErrorInfo
호출 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) 반환 코드 및 공급자 특정 오류 번호와 같은 오류에 대 한 기본 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```
HRESULT GetBasicErrorInfo(ULONG ulRecordNum,   
  ERRORINFO* pErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="return-value"></a>반환 값  
 표준 `HRESULT`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)