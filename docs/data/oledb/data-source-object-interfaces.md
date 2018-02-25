---
title: "데이터 소스 개체 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0a045657b80ddaf70792d1c7f617b0e1f7c0b4a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="data-source-object-interfaces"></a>데이터 소스 개체 인터페이스
다음 표에서 OLE DB 데이터 원본 개체에 대해 정의한 필수 및 선택적 인터페이스를 보여 줍니다.  
  
|인터페이스|필수 여부|OLE DB 템플릿 구현한?|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|필수|예|  
|`IDBInitialize`|필수|예|  
|`IDBProperties`|필수|예|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|필수|예|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|아니요|  
|`IDBDataSourceAdmin`|Optional|아니요|  
|`IDBInfo`|Optional|아니요|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|아니요|  
|`ISupportErrorInfo`|Optional|아니요|  
  
 데이터 원본 개체 구현 하는 `IDBProperties`, `IDBInitialize`, 및 `IDBCreateSession` 상속을 통해 인터페이스입니다. 하거나 이러한 구현 클래스 중 하나에서 상속 하지 하 여 추가 기능을 지원 하도록 선택할 수 있습니다. 지원 하려는 경우는 `IDBDataSourceAdmin` 인터페이스에서 상속 해야 합니다는 `IDBDataSourceAdminImpl` 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)