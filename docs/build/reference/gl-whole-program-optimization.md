---
title: "-GL (전체 프로그램 최적화) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
dev_langs: C++
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20436df9fd2f54193183505eb56da7c7b3371164
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="gl-whole-program-optimization"></a>/GL(전체 프로그램 최적화)
전체 프로그램 최적화를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GL[-]  
```  
  
## <a name="remarks"></a>설명  
 전체 프로그램 최적화 프로그램에서 모든 모듈에서 정보를 사용 하 여 최적화를 수행 하려면 컴파일러가 수 있습니다. 전체 프로그램 최적화 없이 최적화가 수행 됩니다는 모듈 (컴파일) 별로 합니다.  
  
 전체 프로그램 최적화는 기본적으로 꺼져 있고 명시적으로 설정 해야 합니다. 하지만 사용 하 여 명시적으로 비활성화할 수 이기도 **/GL-**합니다.  
  
 모든 모듈에 대 한 정보를 컴파일러는 다음을 수행할 수 있습니다.  
  
-   함수에 관계 없이 레지스터의 사용을 최적화 합니다.  
  
-   글로벌 데이터를 로드 및 저장의 수를 줄일 수를 수정할 추적의 더 나은 작업을 수행 합니다.  
  
-   더 효율적으로 로드 및 저장 수가 감소 한 포인터에 의해 수정 된 항목의 가능한 집합 역참조, 추적을 수행 합니다.  
  
-   인라인 함수는 다른 모듈에 정의 된 경우에 모듈의 함수입니다.  
  
 .obj 파일에서 생성 된 **/GL** 으로 이러한 링커 유틸리티를 사용할 수는 [EDITBIN](../../build/reference/editbin-reference.md) 및 [DUMPBIN](../../build/reference/dumpbin-reference.md)합니다.  
  
 사용 하 여 프로그램을 컴파일하는 경우 **/GL** 및 [/c](../../build/reference/c-compile-without-linking.md), 출력 파일을 만드는 /LTCG 링커 옵션을 사용 해야 합니다.  
  
 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 함께 사용할 수 없습니다 **/GL**  
  
 파일의 형식에서 생성 된 **/GL** 현재 버전에서 읽을 수 없습니다 Visual c + +의 이후 버전에서 합니다. 사용 하 여 생성 하는.obj 파일의 구성 되는.lib 파일을 제공 해서는 안 **/GL** 가 지금 또는 나중에 사용할 사용자에 게 필요한 모든 버전의 Visual c + +에 대 한.lib 파일의 사본을 제공 있지 않은 경우.  
  
 .obj 파일에서 생성 된 **/GL** .lib 파일 생성 되는 동일한 컴퓨터에 연결 됩니다 하지 않는 한.lib 파일을 만드는 미리 컴파일된 헤더 파일을 사용할 수 해야는 **/GL** .obj 파일입니다. .Obj 파일의 미리 컴파일된 헤더 파일에서 정보 링크 타임에 필요 합니다.  
  
 사용할 수 있는 최적화 및 전체 프로그램 최적화의 제한에 대 한 자세한 내용은 참조 하십시오. [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)합니다.  **/GL** 또한을 사용 하면 프로필 안내 최적화를 사용할 수. /LTCG을 참조 합니다.  프로필 기반 최적화 함수의 순서 프로필 기반 최적화를 지정 하려는 경우에 대 한를 컴파일할 때 컴파일하여 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 또는 /Gy를 의미 하는 컴파일러 옵션입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  참조 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md) 지정 하는 방법에 대 한 내용은 **/GL** 개발 환경에서 합니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)