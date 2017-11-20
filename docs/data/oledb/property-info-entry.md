---
title: PROPERTY_INFO_ENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY macro
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a5db7ac8d5420f8daf5e55d2027aee90f1b682e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="propertyinfoentry"></a>PROPERTY_INFO_ENTRY
속성 집합의 특정 속성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *dwPropID*  
 [in] 속성 집합 GUID와 함께 사용하여 속성을 식별할 수 있는 [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 값입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로는 `DWORD` 형식의 속성 값을 ATLDB.H에 정의된 기본값으로 설정합니다. 속성을 선택한 값으로 설정하려면 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)를 사용합니다. 속성에 대한 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 및 [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) 를 동시에 설정하려면 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)를 사용합니다.  
  
## <a name="example"></a>예제  
 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)