---
title: "컴파일러 옵션 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbbc7111ceae2353e8bc9820ead319556ce0016b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-compiler-options"></a>컴파일러 옵션 설정
C 및 C++ 컴파일러 옵션은 통합 개발 환경이나 명령줄에서 설정할 수 있습니다.  
  
## <a name="in-the-development-environment"></a>개발 환경에서 설정  
 각 프로젝트에 대 한 컴파일러 옵션을 설정할 수는 **속성 페이지** 대화 상자. 왼쪽된 창에서 선택 **구성 속성**, **C/c + +** 컴파일러 옵션 범주를 선택 합니다. 각 컴파일러 옵션에 대한 항목에서는 설정하는 방법과 개발 환경의 어느 부분에 있는지 설명합니다. 참조 [컴파일러 옵션](../../build/reference/compiler-options.md) 전체 목록은 합니다.  
  
## <a name="outside-the-development-environment"></a>개발 환경 이외에서 설정  
 컴파일러(CL.exe) 옵션을 설정할 수 있습니다.  
  
-   [명령줄에서](../../build/reference/compiler-command-line-syntax.md)  
  
-   [명령 파일](../../build/reference/cl-command-files.md)  
  
-   [CL 환경 변수](../../build/reference/cl-environment-variables.md)  
  
 CL 환경 변수에서 지정한 옵션은 CL을 실행할 때마다 사용됩니다. CL 환경 변수나 명령줄에서 명령 파일의 이름을 지정하면 명령줄에서 지정한 옵션이 사용됩니다. 명령줄이나 CL 환경 변수와는 달리 명령 파일을 사용하면 여러 줄로 구성된 옵션과 파일 이름을 사용할 수 있습니다.  
  
 컴파일러 옵션은 "왼쪽에서 오른쪽"으로 처리됩니다. 서로 충돌되는 경우 맨 오른쪽에 있는 옵션이 사용됩니다. CL 환경 변수는 명령줄 이전에 처리되므로 CL과 명령줄이 충돌되는 경우 명령줄의 내용이 사용됩니다.  
  
## <a name="additional-compiler-topics"></a>추가 컴파일러 항목  
  
-   [컴파일 속도 향상](../../build/reference/fast-compilation.md)  
  
-   [CL에서의 링커 호출](../../build/reference/cl-invokes-the-linker.md)  
  
## <a name="see-also"></a>참고 항목  
 [C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)