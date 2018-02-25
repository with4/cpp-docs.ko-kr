---
title: "공급자 서비스 기본값 재정의 | Microsoft Docs"
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
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8788de8ad28dc3c746155f59dee3ba5bb763bcaa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="overriding-provider-service-defaults"></a>공급자 서비스 기본값 재정의
공급자의 레지스트리 값에 대 한 **OLEDB_SERVICES** 에 대 한 기본 값으로 반환 되는 [DBPROP_INIT_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) 데이터 원본 개체에서 초기화 속성입니다.  
  
 레지스트리 항목이 존재 공급자의 개체가 집계 되 고 사용자는 공급자의 기본 설정 하 여 사용된 하는 서비스에 대 한 설정을 재정의할 수는 **DBPROP_INIT_OLEDBSERVICES** 초기화 전에 속성입니다. 를 사용 하거나 특정 서비스를 사용 하지 않도록 설정 하려면 사용자는 일반적으로 현재의 값을 가져옵니다는 **DBPROP_INIT_OLEDBSERVICES** 속성을 설정 또는 특정 속성을 사용 하거나 사용 하지 않도록 설정에 대 한 비트가 지우고 속성을 다시 설정 합니다. **DBPROP_INIT_OLEDBSERVICES** OLE DB 또는 ADO에 전달 된 연결 문자열에서 직접 설정할 수 있습니다 또는 **idatainitialize:: Getdatasource**합니다. 설정/해제 개별 서비스의 해당 값은 다음 표에 나열 됩니다.  
  
|기본 서비스를 사용할 수|DBPROP_INIT_OLEDBSERVICES 속성 값|연결 문자열의 값|  
|------------------------------|------------------------------------------------|--------------------------------|  
|모든 서비스 (기본값)|**DBPROPVAL_OS_ENABLEALL**|"OLE DB 서비스 =-1;"|  
|풀링 제외 하 고 모두 및 AutoEnlistment|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~ DBPROPVAL_OS_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL_OS_TXNENLISTMENT**|"OLE DB 서비스-; 4 ="|  
|클라이언트 커서 제외한 모든 컴퓨터|**DBPROPVAL_OS_ENABLEALL** &<br /><br /> ~**DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB 서비스 =-5;"|  
|AutoEnlistment, 및 클라이언트 커서 풀링 차트를 제외한 모든|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~DBPROPVAL_OS_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB Services = -7;"|  
|서비스|~**DBPROPVAL_OS_ENABLEALL**|"OLE DB 서비스 = 0."|  
  
 공급자에 대 한 레지스트리 항목이 없는 경우 구성 요소 관리자는 공급자의 개체를 집계 하 고 사용자가 명시적으로 요청 서비스가 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [리소스 풀링](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [리소스 풀링 소비자를 사용 하는 방법](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [공급자는 효과적으로 리소스 풀링와 함께 작동 방식](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [OLE DB 서비스 사용 및 사용 안 함](../../data/oledb/enabling-and-disabling-ole-db-services.md)