---
title: CMyProviderRowset (MyProviderRS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8922e1643dc5a33721424f2a5d83c7f66e0f58a7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset(MyProviderRS.H)
행 집합 개체에 대 한 항목이 생성 됩니다. 여기서는 이 행 집합을 `CMyProviderRowset`이라고 합니다. `CMyProviderRowset` 클래스 라고 하는 OLE DB provider 클래스에서 상속 `CRowsetImpl`, 행 집합 개체에 대 한 모든 필요한 인터페이스를 구현 하는 합니다. 다음 코드에 대 한 상속 체인을 보여 줍니다. `CRowsetImpl`:  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
 `CRowsetImpl` 또한 사용 하 여는 `IAccessor` 및 `IColumnsInfo` 인터페이스입니다. 이러한 인터페이스를 사용 하 여 테이블의 출력 필드에 대 한 합니다. 클래스에 대 한 구현을 제공 **IRowsetIdentity**를 허용 하는 소비자 두 개의 행이 동일한 지 여부를 결정 합니다. `IRowsetInfo` 행 집합 개체에 대 한 속성을 구현 하는 인터페이스입니다. **IConvertType** 인터페이스를 사용 하면 공급자는 소비자가 요청한 데이터 형식 및 공급자에서 사용 되는 간의 차이를 해결 합니다.  
  
 `IRowset` 인터페이스는 실제로 데이터 검색을 처리 합니다. 라는 메서드를 먼저 호출 하는 소비자 `GetNextRows` 라고 하는 행에 대 한 핸들을 반환 하는 **HROW**합니다. 호출 합니다 **irowset:: Getdata** 와 **HROW** 요청 된 데이터를 검색 합니다.  
  
 `CRowsetImpl` 또한 여러 개의 템플릿 매개 변수를 사용합니다. 이러한 매개 변수를 사용 하면 확인할 수는 어떻게 `CRowsetImpl` 클래스가 데이터를 처리 합니다. `ArrayType` 인수를 사용 하면 저장소 메커니즘은 행 데이터를 저장 하는 데 사용은 확인할 수 있습니다. **RowClass** 매개 변수 지정 어떤 클래스를 포함 한 **HROW**합니다.  
  
 **RowsetInterface** 매개 변수를 사용할 수도 있습니다는 `IRowsetLocate` 또는 `IRowsetScroll` 인터페이스입니다. `IRowsetLocate` 및 `IRowsetScroll` 인터페이스에서 상속 하는 둘 다 `IRowset`합니다. 따라서 OLE DB 공급자 템플릿 이러한 인터페이스에 대 한 특수 처리를 제공 해야 합니다. 이러한 인터페이스 중 하나를 사용 하려는 경우이 매개 변수를 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공급자 마법사가 생성하는 파일](../../data/oledb/provider-wizard-generated-files.md)