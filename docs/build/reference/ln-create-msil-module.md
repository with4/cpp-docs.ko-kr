---
title: "/LN(MSIL 모듈 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/LN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LN 컴파일러 옵션[C++]"
  - "-LN 컴파일러 옵션[C++]"
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /LN(MSIL 모듈 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

어셈블리 매니페스트를 출력 파일에 삽입하지 않도록 지정합니다.  
  
## 구문  
  
```  
/LN  
```  
  
## 설명  
 기본값은 **\/LN**이 적용되지 않고 어셈블리 매니페스트가 출력 파일에 삽입되는 것입니다.  
  
 **\/LN**을 사용하는 경우 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 옵션 중 하나를 함께 사용해야 합니다.  
  
 매니페스트에 어셈블리 메타데이터가 없는 관리되는 프로그램을 모듈이라고 합니다.  [\/c\(링크 없이 컴파일\)](../../build/reference/c-compile-without-linking.md) 및 **\/LN**을 사용하여 컴파일하는 경우 링커 단계에서 [\/NOASSEMBLY\(MSIL 모듈 만들기\)](../../build/reference/noassembly-create-a-msil-module.md)를 지정하여 출력 파일을 만듭니다.  
  
 구성 요소를 기반으로 한 방식을 사용하여 어셈블리를 빌드하려는 경우 모듈을 만들 수 있습니다.  즉, 형식을 작성하고 이를 모듈로 컴파일할 수 있습니다.  그런 다음 하나 이상의 모듈에서 어셈블리를 생성할 수 있습니다.  모듈에서 어셈블리를 만드는 방법에 대한 자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md) 또는 [Al.exe\(어셈블리 링커\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)를 참조하십시오.  
  
 모듈의 기본 확장명은 .netmodule입니다.  
  
 Visual C\+\+ 2005 이전의 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 릴리스에서는 **\/clr:noAssembly**를 사용하여 모듈을 생성하였습니다.  
  
 Visual C\+\+ 링커 입력으로.netmodule 파일을 수락 하 고 어셈블리 또는.netmodule를 링커에 입력 된 중에 런타임에 종속 하지를 사용 하 여.netmodule 링커에 의해 생성 된 출력 파일 수 있습니다.  자세한 내용은 [링커 입력 파일로 사용하는 .netmodule 파일](../../build/reference/netmodule-files-as-linker-input.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
-   링커 단계에서 [\/NOASSEMBLY\(MSIL 모듈 만들기\)](../../build/reference/noassembly-create-a-msil-module.md)를 지정하여 출력 파일을 만듭니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   이 컴파일러 옵션은 프로그래밍 방식으로 변경할 수 없습니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)