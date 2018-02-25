---
title: "CManualAccessor 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecb9f31c862f62ddc2422f201aa824a959e961a0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="cmanualaccessor-class"></a>CManualAccessor 클래스
고급 사용 하기 위한 접근자 유형을 나타냅니다.  
  
## <a name="syntax"></a>구문

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|출력 열에 바인딩 항목을 추가합니다.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|매개 변수 접근자를 매개 변수 항목을 추가합니다.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Bind 구조 열에 대 한 메모리를 할당 하 고 열 데이터 멤버를 초기화 합니다.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Bind 구조는 매개 변수에 대 한 메모리를 할당 하 고 매개 변수 데이터 멤버를 초기화 합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 `CManualAccessor`, 및 런타임 함수 호출에 의해 열 바인딩 출력 매개 변수를 지정할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)