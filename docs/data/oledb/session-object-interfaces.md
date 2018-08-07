---
title: 세션 개체 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 01d08fb35a1e954aad07153f63ad3ed34282570d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337848"
---
# <a name="session-object-interfaces"></a>세션 개체 인터페이스
다음 표에서 세션 개체에 대 한 OLE DB에서 정의 된 필수 및 선택적 인터페이스를 보여 줍니다.  
  
|인터페이스|필수 여부|OLE DB 템플릿에서 구현 되었습니까?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx)|필수|예|  
|[IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx)|필수|예|  
|[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)|필수|예|  
|[IAlterIndex](https://msdn.microsoft.com/library/ms714943.aspx)|Optional|아니요|  
|[IAlterTable](https://msdn.microsoft.com/library/ms719764.aspx)|Optional|아니요|  
|[IBindResource](https://msdn.microsoft.com/library/ms714936.aspx)|Optional|아니요|  
|[ICreateRow](https://msdn.microsoft.com/library/ms716832.aspx)|Optional|아니요|  
|[IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx)|Optional|예|  
|[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)|Optional|예|  
|[IIndexDefinition](https://msdn.microsoft.com/library/ms711593.aspx)|Optional|아니요|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|예|  
|[ITableCreation](https://msdn.microsoft.com/library/ms713639.aspx)|Optional|아니요|  
|[ITableDefinition](https://msdn.microsoft.com/library/ms714277.aspx)|Optional|아니요|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/library/ms720947.aspx)|Optional|아니요|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|Optional|아니요|  
|[ITransactionJoin](https://msdn.microsoft.com/library/ms718071.aspx)|Optional|아니요|  
|[ITransactionLocal](https://msdn.microsoft.com/library/ms714893.aspx)|Optional|아니요|  
|[ITransactionObject](https://msdn.microsoft.com/library/ms713659.aspx)|Optional|아니요|  
  
 세션 개체는 행 집합 개체를 만듭니다. 공급자 명령에서는 하는 경우 세션도 명령 개체를 만듭니다 (`CCommand`를 구현 하는 OLE DB `TCommand`). 명령 개체를 구현 하는 `ICommand` 사용 하 여 인터페이스를 `ICommand::Execute` 다음 그림에 표시 된 대로 행 집합에서 명령을 실행 하는 방법입니다.  
  
 ![공급자 개념적 다이어그램](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)