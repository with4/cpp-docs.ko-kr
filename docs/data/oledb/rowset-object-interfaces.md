---
title: "Rowset 개체 인터페이스 | Microsoft Docs"
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
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211fb5bbd0a950eff5f954d1c23b3dc993badb0d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="rowset-object-interfaces"></a>행 집합 개체 인터페이스
다음 표에서 행 집합 개체에 대 한 OLE DB에서 정의 된 필수 및 선택적 인터페이스를 보여 줍니다.  
  
|인터페이스|필수 여부|OLE DB 템플릿 구현한?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)|필수|예|  
|[IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|필수|예|  
|[IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)|필수|예|  
|[IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)|필수|예|  
|[IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|필수|예|  
|[IChapteredRowset](https://msdn.microsoft.com/en-us/library/ms718180.aspx)|Optional|아니요|  
|[IColumnsInfo2](https://msdn.microsoft.com/en-us/library/ms712953.aspx)|Optional|아니요|  
|[IColumnsRowset](https://msdn.microsoft.com/en-us/library/ms722657.aspx)|Optional|아니요|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|예 (ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/en-us/library/ms709832.aspx)|Optional|아니요|  
|[IGetRow](https://msdn.microsoft.com/en-us/library/ms718047.aspx)|Optional|아니요|  
|[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)|Optional|예|  
|[IRowsetChapterMember](https://msdn.microsoft.com/en-us/library/ms725430.aspx)|Optional|아니요|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/en-us/library/ms709700.aspx)|Optional|아니요|  
|[IRowsetFind](https://msdn.microsoft.com/en-us/library/ms724221.aspx)|Optional|아니요|  
|[IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx)|선택적 (필요한 경우 수준 0 공급자)|예|  
|[IRowsetIndex](https://msdn.microsoft.com/en-us/library/ms719604.aspx)|Optional|아니요|  
|[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)|Optional|예|  
|[IRowsetRefresh](https://msdn.microsoft.com/en-us/library/ms714892.aspx)|Optional|아니요|  
|[IRowsetScroll](https://msdn.microsoft.com/en-us/library/ms712984.aspx)|Optional|아니요|  
|[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)|Optional|예|  
|[IRowsetView](https://msdn.microsoft.com/en-us/library/ms709755.aspx)|Optional|아니요|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|예|  
|[IRowsetBookmark](https://msdn.microsoft.com/en-us/library/ms714246.aspx)|Optional|아니요|  
  
 마법사에서 생성 된 행 집합 개체에서 `IAccessor`, `IRowset`, 및 `IRowsetInfo` 상속을 통해. `IAccessorImpl` 모두 출력 열에 바인딩합니다. `IRowset` 인터페이스 인출 행 및 데이터를 처리 합니다. `IRowsetInfo` 행 집합 속성을 처리 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)