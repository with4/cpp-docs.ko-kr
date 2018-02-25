---
title: rename_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="renamenamespace"></a>네임스페이스 이름 변경
**C + + 전용**  
  
 형식 라이브러리의 콘텐츠가 들어있는 네임스페이스의 이름을 바꿉니다.  
  
## <a name="syntax"></a>구문  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>매개 변수  
 `NewName`  
 네임스페이스의 새 이름입니다.  
  
## <a name="remarks"></a>설명  
 단일 인수를 사용 하기 *NewName*, 네임 스페이스에 대 한 새 이름을 지정 합니다.  
  
 네임 스페이스를 제거 하려면 사용 하 여는 [no_namespace](../preprocessor/no-namespace.md) 특성을 대신 합니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)