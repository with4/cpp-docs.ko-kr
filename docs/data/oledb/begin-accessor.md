---
title: BEGIN_ACCESSOR | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_ACCESSOR
dev_langs: C++
helpviewer_keywords:
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
ms.assetid: 59d0ff3e-7cfd-4ce8-9a1c-d664c0892a52
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 74d8d2197553f9fd2b1f5452236b343424d29148
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="beginaccessor"></a>BEGIN_ACCESSOR
접근자 항목의 시작을 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
BEGIN_ACCESSOR(  
num  
,   
bAuto  
 )  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 *num*  
 [in] 이 접근자 맵에 있는 접근자에 대 한 0 오프셋 수입니다.  
  
 *한*  
 [in] 이 접근자 자동 접근자 또는 수동 접근자 인지 여부를 지정 합니다. 경우 **true**, 접근자 이면 자동; **false**, 접근자는 수동입니다. 자동 접근자 이동 작업에 데이터를 인출 되 의미 합니다.  
  
## <a name="remarks"></a>설명  
 행 집합에서 여러 접근자가 있는 경우 지정 해야 `BEGIN_ACCESSOR_MAP` 사용 하는 `BEGIN_ACCESSOR` 각 접근자에 대 한 매크로입니다. `BEGIN_ACCESSOR` 매크로는 `END_ACCESSOR` 매크로로 완료됩니다. `BEGIN_ACCESSOR_MAP` 매크로로 완료 됩니다는 `END_ACCESSOR_MAP` 매크로입니다.  
  
## <a name="example"></a>예제  
 참조 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atldbcli.h  
  
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역 함수에 대 한 OLE DB 소비자 템플릿](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)