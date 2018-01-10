---
title: "OLE DB 공급자 템플릿 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords:
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2a61e8156b39b9f0afec477f541920570d4af823
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB 공급자 템플릿에 대한 매크로
OLE DB 템플릿 공급자 매크로 다음 범주에서 기능을 제공합니다.  
  
### <a name="property-set-map-macros"></a>속성 집합 맵 매크로  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](../../data/oledb/begin-property-set.md)|속성 집합의 시작을 표시 합니다.|  
|[BEGIN_PROPERTY_SET_EX](../../data/oledb/begin-property-set-ex.md)|속성 집합의 시작을 표시 합니다.|  
|[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)|표시 된 속성의 시작 부분 집합 숨김 또는 공급자의 범위 외부에 정의 된 수 있습니다.|  
|[CHAIN_PROPERTY_SET](../../data/oledb/chain-property-set.md)|속성 그룹도 함께 연결 합니다.|  
|[END_PROPERTY_SET](../../data/oledb/end-property-set.md)|속성 집합의 끝을 표시 합니다.|  
|[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)|속성 집합 맵의 끝을 표시 합니다.|  
|[PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)|기본 값으로 설정 된 속성에서 특정 속성을 설정 합니다.|  
|[PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)|사용자가 제공 되는 값으로 설정 된 속성에서 특정 속성을 설정 합니다. 또한 플래그 및 옵션을 설정할 수 있습니다.|  
|[PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)|사용자가 제공 되는 값으로 설정 된 속성에서 특정 속성을 설정 합니다.|  
  
### <a name="column-map-macros"></a>열 맵 매크로  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)|공급자 열 지도 항목의 시작을 표시 합니다.|  
|[END_PROVIDER_COLUMN_MAP](../../data/oledb/end-provider-column-map.md)|공급자 열 지도 항목의 끝을 표시 합니다.|  
|[PROVIDER_COLUMN_ENTRY](../../data/oledb/provider-column-entry.md)|공급자에서 지 원하는 특정 열을 나타냅니다.|  
|[PROVIDER_COLUMN_ENTRY_GN](../../data/oledb/provider-column-entry-gn.md)|공급자에서 지 원하는 특정 열을 나타냅니다. 열의 크기, 데이터 형식, 정밀도, 배율 및 스키마 행 집합 GUID 지정할 수 있습니다.|  
|[PROVIDER_COLUMN_ENTRY_FIXED](../../data/oledb/provider-column-entry-fixed.md)|공급자에서 지 원하는 특정 열을 나타냅니다. 열 데이터 형식을 지정할 수 있습니다.|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)|공급자에서 지 원하는 특정 열을 나타냅니다. 열 크기를 지정할 수 있습니다.|  
|[PROVIDER_COLUMN_ENTRY_STR](../../data/oledb/provider-column-entry-str.md)|공급자에서 지 원하는 특정 열을 나타냅니다. 열 형식이 문자열이 가정 합니다.|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|공급자에서 지 원하는 특정 열을 나타냅니다. PROVIDER_COLUMN_ENTRY_LENGTH, 비슷하지만 크기 뿐만 아니라 열의 데이터 형식을 지정할 수 있습니다.|  
|[PROVIDER_COLUMN_ENTRY_WSTR](../../data/oledb/provider-column-entry-wstr.md)|공급자에서 지 원하는 특정 열을 나타냅니다. 열 형식이 유니코드 문자열 가정 합니다.|  
  
### <a name="schema-rowset-macros"></a>스키마 행 집합 매크로  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)|스키마 맵의 시작을 표시 합니다.|  
|[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)|GUID는 클래스와 연결합니다.|  
|[END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)|스키마 맵의 끝을 표시 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB 공급자 템플릿 참조](../../data/oledb/ole-db-provider-templates-reference.md)