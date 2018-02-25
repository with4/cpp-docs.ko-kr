---
title: "CEnumeratorAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b3efe610e53d591f17d3ce227c6dbc09f0e23ce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor 클래스
사용 하는 [CEnumerator](../../data/oledb/cenumerator-class.md) 열거자 행 집합에서 데이터에 액세스할 수 있습니다.  
  
## <a name="syntax"></a>구문

```cpp
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>멤버  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|행이 있는 경우 열거자 열거자 부모 열거자 인지를 나타내는 변수입니다.|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|행이 데이터 원본 또는 열거자를 설명 하는지 여부를 나타내는 변수입니다.|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|데이터 원본 또는 열거자의 설명입니다.|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|데이터 원본 또는 열거자의 이름입니다.|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|에 전달 하는 문자열 [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) 데이터 원본 또는 열거자에 대 한 모니커를 가져오는 합니다.|  
  
## <a name="remarks"></a>설명  
 이 행 집합의 데이터 소스와 현재 열거자에서 표시 하는 열거자 구성 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)