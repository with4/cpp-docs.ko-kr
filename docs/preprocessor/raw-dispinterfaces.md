---
title: raw_dispinterfaces | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c20cc7cab6c85f203bc83523229f50749332f3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C + + 전용**  
  
 호출 하는 dispinterface 메서드 및 속성에 대 한 하위 수준의 래퍼 함수를 생성 하는 컴파일러가 **idispatch:: Invoke** 다음 다시 돌아와 `HRESULT` 오류 코드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>설명  
 이 특성이 지정되지 않은 경우 실패 시 C++ 예외를 throw하는 상위 수준 래퍼만 생성됩니다.  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [#import 특성](../preprocessor/hash-import-attributes-cpp.md)   
 [#import Directive](../preprocessor/hash-import-directive-cpp.md)