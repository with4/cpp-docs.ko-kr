---
title: "링커 도구 오류 LNK2038 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2038"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2038"
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# 링커 도구 오류 LNK2038
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\<이름\>에 대해 잘못된 일치: \<filename.obj\>에서 값 '\<값 1\>'은\<2 값\>과 일치하지 않습니다.'  
  
 링커에 의해 기호 불일치가 발견되었습니다.  이 오류는 앱의 다른 부분을\-응용 프로그램의 부분\-라이브러리 또는 응용 프로그램에 연결 하는 다른 개체 코드를 포함\-기호 충돌 하는 정의를 사용하여 가라킵니다.  [불일치 검색](../../preprocessor/detect-mismatch.md) pragma는 기호를 정의하고 충돌하는 값을 검색하는 데에 사용됩니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트에서 개체 파일이 오래 된 경우 이 오류가 발생할 수 있습니다.  이 오류에 대한 다른 솔루션을 시도하기 전에 현재 개체 파일을 확인하기 위해 정리 빌드를 수행합니다.  
  
-   Visual Studio는 런타임 오류나 기타 예기치 않은 동작이 발생할 수 있는 호환 되지 않는 코드의 연결을 방지 하기 위해 다음과 같은 기호를 정의합니다.  
  
     `_MSC_VER`  
     응용 프로그램이 나 라이브러리를 빌드하는 데 사용되는 Visual C\+\+ 컴파일러의 주 및 부 버전의 번호를 나타냅니다.  한 버전의 Visual C\+\+ 컴파일러를 사용하여 컴파일되는 코드는 서로 다른 주 및 부 버전 번호의 버전을 사용하여 컴파일되는 코드와 호환되지 않습니다.  자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)에서 `_MSC_VER`를 참조하십시오.  
  
     Visual C\+\+ 컴파일러의 버전과 호환되지 않는 라이브러리를 연결하는 경우, 라이브러리의 버전과 호환하여 취득하거나 빌드를 할 수 없을 때, 프로젝트의 **플랫폼 도구** 속성을 바꾸어 프로젝트를 빌드하기 위해 이전 버전의 컴파일러를 사용할 수 있습니다.  자세한 내용은 [방법: 대상 프레임워크 및 플랫폼 도구 집합 수정](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)을 참조하십시오.  
  
     `_ITERATOR_DEBUG_LEVEL`  
     C\+\+ 표준 라이브러리에서 사용가능한 보안 수준 및 디버깅 기능을 나타냅니다.  이러한 기능은 특정 c \+ \+ 표준 라이브러리 오브젝트의 표현을 변경하고 이로 인하여 다른 보안과 디버깅 기능을 사용하여 호환 되지 않도록 합니다.  자세한 내용은 [\_ITERATOR\_DEBUG\_LEVEL](../../standard-library/iterator-debug-level.md)을 참조하십시오.  
  
     `RuntimeLibrary`  
     C\+\+ 표준 라이브러리의 버전과 앱 또는 라이브러리에서 사용되는 C 런타임을 나타냅니다.  C 런타임 또는 c \+ \+ 표준 라이브러리의 버전을 사용하는 코드는 다른 버전을 사용 하는 코드와 호환되지 않습니다.  자세한 내용은 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../../build/reference/md-mt-ld-use-run-time-library.md)을 참조하십시오.  
  
     `_PPLTASKS_WITH_WINRT`  
     [라이브러리 PPL \(병렬 패턴\)](../../parallel/concrt/parallel-patterns-library-ppl.md) 을 사용하는 코드를 나타내는 것은 [\/ZW](../../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션에 대한 서로 다른 설정을 사용하여 컴파일한 개체에 연결됩니다. \(**\/ZW** 는 C \+ \+ \/CX를 지원합니다.\) PPL에 따라 사용하는 코드는 앱의 나머지 부분에서 사용되는 동일한 **\/ZW** 설정을 사용하여 컴파일되어야 합니다.  
  
     이 기호의 값이 Visual Studio 솔루션에서 프로젝트 전체에서 일관되는지 앱과 연결된 라이브러리 및 코드와 일관성이 있는지를 확인해야 합니다.  
  
## 참고 항목  
 [링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)