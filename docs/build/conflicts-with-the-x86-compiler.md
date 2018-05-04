---
title: 충돌 x86 컴파일러 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cd72de4922c297b4a230e0dc0fb606b56a2a473
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="conflicts-with-the-x86-compiler"></a>x86 컴파일러와 충돌
데이터 형식은 4 바이트 정렬 되지 않은 자동으로 스택에 x86를 사용 하는 경우 보다 더 큰 응용 프로그램을 컴파일하려면 컴파일러입니다. 때문에 컴파일러는 예를 들어 64 비트 정수 4 바이트 보다 큰 4 바이트 정렬 된 스택이 8 바이트 주소를 자동으로 정렬할 수 없습니다 x86 아키텍처입니다.  
  
 정렬 되지 않은 데이터로 작업은 두 개의 영향을 줍니다.  
  
-   정렬 된 위치에 액세스 하는 것 보다 정렬 되지 않은 위치에 액세스 하는 데 더 많은 시간이 걸릴 수 있습니다.  
  
-   연동된 작업에 정렬 되지 않은 위치를 사용할 수 없습니다.  
  
 더 엄격한 맞춤이 필요 하면 사용 `__declspec(align(N)) on your variable declarations`합니다. 이 동적으로 정렬 사양에 맞게 스택 컴파일러가 합니다. 그러나 런타임 시 스택의 동적으로 조정 응용 프로그램의 실행 속도가 느려지게 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)