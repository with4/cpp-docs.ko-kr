---
title: malloc 맞춤 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d503d0dd891c651a405cb79bb5ce50996f46cff6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368667"
---
# <a name="malloc-alignment"></a>malloc 맞춤
[malloc](../c-runtime-library/reference/malloc.md) 적절 하 게 할당 된 메모리의 양에 맞게 기본 맞춤 하 고 있는 있는 모든 개체를 저장 하기에 대 한 정렬 되는 메모리를 반환 하도록 보장 됩니다. A *기본 맞춤* 은 맞춤 지정을 하지 않고 구현에서 지원 되는 최대 맞춤 보다 작은 맞춤 합니다. (이것은 맞춤에 대 한 필요한 Visual c + +에서는 `double`, 또는 8 바이트입니다. 64비트 플랫폼을 대상으로 하는 코드에서는 16바이트입니다. 예를 들어 4 바이트 할당을 지 원하는 모든 4 바이트 또는 더 작은 개체는 경계에 정렬 합니다.  
  
 Visual c + +에서는 있는 형식을 *맞춤 확장*, 라 하 고 있는 *과도 하 게 정렬* 형식입니다. 예를 들어 SSE 형식은 [__m128](../cpp/m128.md) 및 `__m256`, 및를 사용 하 여 선언 된 형식에 `__declspec(align( n ))` 여기서 `n` 8 보다 크면, 맞춤을 확장 한 합니다. 적합 한 확장 된 맞춤을 필요로 하는 개체에 대 한 경계에서 메모리 맞춤으로 보장 되지 않습니다 `malloc`합니다. 사용 하 여 과도 하 게 정렬 된 형식에 대 한 메모리를 할당 하려면 [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) 및 관련 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [스택 사용](../build/stack-usage.md)   
 [맞춤](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)