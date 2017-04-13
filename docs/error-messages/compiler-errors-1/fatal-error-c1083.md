---
title: "심각한 오류 C1083 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1083
dev_langs:
- C++
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: bbc5e1f78ca1ea15e65fdd76b7ecd2ea0e195b00
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1083"></a>심각한 오류 C1083
filetype 파일을 열 수 없습니다. 'file': message  
  
 컴파일러가 파일을 찾을 수 없는 경우 C1083 오류가 발생합니다. 컴파일러에서 이 오류가 발생하는 일반적인 원인은 다음과 같습니다.  
  
 **지정 된 파일 이름이 잘못 되었습니다.**  
  
 파일 이름이 잘못 입력될 수 있습니다. 예를 들면 다음과 같습니다.  
  
```cpp  
#include <algorithms.h>  
```  
  
 원하는 파일을 찾을 수 없습니다. C + + 표준 라이브러리 헤더 파일이 algorithms 라는.h 파일 확장명이 없는 있습니다. 이 파일은 `include` 지시문으로 찾을 수 없습니다. 이 문제를 해결하려면 올바른 파일 이름을 입력했는지 확인합니다.  
  
 특정 C 런타임 라이브러리 헤더는 표준 포함 디렉터리의 하위 디렉터리에 있습니다. 예를 들어 sys\types.h를 포함하려면 include 지시문에 sys 하위 디렉터리 이름을 포함해야 합니다.  
  
 `#include <sys\types.h>`  
  
 **파일이는 컴파일러 검색 경로에 포함 되지 않습니다.**  
  
 컴파일러가 `include` 또는 `import` 지시문으로 표시되는 검색 규칙을 사용하여 파일을 찾을 수 없습니다. 따옴표로 묶여 있는 헤더 파일 이름을 예로 들 수 있습니다.  
  
 `#include "myincludefile.h"`  
  
 소스 파일이 포함된 같은 디렉터리에서 파일을 찾은 후 빌드 환경에 의해 지정된 다른 위치를 확인하도록 컴파일러에 지시합니다. 따옴표에 절대 경로가 포함되어 있는 경우 컴파일러는 해당 위치에서만 파일을 찾습니다. 따옴표에 상대 경로가 포함되어 있는 경우 컴파일러는 소스 디렉터리에 관련된 디렉터리에서 파일을 찾습니다. 이름이 꺾쇠 괄호로 묶여 있는 경우  
  
 `#include <stdio.h>`  
  
 컴파일러가 빌드 환경에 의해 정의 된 검색 경로 따릅니다는 **/I** 컴파일러 옵션의 **/X** 컴파일러 옵션 및 **INCLUDE** 환경 변수입니다. 파일을 찾는 데 검색 순서에 대 한 특정 세부 정보를 포함 한 자세한 내용은 참조 하십시오. [#include 지시문 (C/c + +)](../../preprocessor/hash-include-directive-c-cpp.md) 및 [#import 지시문](../../preprocessor/hash-import-directive-cpp.md)합니다.  
  
 헤더 파일에 표시 되는 경우에 **솔루션 탐색기** 프로젝트의 일부로 파일을 찾을 수 컴파일러에 의해으로 참조 되는 `include` 또는 `import` 지시문 되 고 디렉터리 검색 경로에 있어야 합니다. 빌드 종류에 따라 다른 검색 경로가 사용될 수도 있습니다. **/X** include 파일 검색 경로에서 디렉터리를 제외할 수 컴파일러 옵션을 사용할 수 있습니다. 이렇게 하면 각 빌드에서 이름은 같지만 다른 디렉터리에 보관되는 다른 포함 파일을 사용할 수 있습니다. 이는 전처리기 명령을 통한 조건부 컴파일의 대체 방법입니다. 에 대 한 자세한 내용은 **/X** 컴파일러 옵션을 참조 [/X (표준 포함 경로 무시)](../../build/reference/x-ignore-standard-include-paths.md)합니다.  
  
 명령줄에서 컴파일러를 호출하는 경우 대체로 환경 변수를 사용하여 검색 경로를 지정합니다. 설명 하는 검색 경로 **INCLUDE** 환경 변수가 올바르게 설정 되지 않았습니다., C1083 오류가 발생 합니다. 환경 변수를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 빌드에서 환경 변수를 사용 하 여](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build)합니다.  
  
 이 문제를 해결하려면 컴파일러가 포함되거나 가져온 파일을 찾는 데 사용하는 경로를 수정합니다. 새 프로젝트는 기본 검색 경로를 사용합니다. 프로젝트에 대한 디렉터리를 추가하려면 경로를 수정해야 할 수도 있습니다. 명령줄에서 컴파일하 하는 경우 설정의 **INCLUDE** 환경 변수 또는 **/I** 컴파일러 옵션을 파일의 경로 지정 합니다. Visual Studio에서 include 디렉터리 경로 설정 하려면 프로젝트를 열고 **속성 페이지** 대화 상자에서 **구성 속성** 및 **VC + + 디렉터리**, 한 다음 편집는 **포함 디렉터리** 값입니다. Visual Studio에서 컴파일러에 의해 검색 된 사용자 및-프로젝트 디렉터리에 대 한 자세한 내용은 참조 [VC + + 디렉터리 속성 페이지](../../ide/vcpp-directories-property-page.md)합니다. 에 대 한 자세한 내용은 **/I** 컴파일러 옵션을 참조 [/I (추가 포함 디렉터리)](../../build/reference/i-additional-include-directories.md)합니다.  
  
 **잘못 된 버전의 파일 이름이 포함 됩니다.**  
  
 C1083 오류가 잘못된 버전의 파일이 포함되었음을 나타낼 수도 있습니다. 예를 들어 빌드에서 사용되지 않는 헤더 파일에 대한 `include` 지시문이 있는 잘못된 버전의 파일이 빌드에 포함되어 있을 수 있습니다. 헤더 파일을 찾을 수 없는 경우 컴파일러에서 C1083 오류가 발생합니다. 이 문제를 해결하려면 올바른 파일을 사용하고 헤더 파일 또는 디렉터리를 빌드에 추가하지 마십시오.  
  
 **미리 컴파일된 헤더가 미리 컴파일되지 않았음**  
  
 프로젝트가 미리 컴파일된 헤더를 사용하도록 구성되어 있는 경우 헤더 콘텐츠를 사용하는 파일이 컴파일될 수 있도록 관련 .PCH 파일을 만들어야 합니다. 예를 들어 새 MFC 프로젝트에 대한 프로젝트 디렉터리에 stdafx.cpp 파일이 자동으로 만들어집니다. 먼저 해당 파일을 컴파일하여 미리 컴파일된 헤더 파일을 만듭니다. 일반적인 빌드 프로세스 디자인에서는 이 작업이 자동으로 수행됩니다. 자세한 내용은 참조 [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)합니다.  
  
 **추가 원인**  
  
