---
title: "CMyProviderRowset(MyProviderRS.H) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderrowset"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MyProviderRS.H의 CMyProviderRowset 클래스"
  - "OLE DB 공급자, 마법사에서 생성된 파일"
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderRowset(MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

마법사는 행 집합 개체에 대한 항목을 생성합니다.  여기서는 이 행 집합을 `CMyProviderRowset`이라고 합니다.  `CMyProviderRowset` 클래스는 행 집합 개체에 필요한 모든 인터페이스를 구현하는 `CRowsetImpl`이라는 OLE DB 공급자 클래스에서 상속됩니다.  다음 코드는 `CRowsetImpl`의 상속 체인을 보여 줍니다.  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 또한`CRowsetImpl`은 `IAccessor`와 `IColumnsInfo` 인터페이스를  테이블의 출력 필드에 사용합니다.  이 클래스는 두 행이 동일한지 소비자가 확인할 수 있도록 **IRowsetIdentity**도 구현합니다.  `IRowsetInfo` 인터페이스는 행 집합 개체에 대한 속성을 구현합니다.  **IConvertType** 인터페이스는 소비자가 요청한 데이터 형식과 공급자가 사용하는 데이터 형식 간의 차이를 공급자가 해결할 수 있도록 합니다.  
  
 `IRowset` 인터페이스는 실제로 데이터 검색을 처리합니다.  소비자는 먼저 `GetNextRows` 메서드를 호출하여 **HROW**라는 핸들을 행에 반환한 다음  이 **HROW**로 **IRowset::GetData**를 호출하여 요청받은 데이터를 검색합니다.  
  
 `CRowsetImpl`은 또한 몇 가지 템플릿 매개 변수를 사용합니다.  이러한 매개 변수를 사용하여 `CRowsetImpl` 클래스가 데이터를 처리하는 방법을 결정할 수 있습니다.  `ArrayType` 인수를 통해 행 데이터를 저장하는 데 사용되는 저장소 메커니즘을 알 수 있습니다.  **RowClass** 매개 변수는 **HROW**를 포함하는 클래스를 지정합니다.  
  
 **RowsetInterface** 매개 변수를 사용하여 `IRowsetLocate`나 `IRowsetScroll` 인터페이스를 사용할 수도 있습니다.  `IRowsetLocate`와 `IRowsetScroll` 인터페이스는 모두 `IRowset`에서 상속하므로,  OLE DB 공급자 템플릿은 이러한 인터페이스에 대한 특수한 처리 방법을 제공해야 합니다.  이러한 인터페이스를 사용하려면 이 매개 변수를 사용해야 합니다.  
  
## 참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)