---
title: 릴리스 빌드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ae18c5e2dcdb735880509fd158dac4ccaa1462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="release-builds"></a>릴리스 빌드
릴리스 빌드 최적화를 사용 합니다. 최적화를 사용 하 여 릴리스 빌드를 만들 때 컴파일러가 기호 디버깅 정보를 생성 하지 않습니다. ASSERT와 추적에 대 한 코드가 생성 되지 않으면 사실 외 기호 디버깅 정보 없으면 호출, 실행 파일의 크기 감소를 더 빠르게 수 없으므로 있다는 것을 의미 합니다.  
  
 이 섹션에서는 시기 및 이유는 변경 하려는 디버그 빌드에서 릴리스 빌드에 대 한 정보를 제공 합니다. 릴리스 빌드를 디버그에서 변경할 때 발생할 수 문제 중 일부에 설명 합니다.  
  
-   [릴리스 빌드 만들기](../../build/reference/how-to-create-a-release-build.md)  
  
-   [릴리스 빌드를 만들 때의 일반적인 문제](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)  
  
    -   [ASSERT 문 검사](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [디버그 빌드 검사를 사용 하 여 메모리 덮어쓰기](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)  
  
    -   [릴리스 빌드 디버깅](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [메모리 덮어쓰기 확인](../../build/reference/checking-for-memory-overwrites.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 c + + 프로젝트 빌드](../../ide/building-cpp-projects-in-visual-studio.md)   
 [C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)