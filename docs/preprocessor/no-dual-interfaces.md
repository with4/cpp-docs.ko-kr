---
title: no_dual_interfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba20fcba43cc23dfce447d7e91955a43c28a6a31
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C + + 전용**  
  
 컴파일러가 이중 인터페이스 메서드에 대한 래퍼 함수를 생성하는 방법을 변경합니다.  
  
## <a name="syntax"></a>구문  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>설명  
 일반적으로 래퍼는 인터페이스의 가상 함수 테이블을 통해 메서드를 호출합니다. 와 `no_dual_interfaces`, 래퍼를 대신 호출 **idispatch:: Invoke** 메서드를 호출 합니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)