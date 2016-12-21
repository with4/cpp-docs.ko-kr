---
title: "공급자 서비스 기본값 재정의 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB 서비스[OLE DB], 기본값 재정의"
  - "서비스 공급자[OLE DB]"
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 공급자 서비스 기본값 재정의
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OLEDB\_SERVICES**에 대한 공급자의 레지스트리 값은 데이터 소스 개체에서의 [DBPROP\_INIT\_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) 초기화 속성에 대한 기본값으로 반환됩니다.  
  
 레지스트리 항목만 있으면 공급자의 개체가 집계되므로, 사용자가 초기화 전에 **DBPROP\_INIT\_OLEDBSERVICES** 속성을 설정하여 사용하는 서비스에 대한 공급자의 기본 설정을 재정의할 수 있습니다.  특정 서비스를 사용하거나 사용하지 않으려면 일반적으로 **DBPROP\_INIT\_OLEDBSERVICES** 속성의 현재 값을 구한 다음 특정 속성을 사용하거나 사용하지 않도록 특정 속성에 대한 비트를 설정하거나 삭제하고 속성을 다시 설정합니다.  **DBPROP\_INIT\_OLEDBSERVICES**를 OLE DB에서 직접 설정하거나 ADO또는 **IDataInitialize::GetDatasource**로 전달된 연결 문자열에서 설정할 수 있습니다.  개별 서비스를 사용하거나 사용하지 않기 위해 설정하는 값은 다음과 같습니다.  
  
|사용하는 기본 서비스|DBPROP\_INIT\_OLEDBSERVICES 속성 값|연결 문자열의 값|  
|-----------------|--------------------------------------|---------------|  
|모든 서비스\(기본값\)|**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= \-1;"|  
|Pooling과 AutoEnlistment를 제외한 모든 서비스|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT**|"OLE DB Services \= \-4;"|  
|Client Cursor를 제외한 모든 서비스|**DBPROPVAL\_OS\_ENABLEALL** &<br /><br /> ~**DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-5;"|  
|Pooling, AutoEnlistment, Client Cursor를 제외한 모든 서비스|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-7;"|  
|서비스 사용 안 함|~**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= 0;"|  
  
 공급자에 대한 레지스트리 항목이 없으면 구성 요소 관리자가 공급자의 개체를 집계하지 않으므로 사용자가 명시적으로 요청하더라도 서비스가 호출되지 않습니다.  
  
## 참고 항목  
 [Resource Pooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [How Consumers Use Resource Pooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [How Providers Work Effectively with Resource Pooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [OLE DB 서비스 사용 및 사용 안 함](../../data/oledb/enabling-and-disabling-ole-db-services.md)