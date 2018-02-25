---
title: no_namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_namespace
dev_langs:
- C++
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6528ce33689dc05fa037bdd6bc110e5e6a0de9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="nonamespace"></a>no_namespace
**C + + 전용**  
  
 컴파일러가 생성하지 않은 네임스페이스 이름을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>설명  
 `#import` 헤더 파일의 형식 라이브러리 콘텐츠는 일반적으로 네임스페이스에 정의됩니다. 네임 스페이스 이름에 지정 된는 **라이브러리** 원본 IDL 파일을 설명 합니다. `no_namespace` 특성을 지정하면 컴파일러가 이 네임스페이스를 생성하지 않습니다.  
  
 다른 네임 스페이스 이름을 사용 하려는 경우 다음 사용 하 여는 [rename_namespace](../preprocessor/rename-namespace.md) 특성을 대신 합니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)