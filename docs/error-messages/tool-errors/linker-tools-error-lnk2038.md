---
title: "링커 도구 오류 LNK2038 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2038
dev_langs: C++
helpviewer_keywords: LNK2038
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73694359c3fbcaa16455be3ce1197ba99fce56c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2038"></a>링커 도구 오류 LNK2038
일치에 대 한 '\<이름 >': 값 '\<값 1 >' 값과 일치 하지 않는 '\<값 2 >'에 \<filename.obj >  
  
 링커에서 기호 불일치가 검색되었습니다. 이 오류는 라이브러리 또는 응용 프로그램이 링크되는 다른 개체 코드를 포함해서 앱의 여러 부분에 사용되는 기호 정의가 충돌함을 나타냅니다. [불일치 검색](../../preprocessor/detect-mismatch.md) pragma는 그러한 기호를 정의 하 고 해당 충돌 하는 값을 검색 하는 데 사용 됩니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   이 오류는 프로젝트의 개체 파일이 오래된 경우에 발생할 수 있습니다. 이 오류에 대해 다른 솔루션을 시도하기 전에 개체 파일이 최신 상태이도록 깨끗한 빌드를 수행합니다.  
  
-   Visual Studio는 런타임 오류 또는 기타 예기치 않은 동작을 일으킬 수 있는 호환할 수 없는 코드 링크를 방지하기 위해 다음과 같은 기호를 정의합니다.  
  
     `_MSC_VER`  
     응용 프로그램 또는 라이브러리를 빌드하는 데 사용되는 Visual C++ 컴파일러의 주 버전 및 부 버전 번호를 나타냅니다. Visual C++ 컴파일러의 한 버전을 사용해서 컴파일된 코드는 주 버전 및 부 버전 번호가 다른 버전을 사용해서 컴파일된 코드와 호환되지 않습니다. 자세한 내용은 참조 `_MSC_VER` 에 [미리 정의 된 매크로](../../preprocessor/predefined-macros.md)합니다.  
  
     사용 중이 고 얻거나 라이브러리의 호환 버전을 빌드할 수 없는 Visual c + + 컴파일러의 버전과 호환 되지 않는 라이브러리에 연결 하 고 하는 경우 프로젝트를 빌드하려면 이전 버전의 컴파일러를 사용할 수 있습니다-변경할는 **플랫폼 도구 집합** 프로젝트의 속성입니다. 자세한 내용은 참조 [하는 방법: 대상 프레임 워크 및 플랫폼 도구 집합 수정](../../build/how-to-modify-the-target-framework-and-platform-toolset.md)합니다.  
  
     `_ITERATOR_DEBUG_LEVEL`  
     C++ 표준 라이브러리에 설정된 보안 및 디버깅 기능 수준을 나타냅니다. 이러한 기능은 특정 C++ 표준 라이브러리 개체의 표현을 변경할 수 있으며, 그 결과 다른 보안 및 디버깅 기능을 사용하는 개체와 호환되지 않을 수 있습니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../../standard-library/iterator-debug-level.md)을 참조하세요.  
  
     `RuntimeLibrary`  
     응용 프로그램 또는 라이브러리에서 사용되는 C++ 표준 라이브러리 및 C 런타임의 버전을 나타냅니다. C++ 표준 라이브러리 또는 C 런타임 버전 중 하나를 사용하는 코드는 다른 버전을 사용하는 코드와 호환되지 않습니다. 자세한 내용은 [/MD, /MT, /LD(런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md)를 참조하세요.  
  
     `_PPLTASKS_WITH_WINRT`  
     사용 하는 코드가 나타냅니다는 [라이브러리 PPL (병렬 패턴)](../../parallel/concrt/parallel-patterns-library-ppl.md) 에 대 한 다른 설정을 사용 하 여 컴파일된 개체에 링크는 [/ZW](../../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션입니다. (**/ZW** 원하는 C + + /cli CX.) 동일한를 사용 하 여 사용 하거나 PPL에 의존 하는 코드를 컴파일해야 합니다. **/ZW** 응용 프로그램의 나머지 부분에 사용 되는 설정입니다.  
  
     이러한 기호의 값이 Visual Studio 솔루션의 프로젝트 전체에서 일치하고 응용 프로그램이 링크되는 코드 및 라이브러리와도 일치하는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 도구 오류 및 경고](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)