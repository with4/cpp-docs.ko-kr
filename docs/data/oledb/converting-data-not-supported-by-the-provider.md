---
title: 공급자가 지원 하지 않는 데이터 변환 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d0be19345ff6c425cfbc020f2096ca82680586d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="converting-data-not-supported-by-the-provider"></a>공급자가 지원하지 않는 데이터 변환
OLE DB 공급자 템플릿 코드에 대 한 소비자는 공급자에서 지원 되지 않는 데이터 형식을 요청 하면 `IRowsetImpl::GetData` Msdadc.dll 데이터 형식을 변환을 호출 합니다.  
  
 같은 인터페이스를 구현 하는 경우 `IRowsetChange` 데이터 변환이 필요한, 변환을 수행 하려면 Msdaenum.dll 호출할 수 있습니다. 사용 하 여 `GetData`, 예를 들어 Atldb.h에 정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿을 사용하여 작업](../../data/oledb/working-with-ole-db-provider-templates.md)