---
title: ".netmodule 입력 파일 형식 선택 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4653d1bd-300f-4083-86f5-d1a06f44e61c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .netmodule 입력 파일 형식 선택
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일한 MSIL .obj 파일은 .netmodule 파일로도 사용할 수 있습니다.  .obj 파일에는 메타데이터와 네이티브 기호가 포함됩니다.  .netmodule 파일에는 메타데이터만 포함됩니다.  
  
 \/addmodule 컴파일러 옵션을 통해 MSIL .obj 파일을 임의의 다른 Visual Studio 컴파일러에 전달할 수 있습니다. 그러나 이 경우 .obj 파일이 어셈블리 결과의 일부가 되므로 어셈블리와 함께 제공해야 한다는 사실에 주의해야 합니다.  예를 들어, Visual C\#과 Visual Basic에 모두 \/addmodule 컴파일러 옵션이 있습니다.  
  
> [!NOTE]
>  대부분의 경우 .net 모듈을 만든 컴파일에서 .obj 파일을 링커에 전달해야 합니다.  이 한 가지 예외는.netmodule를 만든 경우는 [\/clr: pure](../../build/reference/clr-common-language-runtime-compilation.md) 입니다.  LNK1107.dll 또는.netmodule MSIL 모듈 파일을 링커에 전달 될 수 있습니다.  
  
 통해 참조 해당 관련된.h 파일과 함께.obj 파일을 \#include 소스,.netmodule 파일의 경우 관리 되는 형식만 c \+ \+ 응용 프로그램에 의해 사용 될 수 있지만 c \+ \+ 응용 프로그램에서 모듈의 네이티브 형식을 사용할 수 있도록 합니다.  .obj 파일을 \#using에 전달하려고 하면 네이티브 형식에 대한 정보를 사용할 수 없습니다. 대신 .obj 파일의 .h 파일에 대해 \#include를 사용해야 합니다.  
  
 다른 Visual Studio 컴파일러에서는 모듈의 관리되는 형식만 사용할 수 있습니다.  
  
 Visual C\+\+ 링커에 대 한 모듈 입력으로.netmodule 또는.obj 파일을 사용 해야 하는지 여부를 확인 하려면 다음을 사용 합니다.  
  
-   Visual C\+\+ 이외의 다른 Visual Studio 컴파일러를 사용 하 여 작성 하는 경우.netmodule를 생성 한.netmodule는 링커의 입력으로 사용 합니다.  
  
-   Visual C\+\+ 컴파일러를 사용하여 모듈을 생성하고 라이브러리 이외의 대상을 빌드하는 데 모듈을 사용하려는 경우 컴파일러에서 생성된 .obj 파일을 링커에 대한 모듈 입력으로 사용합니다. 이 경우 .netmodule를 input으로 쓰지 마세요.  
  
-   관리되는 라이브러리가 아닌 네이티브 라이브러리를 빌드하는 데 모듈을 사용하려는 경우 링커에 대한 모듈 입력으로 .obj 파일을 사용하여 .lib 라이브러리 파일을 생성합니다.  
  
-   관리되는 라이브러리를 빌드하는 데 모듈을 사용하려는 경우 링커에 대한 모든 모듈 입력이 안정형이면 즉, \/clr:safe를 사용하여 생성한 파일이면 .obj 파일을 링커에 대한 모듈 입력으로 사용하여 .dll\(어셈블리\) 또는 .netmodule \(module\) library file를 사용하세요.  
  
-   관리 되는 라이브러리를 빌드하는 모듈을 링커에 대 한 모듈 입력 모든 \/clr을 사용 하 여 생성 됩니다: pure 또는 \/clr: safe를.obj 파일을 링커에 대 한 모듈 입력으로 사용 하 여.dll \(어셈블리\) 또는.netmodule \(모듈\) 라이브러리에서 관리 되는 형식을 노출 하려는 경우에 생성 합니다.  라이브러리에서 관리되는 형식을 노출하면서 C\+\+ 응용 프로그램에서 라이브러리의 네이티브 형식도 사용하도록 하려는 경우 라이브러리는 해당 라이브러리 구성 요소 모듈에 대한 .obj 파일로 구성됩니다. 각 모듈에 대한 .h 파일도 함께 제공하여 소스 코드에서 \#include를 사용하여 참조할 수 있도록 해야 합니다.  
  
-   관리되는 라이브러리를 빌드하는 데 모듈을 사용하려는 경우 링커에 대한 하나 이상의 모듈 입력이 \/clr만 사용하여 생성한 파일이면 .obj 파일을 링커에 대한 모듈 입력으로 사용하여 .dll\(어셈블리\) 파일을 생성합니다.  라이브러리에서 관리되는 형식을 노출하면서 C\+\+ 응용 프로그램에서 라이브러리의 네이티브 형식도 사용하도록 하려는 경우 라이브러리는 해당 라이브러리 구성 요소 모듈에 대한 .obj 파일로 구성됩니다. 각 모듈에 대한 .h 파일도 함께 제공하여 소스 코드에서 \#include를 사용하여 참조할 수 있도록 해야 합니다.  
  
## 참고 항목  
 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)