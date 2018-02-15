---
title: PROPERTY_INFO_ENTRY_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROPERTY_INFO_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3af47bb5cae4a008d8df9ca26ff1f671c25c0398
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
속성 집합의 특정 속성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *dwPropID*  
 [in] 속성 집합 GUID와 함께 사용하여 속성을 식별할 수 있는 [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 값입니다.  
  
 *vt*  
 [in] 이 속성 항목의 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) 입니다.  
  
 `dwFlags`  
 [in] 이 속성 항목을 설명하는 [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) 값입니다.  
  
 *값*  
 [in] `DWORD`형식의 속성 값입니다.  
  
 `options`  
 **DBPROPOPTIONS_REQUIRED** 또는 **DBPROPOPTIONS_SETIFCHEAP**입니다. 일반적으로 공급자는 `options` 를 설정할 필요가 없습니다. 소비자가 설정합니다.  
  
## <a name="remarks"></a>설명  
 이 매크로를 사용하면 `DWORD` 형식의 속성 값뿐만 아니라 옵션 및 플래그를 직접 지정할 수 있습니다. 속성을 ATLDB.H에 정의된 기본값으로 설정하려면 [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)를 사용합니다. 옵션 또는 플래그를 설정하지 않고 선택한 값으로 속성을 설정하려면 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)를 사용합니다.  
  
## <a name="example"></a>예  
 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)