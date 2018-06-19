---
title: 내장 및 인라인 어셈블리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b8651bea0b1ee9f54ec0af704d92feef0722368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367981"
---
# <a name="intrinsics-and-inline-assembly"></a>내장 및 인라인 어셈블리
에 대 한 제약 조건 중 하나는 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 컴파일러는 인라인 어셈블러 지원 되지 않습니다. 이 따라서 함수를 사용 하는 컴파일러에서 지 원하는 내장 함수 또는 서브루틴으로 쓸 해야 합니다 C 또는 c + +에서 쓸 수 없습니다. 특정 함수 수 있으며 성능이 중요 한 나머지는 그렇지 않습니다. 성능에 민감한 함수는 내장 함수로 구현 되어야 합니다.  
  
 컴파일러에서 지 원하는 내장 함수에 설명 된 [컴파일러 내장](../intrinsics/compiler-intrinsics.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [x64 소프트웨어 규칙](../build/x64-software-conventions.md)