-   하지만 컴파일러 옵션의 관리 되는 코드를 사용 하는 파일 **/clr** 지정 되지 않았습니다. 자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.  
  
-   다른을 사용 하 여 파일을 컴파일하 **/analyze** 헤더를 미리 컴파일하는 데 사용 된 컴파일러 옵션 설정입니다. (프로젝트에 대 한 헤더는 미리 컴파일된 경우 모든 사용 해야 동일한 **/analyze** 설정 합니다.) 자세한 내용은 [/analyze(코드 분석)](../../build/reference/analyze-code-analysis.md)를 참조하세요.  
  
-   파일, 디렉터리 또는 디스크가 읽기 전용입니다.  
  
-   파일 또는 디렉터리에 대한 액세스 권한이 부여되지 않았습니다.  
  
-   파일 핸들이 충분하지 않습니다. 일부 응용 프로그램을 닫은 후 다시 컴파일하십시오. 이러한 경우는 일반적인 상황에서 거의 발생하지 않습니다. 하지만 실제 메모리가 제한된 컴퓨터에서 큰 프로젝트를 빌드하는 경우 발생할 수 있습니다.  
  
 다음 예제에서는 C1083 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C1083.cpp  
// compile with: /c  
#include "test.h"   // C1083 test.h does not exist  
#include "stdio.h"   // OK  
```  
  
 IDE 또는 명령줄에서 C/c + + 프로젝트를 빌드하는 방법에 대 한 정보 및 환경 변수를 설정 하는 방법에 대 한 정보에 대 한 참조 [C/c + + 프로그램 빌드](../../build/building-c-cpp-programs.md)합니다.
 
 ## <a name="see-also"></a>참고 항목
 [MSBuild 속성](/visualstudio/msbuild/msbuild-properties)
