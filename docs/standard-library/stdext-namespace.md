---
title: "stdext 네임스페이스 | Microsoft Docs"
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdext
dev_langs: C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59da07c0cea58e9fc4b544b9f3bad937b2951f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stdext-namespace"></a>stdext 네임스페이스

멤버는 [ \<hash_map >](../standard-library/hash-map.md) 및 [ \<hash_set >](../standard-library/hash-set.md) 헤더 파일은 현재 ISO c + + 표준의 일부가 되지 않습니다. 따라서 C++ 표준을 계속 준수하기 위해 이러한 형식 및 멤버를 `std` 네임스페이스에서 `stdext`네임스페이스로 이동했습니다.

로 컴파일할 때 [/Ze](../build/reference/za-ze-disable-language-extensions.md), 기본값인, 컴파일러에서 경고의 사용에 관한 `std` 의 멤버에 대 한는 \<hash_map > 및 \<hash_set > 헤더 파일입니다. 이 경고를 사용하지 않도록 설정하려면 [경고](../preprocessor/warning.md) pragma를 사용합니다.

컴파일러의 사용에 대 한 오류를 생성 하려면 `std` 의 멤버에 대 한는 \<hash_map > 및 \<hash_set > 헤더 파일을 **/Ze**, 하기 전에 다음 지시문을 추가 `#include` 모든 c + + 표준 라이브러리 헤더 파일입니다.

```cpp  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  

로 컴파일할 때 **/Za**, 컴파일러에 오류가 발생 합니다.  

## <a name="see-also"></a>참고 항목

[C++ 표준 라이브러리 개요](../standard-library/cpp-standard-library-overview.md)

