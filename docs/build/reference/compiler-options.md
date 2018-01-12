---
title: "컴파일러 옵션 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c433abea04ff81c69fe1b73569ea7e043e6e81ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-options"></a>컴파일러 옵션
cl.exe는 Microsoft C 및 c + + 컴파일러 및 링커 제어 하는 도구입니다. cl.exe는 Microsoft Visual Studio를 지 원하는 운영 체제에만 실행할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 컴파일러는 파일 형식은 COFF (공용 개체) 개체 (.obj) 파일을 생성합니다. 링커는 실행 파일 (.exe) 파일 또는 동적 연결 라이브러리 (Dll)를 생성 합니다.  
  
 모든 컴파일러 옵션은 대/소문자 구분을 참고 합니다.  
  
 링크 하지 않고 컴파일하려면를 사용 하 여 [/c](../../build/reference/c-compile-without-linking.md)합니다.  
  
## <a name="finding-an-option"></a>찾기 옵션  
 특정 컴파일러 옵션을 보려면, 다음 목록 중 하나를 참조 합니다.  
  
-   [컴파일러 옵션 사전순 목록](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>옵션 지정  
 각 컴파일러 옵션에 대 한 알아봅니다 방법을 개발 환경에서 설정할 수 있습니다. 개발 환경 외부에서 옵션을 지정 하는 내용은 다음을 참조 하십시오.  
  
-   [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL 명령 파일](../../build/reference/cl-command-files.md)  
  
-   [CL 환경 변수](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>관련된 빌드 도구  
 사용 하 여 [NMAKE](../../build/nmake-reference.md) 출력 파일을 빌드합니다.  
  
 사용 하 여 [BSCMAKE](../../build/reference/bscmake-reference.md) 클래스 검색을 지원 하도록 합니다.  
  
 [링커 옵션](../../build/reference/linker-options.md) 프로그램 빌드 방법을 영향을 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일 속도 향상](../../build/reference/fast-compilation.md)   
 [CL에서의 링커 호출](../../build/reference/cl-invokes-the-linker.md)