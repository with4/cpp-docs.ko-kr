---
title: PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY_VALUE
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY_VALUE macro
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c93b2d010feb6be0160ac3253890ad7ffaa168a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="propertyinfoentryvalue"></a>PROPERTY_INFO_ENTRY_VALUE
속성 집합의 특정 속성을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### <a name="parameters"></a>매개 변수  
 *dwPropID*  
 [in] 속성 집합 GUID와 함께 사용하여 속성을 식별할 수 있는 [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 값입니다.  
  
 *값*  
 [in] `DWORD`형식의 속성 값입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로 지정할 수 있습니다 직접 형식의 속성 값 `DWORD`합니다. ATLDB에 정의 된 기본값으로 값을 속성을 설정 합니다. H, 사용 하 여 [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)합니다. 값, 플래그 및 속성에 대 한 옵션을 설정 하려면 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)합니다.  
  
## <a name="example"></a>예  
 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldb.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)