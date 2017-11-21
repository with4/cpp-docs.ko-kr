---
title: 'Irowsetnotifycp:: Fire_onrowsetchange | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs: C++
helpviewer_keywords: Fire_OnRowsetChange method
ms.assetid: 412a9ec2-5041-4c56-acda-dc8f8e9b35f3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a59f8e13a371472e8355f9fd6903ada04c09d6c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifycpfireonrowsetchange"></a>IRowsetNotifyCP::Fire_OnRowsetChange
브로드캐스트하는 [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) 연결 지점에 대해 모든 수신기에 이벤트 **IID_IRowsetNotify** 전체 행 집합에 영향을 미치는 변경의 사용자에 게 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      HRESULT Fire_OnRowsetChange(  
   IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 참조 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) 에 *OLE DB Programmer's Reference*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [IRowsetNotifyCP 클래스](../../data/oledb/irowsetnotifycp-class.md)