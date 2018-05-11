---
title: no_registry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 416663592f4362c110637fb4d4b4b418d9776cde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="noregistry"></a>no_registry
`no_registry`는 `#import`를 사용하여 가져온 형식 라이브러리를 레지스트리에서 검색하지 않도록 컴파일러에 지시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>매개 변수  
 *filename*  
 형식 라이브러리입니다.  
  
## <a name="remarks"></a>설명  
 포함 디렉터리는 참조 된 형식 라이브러리를 찾을 수 없습니다, 형식 라이브러리를 레지스트리에서 하는 경우에 컴파일이 실패 합니다.  `no_registry` 다른 형식 라이브러리를 사용 하 여 암시적으로 가져온 전파 `auto_search`합니다.  
  
 컴파일러는 파일 이름으로 지정되고 `#import`에 직접 전달된 형식 라이브러리를 레지스트리에서 검색하지 않습니다.  
  
 `auto_search`가 지정된 경우 추가 `#import`는 초기 `no_registry`의 `#import` 설정을 사용하여 생성됩니다. 초기 `#import` 지시문이 `no_registry`인 경우 `auto_search`를 통해 생성된 `#import`도 `no_registry`입니다.  
  
 `no_registry` 레지스트리에서 파일의 이전 버전을 찾는 컴파일러의 위험 없이 교차 참조 된 형식 라이브러리를 가져올 경우 유용 합니다.  `no_registry` 형식 라이브러리 등록 되지 않은 경우에 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import 지시문](../preprocessor/hash-import-directive-cpp.md)