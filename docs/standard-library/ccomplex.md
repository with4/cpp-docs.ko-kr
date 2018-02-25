---
title: "&lt;ccomplex&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb279929a460c43bb7ca564615fde494e3a0eb99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;
효율적으로 표준 C 라이브러리 헤더 \<complex.h>를 포함하고 `std` 네임스페이스에 연결된 이름을 추가하는 C++ 표준 라이브러리 헤더 [\<complex>](../standard-library/complex.md)를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
#include <ccomplex>  
  
```  
  
## <a name="remarks"></a>설명  
 이 헤더를 포함하는 경우 표준 C 라이브러리 헤더의 외부 링크를 사용하여 선언한 이름이 `std` 네임스페이스에도 선언됩니다.  
  
 [\<iostream>](../standard-library/iostream.md)에 선언된 `clog`와 잠재적으로 충돌할 수 있으므로 \<complex.h>에 선언된 이름 `clog`는 `std` 네임스페이스에 정의되어 있지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)



